---
title: Construction Documentation
description: Technical writing for construction projects and building systems.
---

# Construction Documentation

Construction documentation guides the design, building, and commissioning of structures and facilities. From project specifications to as-built drawings, these documents ensure projects are built correctly and can be maintained properly.

## Documentation Lifecycle

### Project Phases

```
Programming → Design → Construction → Commissioning → Operations
     ↓           ↓          ↓              ↓              ↓
  Program    Drawings   Submittals   Punch Lists   O&M Manuals
  Documents  and Specs  RFIs, ASIs   Testing       As-Builts
```

## Design Documents

### Construction Drawings

Types of drawings:

| Drawing Type | Content |
|--------------|---------|
| Architectural | Floor plans, elevations, details |
| Structural | Foundation, framing, connections |
| Mechanical | HVAC systems, equipment |
| Electrical | Power, lighting, systems |
| Plumbing | Piping, fixtures, drainage |
| Civil | Site work, grading, utilities |

### Construction Specifications

CSI MasterFormat organization:

```markdown
# Project Manual Structure

Division 00 - Procurement and Contracting Requirements
Division 01 - General Requirements
Division 02 - Existing Conditions
Division 03 - Concrete
Division 04 - Masonry
Division 05 - Metals
Division 06 - Wood, Plastics, Composites
Division 07 - Thermal and Moisture Protection
Division 08 - Openings
Division 09 - Finishes
Division 10 - Specialties
...
Division 23 - HVAC
Division 26 - Electrical
Division 27 - Communications
Division 28 - Electronic Safety and Security
...
```

### Specification Section Format

```markdown
# SECTION 09 91 00 - PAINTING

## PART 1 - GENERAL

### 1.1 SUMMARY

A. Section Includes:
   1. Surface preparation
   2. Primer application
   3. Finish coat application

B. Related Sections:
   1. Section 05 50 00 - Metal Fabrications
   2. Section 06 20 00 - Finish Carpentry
   3. Section 09 29 00 - Gypsum Board

### 1.2 REFERENCES

A. ASTM D16 - Standard Terminology for Paint

B. SSPC-SP 2 - Hand Tool Cleaning

C. SSPC-SP 3 - Power Tool Cleaning

### 1.3 SUBMITTALS

A. Product Data: Submit manufacturer's product data
   for each paint system specified.

B. Samples: Submit 8" x 8" samples of each color
   and finish for approval.

C. Manufacturer's Certificate: Submit certification
   that products meet specified requirements.

### 1.4 QUALITY ASSURANCE

A. Applicator Qualifications: Minimum 5 years experience
   in commercial painting applications.

B. Pre-Installation Meeting: Conduct meeting with
   Contractor, applicator, and Architect.

## PART 2 - PRODUCTS

### 2.1 MANUFACTURERS

A. Acceptable Manufacturers:
   1. Sherwin-Williams
   2. Benjamin Moore
   3. PPG Industries

### 2.2 PAINT MATERIALS

A. Interior Latex Paint:
   1. Semi-Gloss: [Product name], or equal
   2. Eggshell: [Product name], or equal

B. Metal Primer:
   1. Rust-inhibitive primer for ferrous metals
   2. [Product name], or equal

### 2.3 COLORS

A. Colors as selected by Architect from
   manufacturer's standard colors.

B. Provide color samples for approval before
   beginning work.

## PART 3 - EXECUTION

### 3.1 EXAMINATION

A. Verify surfaces are clean, dry, and ready
   for paint application.

B. Notify Architect of conditions that will
   adversely affect paint application.

### 3.2 PREPARATION

A. Remove hardware, covers, and accessories.

B. Protect adjacent surfaces from paint.

C. Prepare surfaces per manufacturer's instructions:
   1. Fill holes and imperfections
   2. Sand smooth
   3. Clean dust and debris

### 3.3 APPLICATION

A. Apply paint per manufacturer's instructions.

B. Apply minimum coats specified in Paint Schedule.

C. Allow proper dry time between coats.

### 3.4 PROTECTION

A. Protect painted surfaces from damage.

B. Touch up damaged areas to match.

### 3.5 CLEANING

A. Remove masking and protection.

B. Clean paint from adjacent surfaces.

C. Remove debris from work area.

END OF SECTION
```

## Construction Administration Documents

### Request for Information (RFI)

```markdown
# REQUEST FOR INFORMATION

**Project**: [Project Name]
**RFI Number**: RFI-001
**Date**: [Date]
**From**: [Contractor]
**To**: [Architect]

## Subject

Clarification of foundation reinforcement at Grid C-3

## Question

Drawing S-201 shows #5 bars at 12" o.c. for the foundation
wall, but Detail 3/S-401 shows #4 bars at 8" o.c. Please
clarify which is correct.

## Reference Documents

- Drawing S-201, Foundation Plan
- Drawing S-401, Detail 3

## Suggested Resolution

Based on similar conditions elsewhere, we believe #5 at 12"
is correct. Please confirm.

## Impact if Not Resolved

- Schedule: 3-day delay to foundation work
- Cost: No impact if resolved within 5 days

## Response Required By

[Date]

---

## Architect's Response

**Response Date**: [Date]

Use #5 bars at 12" o.c. as shown on S-201. Detail 3/S-401
will be revised on the next ASI.

**Signed**: _____________ **Date**: _______
```

### Submittal

