# Just-in-time-access (JITA) for endpoint administrator account privileges
**ID:** IAM.PAM.1

## Threat Overview
When targeting user or server endpoints, attackers will attempt to compromise an account with administrator privileges to more easily establish persistent access to the compromised endpoint and to gain access to sensitive data only accessible to privileged accounts (e.g. credentials stored in memory, which can be used to connect to other apps or systems).

## Threat Model
```mermaid
flowchart LR
    aa(Admin Account)
    at(Attacker)
    m(Malware)
    p(Process)
    pd(Protected Data)

    at -->|a.1 delivers|m
    at -->|b.1 remotely logs in with stolen credentials|aa
    at -->|c.2 vulnerability exploitation|p

    subgraph ide1 [Endpoint]
        aa-->|a.2 launches|m
        aa-->|b.2 launches|p
        aa-->|c.1 launches|p
        p-->pd
        m-->pd
    end

    style at fill:#ff7676,stroke:#940000,stroke-width:2px,color:#000000

    style m fill:#ff7676,stroke:#940000,stroke-width:2px,color:#000000

    style aa fill:#f9ebb9,stroke:#fb9400,stroke-width:2px,color:#000000

    style pd fill:#9bb8ff,stroke:#0035b3,stroke-width:2px,color:#000000
```

## Control Context
Implementing JITA for local admin access requires a user to intentionally request admin privileges before using them. After a set period of time, the user's privileges are downgraded. 

This control is most beneficial for organizations that have a valid reason to provide some users with local admin access on their computers. By making local admin access temporary and only granted upon request, this control helps minimize the impact of an attacker exploiting vulnerable software, moving laterally with stolen credentials, or tricking users into executing malicious code on their endpoint.

## Control Model
 ```mermaid
flowchart LR
    u(User)
    j(JITA Request Tool)
    s[(SIEM)]
    t((Timer))

    u-->|1. submits local admin access request|j
    j-->|2. log request|s
    j-.->|3 start|t
    j---->|4 provide local admin|u    
    t-.->|5 end|j
    j-->|6 revoke local admin|u

    style j fill:#9ecea2,stroke:#015407,stroke-width:2px,color:#000000
```

## Control Tools
|Tool|Compatible Systems|
|-|-|
|[Privileges](https://github.com/SAP/macOS-enterprise-privileges)|macOS|
|[MakeMeAdmin](https://github.com/pseymour/MakeMeAdmin)|Windows|

## Control Framework Mappings
|Framework|Control ID(s)|
|-|-|
|SOX||
|SOC 2|CC6.1, CC6.2|
|ISO 27001||
|NIST CSF 1.1||
|NIST CSF 2||
|NIST 800-53 Rev. 5|AC-6(2)|
|FedRAMP||
|PCI DSS||
|HIPAA||
|GDPR||
|CCPA||
|CIS CSC v8|5.4|

## References
* [Apple @ Work: Privileges for macOS is the open source tool that all Apple IT departments need](https://9to5mac.com/2019/11/16/privileges-app-for-macos/)
