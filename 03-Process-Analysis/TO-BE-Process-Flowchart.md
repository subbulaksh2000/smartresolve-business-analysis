# CarePath TO-BE Process Flowchart

## Purpose

This flowchart presents the proposed CarePath outpatient referral process and
identifies the activities that can later be implemented through Smart Agile
Hub. All clinical decisions remain with authorised healthcare professionals.

```mermaid
flowchart TD
    A([Referral submitted]) --> B[Digital Intake Agent<br/>creates referral record]
    B --> C[Validation Agent<br/>checks required information]
    C --> D{Referral complete?}

    D -- No --> E[Set status:<br/>Information Required]
    E --> F[Notification Agent<br/>prepares follow-up draft]
    F --> G[Administration officer<br/>reviews follow-up]
    G --> H[Referrer supplies<br/>missing information]
    H --> C

    D -- Yes --> I[Routing Agent<br/>recommends specialty]
    I --> J{Administration officer<br/>confirms route?}
    J -- No --> K[Correct route and<br/>record reason]
    J -- Yes --> L[Send to clinical-review queue]
    K --> L

    L --> M[Authorised clinician<br/>reviews referral]
    M --> N{Human clinical decision}

    N -- Return --> O[Request further<br/>clinical information]
    O --> M

    N -- Redirect --> P[Assign approved<br/>alternative service]
    P --> L

    N -- Decline --> Q[Record authorised<br/>reason]
    Q --> R[Notification Agent<br/>prepares outcome draft]

    N -- Accept --> S[Clinician records<br/>priority and acceptance]
    S --> T[Workflow Agent creates<br/>appointment-booking task]
    T --> U[Scheduling officer<br/>books appointment]
    U --> V[Notification Agent prepares<br/>appointment draft]

    R --> W[Audit Agent records<br/>status and activity]
    V --> W
    W --> X[Reporting dataset<br/>is updated]
    X --> Y([Power BI operational dashboard])

    classDef startEnd fill:#17365d,color:#ffffff,stroke:#17365d,stroke-width:2px;
    classDef agent fill:#dbeafe,color:#172554,stroke:#2563eb,stroke-width:1.5px;
    classDef human fill:#dcfce7,color:#14532d,stroke:#16a34a,stroke-width:1.5px;
    classDef decision fill:#fef3c7,color:#78350f,stroke:#d97706,stroke-width:1.5px;
    classDef exception fill:#fee2e2,color:#7f1d1d,stroke:#dc2626,stroke-width:1.5px;
    classDef data fill:#f3e8ff,color:#581c87,stroke:#9333ea,stroke-width:1.5px;

    class A,Y startEnd;
    class B,C,F,I,R,T,V,W agent;
    class G,H,K,L,M,S,U human;
    class D,J,N decision;
    class E,O,P,Q exception;
    class X data;
```

## Flowchart Legend

| Colour | Meaning |
|---|---|
| Dark blue | Process start or final reporting output |
| Blue | Smart Agile Hub agent or automated workflow activity |
| Green | Human-controlled activity |
| Amber | Decision point |
| Red | Exception or alternative outcome |
| Purple | Reporting data activity |

## Human-Control Points

The following activities cannot be completed autonomously by Smart Agile Hub:

- Confirming or correcting the administrative route.
- Determining clinical suitability and urgency.
- Accepting, redirecting, returning or declining a referral.
- Selecting the final appointment.
- Approving communications where human review is required.

## Smart Agile Hub Agent Mapping

| Proposed Agent | Trigger | Main Responsibility | Human Control |
|---|---|---|---|
| Digital Intake Agent | New referral submission | Create the referral record, identifier and submission timestamp | Administration staff can review or correct captured information |
| Validation Agent | Referral created or updated | Check mandatory fields and supporting documents | Administration staff confirm exceptions and follow-up requirements |
| Routing Agent | Administrative validation completed | Recommend a specialty using approved administrative rules | Administration officer confirms or corrects the route |
| Workflow Agent | Authorised clinical decision recorded | Create the appropriate booking, follow-up or closure task | Clinical and scheduling staff retain decision ownership |
| Notification Agent | Information request, outcome or appointment event | Prepare an approved draft notification | Staff review when required before sending |
| Audit Agent | Material action or status change | Record actor, timestamp, old status, new status and reason | Audit records remain available for authorised review |
| Reporting Agent | Scheduled refresh or material update | Prepare operational data for Power BI | Operations manager interprets and acts on reports |

## Implementation Boundary

Smart Agile Hub supports the administrative workflow. It does not diagnose,
recommend treatment, make autonomous clinical-priority decisions or replace an
authorised clinical reviewer.

