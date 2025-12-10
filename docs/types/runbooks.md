---
title: Writing Runbooks
description: Learn how to create operational runbooks that guide teams through system maintenance, incident response, and routine procedures.
---

# Runbooks

Runbooks document operational procedures for maintaining and troubleshooting systems. They provide step-by-step guidance for common tasks, incident response, and system recovery. Good runbooks enable consistent operations and reduce mean time to recovery during incidents.

## Runbook Purpose

Runbooks help operations teams:

- Respond to incidents consistently
- Perform routine maintenance safely
- Onboard new team members
- Reduce dependency on tribal knowledge
- Meet compliance requirements

## Runbook Types

### Incident Response Runbooks

For handling alerts and outages:

```markdown
# Runbook: High CPU Alert

## Alert Details
- **Alert Name**: High CPU Usage
- **Threshold**: CPU > 90% for 5 minutes
- **Severity**: High
- **Escalation**: Page on-call engineer

## Initial Assessment

1. Check if alert is real or false positive
   ```bash
   ssh prod-server
   top -bn1 | head -20
   ```

2. Identify the process consuming CPU
   ```bash
   ps aux --sort=-%cpu | head -10
   ```

3. Check if this correlates with traffic
   ```bash
   curl -s localhost:9090/metrics | grep requests_total
   ```

## Common Causes and Solutions

### Cause: Traffic Spike

**Symptoms**: Request rate significantly above normal

**Actions**:
1. Verify this is legitimate traffic (not attack)
2. Scale horizontally if possible
   ```bash
   kubectl scale deployment api --replicas=5
   ```
3. Enable rate limiting if needed

### Cause: Runaway Process

**Symptoms**: Single process consuming most CPU

**Actions**:
1. Identify the process and its purpose
2. Check logs for errors
   ```bash
   journalctl -u myservice -n 100
   ```
3. Restart if safe
   ```bash
   systemctl restart myservice
   ```

### Cause: Memory Pressure

**Symptoms**: OOM killer active, swap usage high

**Actions**:
1. Check memory usage
   ```bash
   free -h
   ```
2. Identify memory-hungry processes
3. Restart affected services

## Escalation

If unable to resolve within 15 minutes:
1. Page secondary on-call
2. Create incident channel: #incident-YYYYMMDD
3. Notify stakeholders via status page
```

### Maintenance Runbooks

For routine operations:

```markdown
# Runbook: Database Backup Verification

## Purpose
Weekly verification that database backups are completing
and restorable.

## Schedule
Every Monday, 10:00 AM

## Prerequisites
- Access to backup storage
- Restore environment available
- 2 hours of uninterrupted time

## Procedure

### 1. Verify Backup Completion

Check that nightly backup completed:

```bash
aws s3 ls s3://backups/database/$(date -d yesterday +%Y%m%d)/
```

Expected: backup file present, size > 1GB

### 2. Download Latest Backup

```bash
aws s3 cp s3://backups/database/$(date -d yesterday +%Y%m%d)/db.sql.gz ./
```

### 3. Restore to Test Environment

```bash
gunzip -c db.sql.gz | psql -h test-db -U admin testdb
```

Expected: No errors, restore completes

### 4. Verify Data Integrity

Run validation queries:

```sql
-- Check record counts
SELECT COUNT(*) FROM users;  -- Expected: > 10000
SELECT COUNT(*) FROM orders; -- Expected: > 50000

-- Check recent data
SELECT MAX(created_at) FROM orders;
-- Expected: Yesterday's date
```

### 5. Document Results

Record in backup log:
- Backup date
- File size
- Restore time
- Verification status
- Any issues encountered

### 6. Clean Up

```bash
rm db.sql.gz
psql -h test-db -U admin -c "DROP DATABASE testdb; CREATE DATABASE testdb;"
```

## Troubleshooting

### Backup missing
1. Check backup job logs
2. Verify storage permissions
3. Escalate if backup job failed

### Restore fails
1. Check disk space on restore target
2. Verify database permissions
3. Check for corruption in backup file
```

### Deployment Runbooks

For release procedures:

```markdown
# Runbook: Production Deployment

## Pre-Deployment Checklist

- [ ] All tests passing in CI
- [ ] Code review completed
- [ ] Changelog updated
- [ ] Stakeholders notified
- [ ] Rollback plan reviewed

## Deployment Steps

### 1. Notify Team

Post in #deployments:
> Starting production deployment of v1.2.3

### 2. Create Deployment Snapshot

```bash
kubectl get deployment api -o yaml > pre-deploy-snapshot.yaml
```

### 3. Deploy

```bash
kubectl set image deployment/api api=myapp:v1.2.3
```

### 4. Monitor Rollout

```bash
kubectl rollout status deployment/api
```

Wait for "successfully rolled out" message.

### 5. Verify Deployment

Run smoke tests:
```bash
./scripts/smoke-test.sh production
```

Check key metrics:
- Error rate: Should be < 0.1%
- Latency p99: Should be < 500ms
- Request rate: Should be stable

### 6. Announce Completion

Post in #deployments:
> Production deployment of v1.2.3 complete ✓

## Rollback Procedure

If issues detected:

### Immediate Rollback

```bash
kubectl rollout undo deployment/api
```

### Restore from Snapshot

If rollback fails:
```bash
kubectl apply -f pre-deploy-snapshot.yaml
```

### Post-Rollback

1. Notify team of rollback
2. Create incident report
3. Investigate root cause
```

## Writing Effective Runbooks

### Be Specific

Provide exact commands:

**Vague:**
> Check the logs for errors

**Specific:**
> Check application logs:
> ```bash
> kubectl logs -l app=api --tail=100 | grep ERROR
> ```

### Include Expected Output

Show what success looks like:

```markdown
Run health check:
```bash
curl http://localhost:8080/health
```

Expected output:
```json
{"status": "healthy", "version": "1.2.3"}
```

If status is not "healthy", proceed to troubleshooting.
```

### Provide Context

Explain why, not just what:

```markdown
### 2. Enable Maintenance Mode

Before proceeding, enable maintenance mode to prevent data
corruption during the migration:

```bash
./scripts/maintenance-mode.sh enable
```

This redirects traffic to a static page and blocks API writes.
```

### Cover Failure Cases

Document what to do when things go wrong:

```markdown
## Troubleshooting

### Command hangs

If the migration command hangs for more than 10 minutes:

1. Do NOT kill the process (may cause corruption)
2. Check database locks:
   ```sql
   SELECT * FROM pg_locks WHERE NOT granted;
   ```
3. Contact DBA for assessment
```

### Include Contact Information

Provide escalation paths:

```markdown
## Escalation

| Issue | Contact | Method |
|-------|---------|--------|
| Database | DBA Team | #dba-oncall |
| Infrastructure | Platform Team | Page via PagerDuty |
| Business Impact | Product Manager | Slack @pm-oncall |
```

## Runbook Maintenance

### Keep Current

Runbooks must reflect current systems:

- Update when systems change
- Review after incidents
- Test procedures periodically
- Remove obsolete content

### Version Control

Track runbook changes:

- Use git for runbook storage
- Require review for changes
- Link to related system changes

### Test Runbooks

Verify procedures work:

- Run through procedures regularly
- Use game days to test incident runbooks
- Update based on findings

## Summary

Runbooks guide operational procedures:

- Provide specific, copy-paste commands
- Include expected outputs
- Cover failure scenarios
- Keep procedures current
- Test regularly

Good runbooks reduce incident response time and ensure consistent operations.

---

**Next**: [Internal Documentation](internal-documentation.md) covers team-facing documentation.
