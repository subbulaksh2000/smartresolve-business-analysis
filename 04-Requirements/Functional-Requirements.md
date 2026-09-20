# CarePath Functional Requirements

## Purpose

This document defines what the proposed CarePath solution must do when
implemented through Smart Agile Hub. Requirements are grouped by agent and
retain human control over all clinical decisions.

## Priority Scale

- **Must:** Required for the minimum viable product.
- **Should:** Important but may follow the initial release.
- **Could:** Useful enhancement after the core workflow is stable.

## Digital Intake Agent

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-001 | The solution must capture referrals through a standard digital form using synthetic data in the prototype. | Must | Submit a valid synthetic referral and confirm a record is created |
| FR-002 | The solution must generate a unique referral identifier for every submission. | Must | Submit two referrals and verify different identifiers |
| FR-003 | The solution must record the submission date, time and source. | Must | Inspect the created referral and audit record |
| FR-004 | The solution should flag possible duplicate referrals for human review without automatically deleting or merging them. | Should | Submit matching test records and verify a review flag |

## Validation Agent

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-005 | The solution must check configured mandatory administrative fields and required documents. | Must | Omit a required field and verify validation fails |
| FR-006 | The solution must identify which mandatory items are missing. | Must | Confirm the missing-item list matches the test referral |
| FR-007 | The solution must set an incomplete referral to `Information Required`. | Must | Validate an incomplete referral and inspect its status |
| FR-008 | The solution must revalidate a referral after additional information is supplied. | Must | Update the referral and verify validation reruns |
| FR-009 | The solution must prevent an administratively incomplete referral from proceeding to routing unless an authorised user records an approved exception. | Must | Attempt to route an incomplete referral |

## Routing Agent

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-010 | The solution must recommend an administrative specialty route using approved routing rules. | Must | Run test referrals with known rule outcomes |
| FR-011 | The solution must display the recommendation as advice rather than a confirmed clinical decision. | Must | Inspect the recommendation label and workflow state |
| FR-012 | An administration officer must be able to confirm or correct the recommended route. | Must | Test both confirmation and correction paths |
| FR-013 | The solution must record the confirmed route, original recommendation, actor, timestamp and correction reason. | Must | Correct a route and inspect the audit record |
| FR-014 | Unsupported or ambiguous referrals must be placed in a manual-review queue. | Must | Submit an unmatched test referral |

## Human Clinical Review and Workflow Agent

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-015 | The solution must create a clinical-review task after administrative routing is confirmed. | Must | Confirm a route and verify task creation |
| FR-016 | Only authorised clinical users must be able to record suitability, urgency, acceptance, return, redirect or decline decisions. | Must | Test role permissions with authorised and unauthorised users |
| FR-017 | The solution must not independently diagnose, recommend treatment or determine final clinical priority. | Must | Review agent instructions, permissions and test outcomes |
| FR-018 | The solution must require a reason when a referral is returned, redirected, declined, cancelled or closed. | Must | Attempt each outcome without a reason |
| FR-019 | The solution must create an appointment-booking task only after an authorised clinical acceptance. | Must | Compare accepted and non-accepted referral paths |
| FR-020 | A scheduling officer must be able to record appointment details or a no-availability exception. | Must | Test booking and no-availability paths |

## Notification Agent

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-021 | The solution must prepare approved draft notifications for missing information, referral outcomes and appointment details. | Must | Trigger each event and inspect the draft |
| FR-022 | The solution must not include unnecessary clinical information in notification content. | Must | Review generated drafts against the data-minimisation rule |
| FR-023 | The solution must record notification status, timestamp and failure reason. | Must | Simulate successful and failed notification outcomes |
| FR-024 | A failed notification must create a staff follow-up task. | Should | Simulate delivery failure and verify task creation |

## Audit and Reporting Agents

| ID | Requirement | Priority | Verification |
|---|---|---|---|
| FR-025 | The solution must record every material status change with referral ID, previous status, new status, actor, timestamp and reason where applicable. | Must | Execute the end-to-end workflow and inspect audit history |
| FR-026 | Authorised users must be able to view the current referral status and chronological history. | Must | Open a test referral as an authorised user |
| FR-027 | The solution must provide standardised operational data for Power BI reporting. | Must | Compare the reporting dataset with the defined schema |
| FR-028 | The reporting dataset must support volumes, completeness, processing time, queue age, routing corrections, waiting time and notification outcomes. | Must | Validate the required measures against synthetic records |
| FR-029 | The solution should support filtering by date, specialty, status and service queue. | Should | Test all required report filters |
| FR-030 | The solution should provide an export of approved non-sensitive operational results. | Could | Export a test report using an authorised role |

## Traceability to Smart Agile Hub Agents

| Agent | Functional Requirements |
|---|---|
| Digital Intake Agent | FR-001 to FR-004 |
| Validation Agent | FR-005 to FR-009 |
| Routing Agent | FR-010 to FR-014 |
| Workflow Agent and Human Clinical Review | FR-015 to FR-020 |
| Notification Agent | FR-021 to FR-024 |
| Audit Agent | FR-025 to FR-026 |
| Reporting Agent | FR-027 to FR-030 |

