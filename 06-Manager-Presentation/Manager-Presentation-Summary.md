# CarePath Smart Agile Hub — Manager Presentation Summary

## Slide 1 — CarePath Project Overview

**Key points**

- AI-assisted outpatient referral-management concept.
- Fictional BrightCare Health case study using synthetic data only.
- Proposed implementation platform: Smart Agile Hub.
- Objective: improve completeness, routing, visibility, auditability and
  operational reporting.

**Talk track**

CarePath addresses administrative friction in the outpatient referral journey.
The concept uses Smart Agile Hub agents to support repetitive administrative
work while keeping all clinical decisions with authorised healthcare staff.

## Slide 2 — Current AS-IS Challenges

**Key points**

- Referrals arrive through inconsistent forms, emails and scanned documents.
- Staff manually record and validate referral information.
- Missing information creates repeated follow-up.
- Routing, status tracking and reporting are inconsistent.
- Clinical time may be consumed by administrative issues.

**Talk track**

The AS-IS process is deliberately documented without Smart Agile Hub because it
represents today's manual workflow. This gives us a credible baseline for
measuring the proposed improvement.

## Slide 3 — Proposed TO-BE Process

**Key points**

- Standard digital referral submission.
- Automated administrative completeness validation.
- Explainable specialty-routing recommendation.
- Human confirmation and clinical-review gates.
- Appointment-task creation, draft notifications and audit history.
- Power BI operational reporting.

**Talk track**

The TO-BE model removes avoidable administrative hand-offs but does not automate
clinical judgement. Recommendations and confirmed decisions remain visibly
separate.

## Slide 4 — Smart Agile Hub Agent Model

| Agent | Responsibility |
|---|---|
| Digital Intake Agent | Creates a standard, traceable referral record |
| Validation Agent | Checks mandatory fields and documents |
| Routing Agent | Recommends an administrative specialty route |
| Workflow Agent | Creates review, follow-up and booking tasks |
| Notification Agent | Prepares approved draft communications |
| Audit Agent | Records status changes, actors, reasons and timestamps |
| Reporting Agent | Prepares standardised operational data for Power BI |

**Talk track**

Each agent has one clear responsibility. This modular design makes the workflow
easier to test, govern and improve without giving one agent broad authority.

## Slide 5 — Human-Controlled Clinical Decisions

**Key points**

- Smart Agile Hub cannot diagnose or recommend treatment.
- It cannot decide final clinical priority.
- Administration officers confirm routing.
- Authorised clinicians accept, return, redirect or decline referrals.
- Scheduling officers select appointments.
- Overrides and reasons are audited.

**Talk track**

The design treats AI as administrative decision support. Human authority is a
functional requirement, a non-functional safety control and an acceptance
criterion in the backlog.

## Slide 6 — Requirements and Backlog

**Key points**

- 30 functional requirements mapped to seven agents.
- 20 non-functional requirements covering privacy, security, safety,
  reliability, performance and governance.
- Seven epics and 15 prioritised user stories.
- Given/When/Then-style acceptance criteria.
- Five proposed MVP sprints.

**Talk track**

The backlog provides traceability from the pain points through the TO-BE process
to requirements, agents, stories and tests. It is ready for manager review and
later configuration planning.

## Slide 7 — MVP Delivery Plan

| Sprint | Outcome |
|---|---|
| 1 | Digital intake and audit foundation |
| 2 | Completeness validation and follow-up |
| 3 | Administrative routing and human confirmation |
| 4 | Clinical hand-off and appointment workflow |
| 5 | Notifications, responsible AI controls and reporting |

**Talk track**

The MVP is sequenced by dependency. We first establish the referral record and
audit trail, then add validation, routing, workflow and reporting capabilities.

## Slide 8 — Measures of Success

**Key points**

- First-time referral completeness.
- Average validation time.
- Routing-recommendation correction rate.
- Time awaiting clinical review.
- Time from acceptance to appointment booking.
- Referral backlog volume and age.
- Notification success and failure rate.
- Human override rate.

**Talk track**

These measures show whether CarePath reduces rework and increases visibility.
They also monitor whether agent recommendations require frequent correction.

## Slide 9 — Risks and Controls

| Risk | Control |
|---|---|
| Clinical overreach | Agents have no clinical-decision permissions |
| Incorrect routing | Human confirmation and correction reason |
| Missing or duplicated processing | Validation rules and idempotent event handling |
| Privacy exposure | Synthetic data, minimum fields and role access |
| Untraceable changes | Version control and append-only audit history |
| Communication failure | Failure log and staff follow-up task |

## Slide 10 — Manager Decisions Requested

**Confirm or approve:**

1. Smart Agile Hub as the proposed prototype platform.
2. The seven-agent responsibility model.
3. Synthetic data only for the portfolio prototype.
4. Human confirmation for administrative routing.
5. Human-only clinical decisions and priority.
6. The five-sprint MVP sequence.
7. Power BI as the reporting layer.
8. The proposed functional and non-functional requirement baseline.

**Closing message**

CarePath uses Smart Agile Hub to simplify administrative referral work, improve
traceability and support operational insight, while preserving clear human
ownership of every clinical decision.

