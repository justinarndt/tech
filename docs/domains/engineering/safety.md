---
title: Safety Documentation
description: Writing safety procedures, warnings, and compliance documentation.
---

# Safety Documentation

Safety documentation protects workers, equipment, and the environment. From hazard warnings to emergency procedures, safety writing requires precision, clarity, and compliance with regulations.

## Regulatory Framework

### Key Regulations

**United States:**
- OSHA (Occupational Safety and Health Administration)
- ANSI standards
- NFPA codes

**International:**
- ISO 45001 (Occupational health and safety)
- ISO 12100 (Safety of machinery)
- IEC 82079 (Preparation of instructions)

### Compliance Requirements

Safety documentation must:

- Identify hazards
- Communicate risks clearly
- Provide protective measures
- Meet regulatory standards
- Be accessible to users

## Signal Words and Symbols

### ANSI Z535 Signal Words

| Signal Word | Meaning | Use When |
|-------------|---------|----------|
| **DANGER** | Immediate hazard | Death or serious injury WILL occur |
| **WARNING** | Potential hazard | Death or serious injury COULD occur |
| **CAUTION** | Potential hazard | Minor or moderate injury COULD occur |
| **NOTICE** | Property damage | Equipment or property damage possible |

### Safety Alert Symbol

The safety alert symbol (⚠️) precedes DANGER, WARNING, and CAUTION but NOT NOTICE.

### Formatting

```markdown
⚠️ **WARNING: Electrical Shock Hazard**

Contact with live electrical parts will cause
death or serious injury.

Disconnect and lock out power before servicing.
```

### Color Coding

| Signal Word | Background | Text |
|-------------|------------|------|
| DANGER | Red | White |
| WARNING | Orange | Black |
| CAUTION | Yellow | Black |
| NOTICE | Blue | White |

## Safety Procedure Structure

### Standard Safety Procedure

```markdown
# Safety Procedure SP-001
# Confined Space Entry

## 1. Purpose

This procedure establishes requirements for safe entry
into confined spaces.

## 2. Scope

Applies to all personnel who enter or supervise entry
into permit-required confined spaces.

## 3. Definitions

| Term | Definition |
|------|------------|
| Confined Space | Space with limited entry/exit, not designed for continuous occupancy |
| Permit-Required | Confined space with serious hazards |
| Entrant | Person who enters confined space |
| Attendant | Person stationed outside confined space |
| Entry Supervisor | Person responsible for entry operations |

## 4. Hazards

### Atmospheric Hazards
- Oxygen deficiency (<19.5%) or enrichment (>23.5%)
- Flammable gases or vapors
- Toxic gases (H2S, CO, etc.)

### Physical Hazards
- Engulfment
- Entrapment
- Mechanical hazards
- Electrical hazards

## 5. Responsibilities

### Entry Supervisor
- Verify permit completion
- Ensure rescue procedures in place
- Cancel permit when conditions change

### Attendant
- Remain outside space at all times
- Monitor entrants and conditions
- Summon rescue if needed
- Prevent unauthorized entry

### Entrant
- Know hazards and symptoms
- Use required equipment properly
- Exit immediately when ordered or if hazard detected

## 6. Procedure

### 6.1 Pre-Entry

1. Entry Supervisor completes confined space permit.

2. Verify all hazards identified and controlled:
   - Isolation verified (lockout/tagout)
   - Ventilation established
   - Atmosphere tested

3. Atmospheric testing required:

   | Parameter | Acceptable Range |
   |-----------|------------------|
   | Oxygen | 19.5% - 23.5% |
   | LEL | <10% |
   | H2S | <10 ppm |
   | CO | <25 ppm |

4. Verify rescue equipment available:
   - Full body harness and retrieval line
   - Tripod and winch (if applicable)
   - SCBA available for rescue

### 6.2 Entry Operations

5. Entrant dons required PPE:
   - Hard hat
   - Safety glasses
   - Appropriate respiratory protection

6. Attendant establishes communication with entrant.

7. Entry Supervisor authorizes entry.

8. Continuous atmospheric monitoring during entry.

9. If any alarm condition:
   - Evacuate immediately
   - Notify Entry Supervisor
   - Do not re-enter until cleared

### 6.3 Post-Entry

10. Entrant exits space.

11. Entry Supervisor closes permit.

12. Document any incidents or observations.

## 7. Emergency Response

### Alarm Conditions
- Atmospheric alarm
- Entrant unresponsive
- Hazardous condition observed

### Response
1. Attendant orders evacuation
2. Attendant calls for rescue team (do NOT enter)
3. Entry Supervisor notified
4. Rescue team responds per rescue plan

**NEVER ENTER TO RESCUE WITHOUT PROPER EQUIPMENT AND TRAINING**

## 8. Training Requirements

| Role | Initial | Refresher |
|------|---------|-----------|
| Entrant | 8 hours | Annual |
| Attendant | 8 hours | Annual |
| Entry Supervisor | 8 hours | Annual |
| Rescue Team | 16 hours | Annual + quarterly drills |

## 9. Documentation

- Retain permits for 1 year
- Document all entries in logbook
- Report all incidents per incident reporting procedure

## 10. References

- OSHA 29 CFR 1910.146
- ANSI Z117.1 Confined Space Safety
- Company Emergency Response Plan
```

