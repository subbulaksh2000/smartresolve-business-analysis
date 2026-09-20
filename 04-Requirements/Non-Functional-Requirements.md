# CarePath Non-Functional Requirements

## Purpose

This document defines the quality, safety, security and operational conditions
for the CarePath Smart Agile Hub implementation. Values are proposed targets for
the fictional prototype and would require stakeholder validation before a real
healthcare implementation.

| ID | Category | Requirement | Proposed Measure | Priority |
|---|---|---|---|---|
| NFR-001 | Privacy | The prototype must use synthetic referral and patient information only. | No real patient records appear in test data, logs, screenshots or reports | Must |
| NFR-002 | Data minimisation | Each agent must access and retain only the fields required for its approved activity. | Data-field and agent-access matrix reviewed before release | Must |
| NFR-003 | Access control | Access must be role-based for referrers, administration officers, clinical reviewers, schedulers, managers and system administrators. | Permission tests pass for every role and restricted action | Must |
| NFR-004 | Clinical safety | Smart Agile Hub must not diagnose, recommend treatment or make final clinical-priority decisions. | No autonomous clinical-decision path exists in configuration or testing | Must |
| NFR-005 | Human oversight | Clinical outcomes and corrected routing decisions must identify the authorised human decision-maker. | Actor and timestamp are present for 100% of controlled decisions | Must |
| NFR-006 | Auditability | Material actions and status changes must be recorded in an append-only audit history for the prototype. | Every tested material event produces one traceable audit entry | Must |
| NFR-007 | Explainability | Administrative routing recommendations must show the approved rule or reason supporting the recommendation. | Reason is visible for 100% of test recommendations | Must |
| NFR-008 | Reliability | The workflow must prevent duplicate processing when the same event is retried. | Replaying an event does not create a duplicate task or audit result | Must |
| NFR-009 | Performance | Standard validation and routing responses should complete within five seconds in the prototype under normal test load. | 95% of test transactions meet the target | Should |
| NFR-010 | Availability | The prototype should be available during agreed demonstration and testing windows. | No unplanned outage during the manager demonstration | Should |
| NFR-011 | Recoverability | Failed agent actions must be logged and placed in a recoverable review queue. | Failed test actions can be identified and safely retried | Must |
| NFR-012 | Usability | Core referral statuses, assigned owner and next action must be understandable without technical knowledge. | Representative users complete agreed tasks without facilitator correction | Should |
| NFR-013 | Accessibility | User-facing prototype screens should follow WCAG 2.1 AA principles where supported. | Keyboard, label, contrast and text-scaling checks completed | Should |
| NFR-014 | Interoperability | Data exchange must use documented field names, status values and standard date-time formats. | Schema validation passes for intake, workflow and reporting records | Must |
| NFR-015 | Maintainability | Business rules, templates and status mappings must be configuration-controlled and documented. | Approved changes can be traced to a version and decision record | Must |
| NFR-016 | Observability | Agent execution, failure, retry and human override events must be monitorable. | Operations view displays test executions and failures | Should |
| NFR-017 | Reporting freshness | Operational data should be available to Power BI within the agreed prototype refresh interval. | Refresh completes within 30 minutes of the scheduled run | Should |
| NFR-018 | Retention | Prototype retention and deletion periods must be documented and configurable. | Approved retention rule is recorded and test data can be removed | Must |
| NFR-019 | Security | Secrets, credentials and access tokens must not be stored in source code or public GitHub files. | Repository scan finds no exposed secrets | Must |
| NFR-020 | Change governance | Agent instructions, rules and templates must be reviewed and approved before release. | Each released version has an owner, reviewer and change record | Must |

## Assumptions Requiring Manager Confirmation

- The prototype will continue to use synthetic data only.
- Smart Agile Hub will provide role controls, audit logging and agent
  configuration suitable for the demonstration.
- Power BI will consume a standardised reporting dataset rather than direct
  clinical notes.
- The five-second response and 30-minute reporting targets are demonstration
  targets, not confirmed production service levels.
- Data residency, production retention and healthcare compliance requirements
  are outside the prototype and require formal review before real deployment.

