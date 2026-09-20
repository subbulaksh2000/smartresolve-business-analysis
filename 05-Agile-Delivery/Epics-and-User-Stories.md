# CarePath Epics and User Stories

## Purpose

This backlog translates the CarePath requirements into manager-reviewable epics
and user stories for a Smart Agile Hub implementation. The proposed MVP uses
synthetic data and preserves human-controlled clinical decisions.

## Epic Summary

| Epic ID | Epic | Business Outcome | Smart Agile Hub Component | MVP |
|---|---|---|---|---|
| EP-01 | Digital Referral Intake | Standardised referral capture and traceability | Digital Intake Agent | Yes |
| EP-02 | Completeness Validation | Fewer incomplete referrals and less rework | Validation Agent | Yes |
| EP-03 | Administrative Routing | Consistent, explainable specialty recommendations | Routing Agent | Yes |
| EP-04 | Human Clinical Review and Workflow | Safe hand-off to authorised clinical and scheduling staff | Workflow Agent | Yes |
| EP-05 | Notifications and Follow-up | Consistent draft communications and failure follow-up | Notification Agent | Yes |
| EP-06 | Audit, Governance and Responsible AI | Traceable actions, overrides and decisions | Audit Agent | Yes |
| EP-07 | Operational Reporting | Visibility of volumes, timeframes and backlog | Reporting Agent and Power BI | Yes |

## EP-01: Digital Referral Intake

### US-001 — Submit a standard referral

**As a** referring clinician, **I want** to submit a referral using a standard
digital form **so that** BrightCare Health receives consistent information.

**Priority:** Must  
**Requirements:** FR-001, FR-003; NFR-001, NFR-002

**Acceptance criteria**

- Given the required fields are complete, when the referral is submitted, then
  a referral record is created.
- Given a required field is missing, when submission is attempted, then the
  missing field is identified.
- The prototype accepts synthetic information only.

### US-002 — Create a traceable referral identifier

**As a** referral administration officer, **I want** each referral to receive a
unique identifier **so that** I can track it throughout the process.

**Priority:** Must  
**Requirements:** FR-002, FR-025

**Acceptance criteria**

- Each submitted referral receives one unique identifier.
- The identifier remains unchanged through validation, review and scheduling.
- The submission time and source are recorded.

### US-003 — Flag a possible duplicate

**As a** referral administration officer, **I want** possible duplicate
referrals flagged **so that** I can review them without accidental deletion.

**Priority:** Should  
**Requirements:** FR-004; NFR-008

**Acceptance criteria**

- A possible duplicate is flagged for human review.
- The solution does not automatically merge or delete either record.

## EP-02: Completeness Validation

### US-004 — Validate administrative completeness

**As a** referral administration officer, **I want** mandatory information and
documents checked automatically **so that** incomplete referrals are identified
early.

**Priority:** Must  
**Requirements:** FR-005 to FR-009

**Acceptance criteria**

- The Validation Agent checks every configured mandatory item.
- An incomplete referral receives `Information Required` status.
- The missing-item list is visible to authorised administration staff.
- An incomplete referral cannot proceed without an approved exception.

### US-005 — Revalidate updated information

**As a** referring clinician, **I want** my updated referral to be rechecked
**so that** it can continue after missing information is supplied.

**Priority:** Must  
**Requirements:** FR-008

**Acceptance criteria**

- Updating an incomplete referral triggers revalidation.
- A complete updated referral moves to `Ready for Routing`.
- The update and status change are recorded in the audit history.

## EP-03: Administrative Routing

### US-006 — Recommend a specialty route

**As a** referral administration officer, **I want** Smart Agile Hub to
recommend an administrative specialty **so that** routing is more consistent.

**Priority:** Must  
**Requirements:** FR-010, FR-011, FR-014; NFR-007

**Acceptance criteria**

- The Routing Agent uses only approved administrative rules.
- The recommendation displays its supporting rule or reason.
- The recommendation is labelled as advice requiring human confirmation.
- Unsupported or ambiguous referrals enter a manual-review queue.

### US-007 — Confirm or correct the route

**As a** referral administration officer, **I want** to confirm or correct a
routing recommendation **so that** responsibility remains with an authorised
person.

**Priority:** Must  
**Requirements:** FR-012, FR-013; NFR-005

**Acceptance criteria**

- The officer can confirm the recommended route.
- The officer can select a different approved route.
- A correction requires a reason.
- The recommendation, decision, actor and timestamp are retained.

## EP-04: Human Clinical Review and Workflow