## Hazard Communication

### Safety Data Sheets (SDS)

16-section GHS format:

```markdown
# Safety Data Sheet
# [Product Name]

## Section 1: Identification

**Product Identifier**: [Chemical name]
**Product Code**: [Code]
**Supplier**: [Company name and contact]
**Emergency Phone**: [Number]

## Section 2: Hazard Identification

**GHS Classification**:
- Flammable Liquid, Category 2
- Eye Irritation, Category 2A

**Signal Word**: DANGER

**Hazard Statements**:
- H225: Highly flammable liquid and vapor
- H319: Causes serious eye irritation

**Precautionary Statements**:
- P210: Keep away from heat, sparks, open flames
- P233: Keep container tightly closed
- P280: Wear protective gloves/eye protection

**Pictograms**:
[Flame symbol] [Exclamation mark symbol]

## Section 3: Composition/Information on Ingredients

| Component | CAS Number | Concentration |
|-----------|------------|---------------|
| [Chemical 1] | [CAS] | 80-90% |
| [Chemical 2] | [CAS] | 10-20% |

## Section 4: First-Aid Measures

**Inhalation**: Move to fresh air. If symptoms persist, seek medical attention.

**Skin Contact**: Wash with soap and water. Remove contaminated clothing.

**Eye Contact**: Rinse with water for 15 minutes. Seek medical attention.

**Ingestion**: Do NOT induce vomiting. Seek medical attention immediately.

[Continue with Sections 5-16...]
```

### Labels

```markdown
# Product Label Requirements

**Product Name**: [Name]

**Signal Word**: DANGER

**Hazard Statements**:
- Highly flammable liquid and vapor
- Causes serious eye irritation

**Pictograms**: [Flame] [Exclamation]

**Precautionary Statements**:
- Keep away from heat, sparks, flames
- Wear eye protection
- IF IN EYES: Rinse cautiously with water

**Supplier Information**:
[Company Name]
[Address]
[Phone]
```

## Lockout/Tagout Documentation

### LOTO Procedure

```markdown
# Lockout/Tagout Procedure
# Equipment: [Name]

## Energy Sources

| # | Type | Location | Isolation Method |
|---|------|----------|------------------|
| 1 | Electrical | MCC Panel 2, Breaker 15 | Lock in OFF position |
| 2 | Pneumatic | Supply valve V-101 | Close and lock |
| 3 | Hydraulic | Pump disconnect | Lock in OFF position |
| 4 | Stored Energy | Accumulator | Bleed down |

## Lockout Sequence

### Shutdown

1. Notify affected employees of shutdown.
2. Operate equipment stop controls.
3. Verify equipment has stopped.

### Isolation

4. Electrical (Source #1):
   - Open breaker in MCC Panel 2
   - Install lock with tag
   - Verify open position

5. Pneumatic (Source #2):
   - Close valve V-101
   - Install lock with tag
   - Bleed downstream pressure

6. Hydraulic (Source #3):
   - Operate pump disconnect
   - Install lock with tag

7. Stored Energy (Source #4):
   - Open bleed valve on accumulator
   - Verify zero pressure on gauge

### Verification

8. Attempt to start equipment at all start points.
9. Verify zero energy:
   - Use voltmeter on electrical
   - Verify zero on pressure gauges

## Release Sequence

1. Verify all tools removed from equipment.
2. Verify all guards reinstalled.
3. Verify all personnel clear of equipment.
4. Remove locks and tags in reverse order.
5. Restore energy sources.
6. Notify affected employees of restart.
```

## Emergency Response Documentation

### Emergency Action Plan

```markdown
# Emergency Action Plan
# [Facility Name]

## Emergency Contacts

| Emergency | Contact |
|-----------|---------|
| Fire/Medical | 911 |
| Plant Emergency | Ext. 5555 |
| Environmental | [Number] |
| Security | Ext. 5500 |

## Emergency Types

### Fire

1. Activate nearest fire alarm pull station.
2. Call 911 and Plant Emergency.
3. Evacuate using nearest safe exit.
4. Meet at designated assembly point.
5. Account for all personnel.

### Chemical Spill

1. Evacuate immediate area.
2. Call Plant Emergency.
3. Do NOT attempt cleanup unless trained.
4. Prevent spread if safe to do so.
5. Provide SDS to responders.

### Medical Emergency

1. Call 911.
2. Do not move victim unless in danger.
3. Provide first aid if trained.
4. Send someone to guide responders.

## Evacuation

### Assembly Points

- Building A: North parking lot
- Building B: South parking lot
- Warehouse: Loading dock area

### Evacuation Routes

[Include evacuation maps]

### Accountability

Department supervisors account for all personnel
and report to Emergency Coordinator.
```

## Summary

Effective safety documentation:

- Uses proper signal words and formatting
- Clearly identifies hazards and risks
- Provides specific protective measures
- Complies with applicable regulations
- Supports emergency response

Clear safety documentation prevents injuries and saves lives.
