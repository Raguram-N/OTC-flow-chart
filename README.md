```mermaid
flowchart LR
    %% Node Definitions
    Start([<b>Upload PDF]):::blue
    Run[<b>Run]:::blue
    Decisions{<b>Audit Result</b>}:::logic
    
    Pass(<b>APPROVE</b>):::green
    Negotiate(<b>MARK UP</b>):::yellow
    Legal(<b>ESCALATE</b>):::red
    
    End([<b>ARCHIVE</b>]):::blue

    %% Connections
    Start --> Run
    Run --> Decisions
    
    Decisions ---->|Success| Pass
    Decisions ---->|Review| Negotiate
    Decisions ---->|Critical| Legal
    
    Pass --> End
    Negotiate --> End
    Legal --> End

    %% Styling
    classDef blue fill:#f0f9ff,stroke:#0369a1,stroke-width:2px,color:#0369a1
    classDef logic fill:#fff,stroke:#334155,stroke-width:2px
    classDef green fill:#f0fdf4,stroke:#166534,stroke-width:2px,color:#166534
    classDef yellow fill:#fffbeb,stroke:#92400e,stroke-width:2px,color:#92400e
    classDef red fill:#fef2f2,stroke:#991b1b,stroke-width:2px,color:#991b1b