### US-008 — Create a clinical-review task

**As a** clinical reviewer, **I want** validated referrals placed in the correct
review queue **so that** I can make an authorised clinical decision.

**Priority:** Must  
**Requirements:** FR-015, FR-016

**Acceptance criteria**

- A task is created only after administrative routing is confirmed.
- Only authorised clinical users can record a clinical outcome.
- The task displays the referral identifier, confirmed route and required
  supporting information.

### US-009 — Record a clinical outcome

**As an** authorised clinical reviewer, **I want** to accept, return, redirect
or decline a referral **so that** the correct next action is initiated.

**Priority:** Must  
**Requirements:** FR-016 to FR-018; NFR-004, NFR-005

**Acceptance criteria**

- The clinical reviewer selects the outcome and, where applicable, priority.
- Return, redirect and decline outcomes require a reason.
- Smart Agile Hub cannot select or submit the final clinical outcome.
- The decision, reviewer and timestamp are audited.

### US-010 — Create an appointment-booking task

**As an** appointment scheduling officer, **I want** a booking task after an
accepted referral **so that** scheduling begins without manual hand-off.

**Priority:** Must  
**Requirements:** FR-019, FR-020

**Acceptance criteria**

- A booking task is created only for an accepted referral.
- The scheduler can record appointment details.
- If no appointment is available, the referral remains visible in the backlog.

## EP-05: Notifications and Follow-up

### US-011 — Prepare a missing-information draft

**As a** referral administration officer, **I want** a draft request for missing
information **so that** communication is consistent and reviewable.

**Priority:** Must  
**Requirements:** FR-021, FR-022

**Acceptance criteria**

- The draft lists only the approved missing items.
- The draft contains the referral identifier and no unnecessary clinical data.
- Staff can review the draft before communication when required.

### US-012 — Prepare outcome and appointment drafts

**As a** scheduling or administration officer, **I want** approved outcome and
appointment drafts **so that** stakeholders receive consistent information.

**Priority:** Must  
**Requirements:** FR-021 to FR-024

**Acceptance criteria**

- Draft content matches the authorised referral outcome.
- The notification outcome and timestamp are recorded.
- A failed notification creates a staff follow-up task.

## EP-06: Audit, Governance and Responsible AI

### US-013 — View an end-to-end audit history

**As a** privacy, compliance or operations user, **I want** a chronological
history **so that** actions and decisions can be traced.

**Priority:** Must  
**Requirements:** FR-025, FR-026; NFR-006

**Acceptance criteria**

- Each material event records referral ID, actor, timestamp and status change.
- Reasons are included for corrections and exception outcomes.
- Authorised users can view the history in chronological order.

### US-014 — Enforce responsible AI boundaries

**As a** privacy and compliance officer, **I want** clinical authority excluded
from agent permissions **so that** Smart Agile Hub remains an administrative
support tool.

**Priority:** Must  
**Requirements:** FR-017; NFR-004, NFR-020

**Acceptance criteria**

- No agent can diagnose, recommend treatment or determine final urgency.
- Agent recommendations are visibly separated from human decisions.
- Configuration changes require an owner, reviewer and version record.

## EP-07: Operational Reporting

### US-015 — Monitor referral performance

**As a** healthcare operations manager, **I want** a Power BI dashboard **so
that** I can monitor volumes, processing times, waiting times and backlogs.

**Priority:** Must  
**Requirements:** FR-027 to FR-029; NFR-017

**Acceptance criteria**

- The dashboard reports referral volumes by date, specialty and status.
- The dashboard reports completeness, validation time, queue age, routing
  corrections, waiting time and notification outcomes.
- Operational data is available within the approved refresh interval.
- Dashboard access follows the authorised role model.

## Proposed MVP Sequence

| Sprint | Focus | Stories |
|---|---|---|
| Sprint 1 | Digital intake and audit foundation | US-001, US-002, US-013 |
| Sprint 2 | Completeness validation and follow-up | US-004, US-005, US-011 |
| Sprint 3 | Administrative routing and human confirmation | US-006, US-007 |
| Sprint 4 | Clinical hand-off and appointment workflow | US-008, US-009, US-010 |
| Sprint 5 | Notifications, responsible AI and reporting | US-012, US-014, US-015 |

## Definition of Done

A story is complete when:

- Acceptance criteria pass using synthetic test data.
- Human-control boundaries are verified.
- Role permissions are tested.
- Required audit entries are produced.
- Failure and exception paths are tested.
- Relevant requirements and process steps are traceable.
- Documentation and demonstration evidence are updated.

