# CarePath Pain-Point and Root-Cause Analysis

## Purpose

This document identifies the operational challenges, root causes and business
impacts within the current outpatient referral-management process.

The analysis supports the design of CarePath, an AI-assisted administrative
referral-management concept that retains human control over all clinical
decisions.

## Pain-Point Analysis

| Process Stage | Pain Point | Likely Root Cause | Business Impact | CarePath Opportunity |
|---|---|---|---|---|
| Referral submission | Referrals arrive through different channels and formats | No standard digital referral form | Inconsistent information and additional administrative effort | Standardised digital submission |
| Completeness checking | Staff manually check every referral | No automated mandatory-field validation | Processing delays and avoidable rework | Automated completeness validation |
| Missing information | Staff repeatedly contact referrers | Required fields and supporting documents are unclear | Longer referral-processing time | Identify missing items and prepare a follow-up draft |
| Administrative routing | Referrals may enter the wrong specialty queue | Complex routing rules and inconsistent interpretation | Reassignment and delayed clinical review | AI-assisted administrative routing recommendation |
| Clinical review | Clinicians receive administratively incomplete referrals | Validation occurs too late in the process | Clinical time is used inefficiently | Complete administrative checks before clinical review |
| Prioritisation | Clinical decisions may be recorded inconsistently | Decisions are captured across separate systems | Limited visibility and inconsistent tracking | Structured recording of the authorised clinician's decision |
| Status tracking | Referral progress is difficult to monitor | No central referral-status record | More enquiries and uncertainty | Centralised referral-status tracking |
| Appointment booking | Accepted referrals may wait before scheduling | Review and booking processes are disconnected | Longer patient waiting time | Create a booking task after acceptance |
| Notifications | Updates are manually prepared | No event-based notification workflow | Delayed or inconsistent communication | Draft notifications for staff approval |
| Reporting | Operational reports are manually created | Fragmented data and inconsistent fields | Limited performance visibility | Standardised data and Power BI reporting |
| Governance | Actions and changes may not be consistently recorded | Limited audit history | Decisions and activities are difficult to trace | Timestamped audit trail |
| Privacy | Unnecessary sensitive information may be copied | Unclear data-minimisation rules | Privacy and compliance risks | Minimum necessary fields and synthetic prototype data |

## Root-Cause Categories

### People

- Staff may interpret routing rules differently.
- Process roles and ownership may be unclear.
- Clinical staff may spend time resolving administrative issues.

### Process

- There is no standard end-to-end referral workflow.
- Completeness checks are performed manually.
- Missing-information follow-up is inconsistent.
- Referral review and appointment booking are disconnected.

### Technology

- Information may be stored across separate systems.
- There is no automated validation or routing assistance.
- Referral-status visibility is limited.
- Reports require manual preparation.

### Data

- Mandatory information may be missing.
- Referral terminology may be inconsistent.
- Status values may not be standardised.
- Actions and decision timestamps may not be recorded consistently.

### Governance

- Auditability is limited.
- AI recommendation boundaries may not be clearly defined.
- Privacy, access and retention requirements require formal definition.

## Prioritised MVP Problems

The CarePath minimum viable product will focus on:

1. Incomplete referrals.
2. Incorrect or delayed administrative routing.
3. Limited referral-status visibility.
4. Manual missing-information follow-up.
5. Fragmented audit records.
6. Manual operational reporting.

## Responsible AI Boundary

CarePath may support administrative activities such as completeness checking,
routing recommendations, status tracking and draft notifications.

CarePath will not:

- Diagnose a patient.
- Recommend treatment.
- Process emergency referrals.
- Make autonomous clinical-priority decisions.
- Replace authorised healthcare professionals.
- Use real patient data in the prototype.

All clinical review, acceptance and prioritisation decisions remain under human
control.

## Expected Business Benefits

CarePath is expected to:

- Reduce avoidable administrative rework.
- Improve referral completeness.
- Support more consistent administrative routing.
- Improve referral-status visibility.
- Strengthen auditability.
- Support operational reporting through Power BI.
- Allow clinicians to focus on clinical decision-making.

## Next Step

The next project activity is to design the CarePath TO-BE process and map how
referrals move through submission, validation, routing recommendation, human
clinical review, appointment booking, notification and reporting.
