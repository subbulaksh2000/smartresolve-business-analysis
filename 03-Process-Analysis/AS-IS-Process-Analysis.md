# AS-IS Outpatient Referral Process Analysis

## Purpose

This document describes the current outpatient referral process at the fictional
BrightCare Health organisation.

The AS-IS analysis identifies existing activities, stakeholders, hand-offs,
decisions and pain points before the proposed CarePath solution is introduced.

## Process Trigger

The process begins when a referring clinician determines that a patient requires
assessment or treatment by a specialist outpatient service.

## Current-State Process

| Step | Actor | Current Activity | Output | Pain Point |
|---|---|---|---|---|
| 1 | Referring Clinician | Determines that the patient requires specialist care | Decision to create referral | Referral criteria may not be easily available |
| 2 | Referring Clinician | Completes a referral using an email, scanned form or available template | Referral document | Different forms capture inconsistent information |
| 3 | Referring Clinician | Sends the referral to BrightCare Health | Submitted referral | No immediate confirmation or status visibility |
| 4 | Referral Administration Officer | Receives and manually records the referral | Referral record | Manual data entry is time-consuming and may introduce errors |
| 5 | Referral Administration Officer | Checks whether required patient, referrer and clinical information is present | Completeness decision | Completeness checking is manual |
| 6 | Referral Administration Officer | Contacts the referrer when information is missing | Request for additional information | Creates repeated communication and processing delays |
| 7 | Referring Clinician | Provides the missing information | Updated referral | Referral remains pending while staff wait for a response |
| 8 | Referral Administration Officer | Routes the complete referral to a specialty | Referral assigned to specialty | Manual routing may result in incorrect assignment |
| 9 | Clinical Review Nurse | Reviews clinical information, suitability and urgency | Clinical review decision | Review may be delayed by incomplete or poorly organised information |
| 10 | Clinical Review Nurse | Accepts, returns or declines the referral | Referral outcome | Outcome communication may be inconsistent |
| 11 | Appointment Scheduling Officer | Identifies an available appointment for an accepted referral | Appointment booking | Scheduling information may be stored separately |
| 12 | Appointment Scheduling Officer | Contacts the patient with appointment details | Patient notification | Communication attempts may not be consistently tracked |
| 13 | Healthcare Operations Manager | Reviews spreadsheets and reports to monitor performance | Operational report | Reporting is delayed and provides limited backlog visibility |

## Main Decision Points

### Decision 1: Is the referral complete?

- **Yes:** Continue to specialty routing.
- **No:** Return to the referring clinician for additional information.

### Decision 2: Is the referral appropriate for the selected specialty?

- **Yes:** Continue to clinical prioritisation.
- **No:** Redirect or return the referral.

### Decision 3: Is the referral clinically accepted?

- **Yes:** Continue to appointment scheduling.
- **No:** Record the reason and notify the referrer.

## Current-State Pain Points

### Inconsistent Referral Submission

Referrals arrive through different channels and formats, resulting in inconsistent
information quality.

### Manual Completeness Validation

Administrative staff manually review every referral to identify missing
information.

### Repeated Communication

Incomplete referrals create additional emails and telephone communication
between referral staff and referring clinicians.

### Manual Referral Routing

Staff must determine the appropriate specialty without standardised
administrative routing support.

### Limited Status Visibility

Patients and referring clinicians cannot easily see whether a referral has been
received, reviewed, accepted or scheduled.

### Fragmented Information

Referral information, clinical documents, appointments and communications may be
maintained in separate locations.

### Limited Operational Reporting

Managers have limited visibility of referral volumes, processing time, waiting
time, incomplete referrals and service backlogs.

## Process End States

The AS-IS process ends when the referral is:

- Accepted and an appointment is booked.
- Returned for additional information.
- Redirected to another specialty.
- Declined with a recorded reason.
- Cancelled or closed.

## Analysis Note

The described pain points and process steps are hypotheses for this fictional
portfolio project. In a real engagement, they would be validated through
stakeholder interviews, process observation, document review and operational
data analysis.
