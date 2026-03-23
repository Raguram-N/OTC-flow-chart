```mermaid
flowchart TD
    A[Start] --> B[Login to OTC Tool]
    B --> C[Upload Document]
    C --> D[Run Check]
    D --> E{Are Issues Flagged?}
    E -->|Yes| F[Review Issues]
    F --> G[Escalate to Compliance]
    G --> H[Reject]
    E -->|No| K[Approve]
    H --> I[Archive Document]
    K --> I[Archive Document]
    I --> J[End]
  
