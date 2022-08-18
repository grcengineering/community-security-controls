# Just-in-time-access (JITA) for local admin privileges
**ID:** IAM.PAM.1

## Description
Attackers 

## Threat Model
```mermaid
graph LR
    A[Attacker] -->|malware| B((Operating System))
    A[Attacker] -->|remote login| B((Operating System))
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```

## Tools

|Tool|Compatible Systems|Description|
|-|-|-|
|[Privileges](https://github.com/SAP/macOS-enterprise-privileges)|macOS|Stuff|
|[MakeMeAdmin](https://github.com/pseymour/MakeMeAdmin)|Windows|Stuff|

## Processes
```mermaid
graph TD
    A[User] -->|request JITA| B((Operating System))
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```