```markdown
# SUBMITTAL TRANSMITTAL

**Project**: [Project Name]
**Submittal Number**: SUB-023
**Date**: [Date]
**Specification Section**: 09 91 00 - Painting

## Items Submitted

1. Product data sheets for:
   - ProMar 200 Interior Latex Semi-Gloss
   - ProMar 200 Interior Latex Eggshell
   - Pro Industrial DTM Acrylic Primer

2. Color samples (8" x 8"):
   - SW 7015 Repose Gray (walls)
   - SW 7006 Extra White (trim)

## Contractor Certification

I certify these products meet specification requirements.

**Signed**: _____________ **Date**: _______

---

## Architect Review

☐ Approved
☐ Approved as Noted
☐ Revise and Resubmit
☐ Rejected

**Comments**: _________________________________

**Signed**: _____________ **Date**: _______
```

### Architect's Supplemental Instruction (ASI)

```markdown
# ARCHITECT'S SUPPLEMENTAL INSTRUCTION

**Project**: [Project Name]
**ASI Number**: ASI-005
**Date**: [Date]

## Description of Change

Revise interior paint colors in Conference Room 201.

## Affected Documents

- Drawing A-301, Room Finish Schedule
- Specification Section 09 91 00

## Instructions

1. Change wall color from SW 7015 Repose Gray
   to SW 7029 Agreeable Gray.

2. Accent wall (north wall) to be SW 6244 Naval.

3. All other finishes per original documents.

## Cost and Schedule Impact

No change to contract sum or time. This clarifies
selections only.

**Issued By**: _____________ **Date**: _______
```

## Commissioning Documentation

### Commissioning Plan

```markdown
# Commissioning Plan
# [Project Name]

## 1. Overview

### 1.1 Purpose
This plan establishes commissioning requirements to verify
building systems perform per design intent.

### 1.2 Systems to be Commissioned
- HVAC systems
- Lighting controls
- Building automation system
- Fire alarm system
- Emergency power

## 2. Commissioning Team

| Role | Responsibility |
|------|----------------|
| Commissioning Agent | Lead commissioning process |
| Contractor | Perform pre-functional checks |
| TAB Contractor | Testing and balancing |
| Controls Contractor | Program and verify controls |

## 3. Commissioning Process

### Phase 1: Pre-Functional Testing

Contractor verifies:
- Equipment installed per specifications
- Connections complete
- Startup procedures complete
- Safety devices functional

### Phase 2: Functional Performance Testing

Commissioning Agent verifies:
- Sequences of operation
- Control strategies
- System integration
- Performance under various conditions

### Phase 3: Seasonal Testing

Verify performance in:
- Heating mode
- Cooling mode
- Economizer operation

## 4. Documentation Requirements

- Pre-functional checklists
- Functional test procedures
- Test results and deficiency logs
- Final commissioning report
```

### Functional Test Procedure

```markdown
# Functional Test Procedure
# Air Handling Unit AHU-1

## Equipment Information

| Parameter | Value |
|-----------|-------|
| Unit Tag | AHU-1 |
| Location | Mechanical Room 1 |
| Capacity | 10,000 CFM |
| Serves | Floors 1-2 |

## Test Conditions

- Outdoor temp: Record actual
- Building occupancy: Normal
- All terminal units operational

## Test Procedures

### Test 1: Supply Fan Operation

**Procedure**:
1. Command fan ON from BAS
2. Verify fan starts
3. Verify VFD operates
4. Record supply static pressure

**Expected Result**: Fan operates, SP = 1.5" w.c. ±0.1

**Actual Result**: _____________

☐ Pass  ☐ Fail

### Test 2: Economizer Operation

**Procedure**:
1. Simulate OAT at 55°F
2. Observe damper positions
3. Verify minimum OA maintained

**Expected Result**: OA damper 100%, RA damper modulates

**Actual Result**: _____________

☐ Pass  ☐ Fail

### Test 3: Cooling Sequence

**Procedure**:
1. Set space temp setpoint to 70°F
2. Simulate space temp at 74°F
3. Observe cooling response

**Expected Result**: Cooling valve modulates to maintain setpoint

**Actual Result**: _____________

☐ Pass  ☐ Fail

## Deficiencies

| Item | Description | Responsible Party | Due Date |
|------|-------------|-------------------|----------|
| | | | |

## Signatures

**Tested By**: _____________ **Date**: _______

**Witnessed By**: _____________ **Date**: _______
```

## Operations and Maintenance Documentation

### O&M Manual Contents

```markdown
# Operations and Maintenance Manual
# [Building Name]

## Volume 1: General Information
- Project directory
- Building overview
- Emergency procedures
- Warranty information

## Volume 2: Architectural
- Exterior materials
- Interior finishes
- Doors and hardware
- Specialties

## Volume 3: Mechanical
- HVAC systems
- Plumbing systems
- Fire protection

## Volume 4: Electrical
- Power distribution
- Lighting systems
- Fire alarm
- Communications

## Each Section Includes:
- System description
- Equipment schedules
- Operation procedures
- Maintenance schedules
- Parts lists
- Manufacturer literature
- As-built drawings
- Warranty documents
```

## Summary

Construction documentation requires:

- Precise technical specifications
- Clear communication during construction
- Thorough commissioning verification
- Complete O&M documentation for operations

Good construction documentation ensures projects are built correctly and can be maintained effectively throughout their lifecycle.
