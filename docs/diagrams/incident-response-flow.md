# Incident Investigation and Response Flow

```mermaid
flowchart TD
    A[Alert or Incident] --> B[Triage and Normalize Evidence]
    B --> C[Correlate SIEM Identity Endpoint Context]
    C --> D[MITRE Mapping and Risk Scoring]
    D --> E[Knowledge Context]
    E --> F[AI Recommendation]
    F --> G[Deterministic Policy Classification]
    G --> H{Impact level}
    H -- Read or Low --> I[Execution Gateway Controls]
    H -- Medium or High --> J[Human Approval]
    J --> I
    I --> K[Execute or Simulate]
    K --> L[Validate Result]
    L --> M[Audit Evidence]
    L --> N{Rollback needed and supported?}
    N -- Yes --> O[Governed Rollback]
    O --> M
    N -- No --> M
```

AI recommendations are advisory. State-changing actions remain subject to deterministic policy, role authorization, approval requirements, and the execution gateway.
