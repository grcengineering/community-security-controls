# Just-in-time-access (JITA) for endpoint administrator account privileges
**ID:** IAM.PAM.1

## Description
When targeting user or server endpoints, attackers will attempt to compromise an account with administrator privileges to more easily establish persistent access to the compromised endpoint and/or to gain access to sensitive data only accessible to privileged accounts (e.g. credentials stored in memory).

Implementing JITA for endpoint administrator account privileges requires an authorized user to intentionally request admin privileges before using them. After a set period of time, the user's privileges are downgraded.

An attacker that is unaware of this JITA control being present will have a harder time trying to obtain and use endpoint admin privileges. This can make it easier to detect an attacker who fails 

## Threat Model
```mermaid
flowchart LR
    ac(Admin Account)
    at(Attacker)
    m(Malware)
    p(Process)
    pd(Protected Data)

    at -->|1.1 delivers|m
    at -->|2.1 remotely logs in with stolen credentials|ac
    at -->|3.2 vulnerability exploitation|p

    subgraph ide1 [Endpoint]
        ac-->|1.2 launches|m
        ac-->|2.2 launches|p
        ac-->|3.1 launches|p
        p-->pd
        m-->pd
    end

    style at fill:#ff7676,stroke:#940000,stroke-width:2px,color:#000000

    style m fill:#ff7676,stroke:#940000,stroke-width:2px,color:#000000

    style ac fill:#f9ebb9,stroke:#fb9400,stroke-width:2px,color:#000000

    style pd fill:#9bb8ff,stroke:#0035b3,stroke-width:2px,color:#000000
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
