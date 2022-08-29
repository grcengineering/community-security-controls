# Community Security Controls Framework

## Problem
For decades now, information security practitioners have been playing a constant game of cat-and-mouse with threat actors. Throughout that time, one thing has held true: attackers often outpace defenders. They have the advantage of needing to only be right once while defenders need to be right 100% of the time with their defensive techniques.

The security community has attempted to address this core concern by producing controls frameworks (e.g. SOC 2, NIST CSF, CIS Critical Security Controls, ISO 27001, etc.) that provide best practices as a sort of "shared foundation" for all organizations to build their security programs on. By implementing these best practices, organizations will be able to better defend against well known threats.

Unfortunately, this hasn't panned out as intended due to the following problems:
* Updates to existing controls frameworks significantly lag a rapidly changing threat landscape, with years passing between framework updates
* Control frameworks provide abstract concepts and principles for organizations to abide by without any detailed or prescriptive best practice recommendations, resulting in organizations spending excessive time reinventing wheels and exploring a market that is hypersatured with security tools and services
* Controls frameworks are gatekept by organizations such as CIS, NIST, ISO, AICPA, etc. This limits the number of minds, and thus the number of useful ideas, contributing to the collection of best practice controls that constitute a framework
  * Some organizations allow for community input; however, these input processes are difficult to access, typically using proprietary community portals/websites or cumbersome email-based RFC processes

## Solution: Community Security Controls Framework (CSCF)
CSCF is an open source repository of community-maintained information security controls. It contains controls mapped to other frameworks as well as community best practices that don't map clearly to existing control frameworks. It is intended to solve the aforementioned problems by:
* Allowing for rapid, incremental, and granular framework updates on a per-control basis, as opposed to holistic framework updates that take years to complete
* Providing concise, detailed, and prescriptive recommendations on what best practice tools and processes to use to implement controls (biased toward free and open source tools whenever possible)
* Making it easier for anyone in the security community to propose changes to the framework, recommend new controls, etc. by using a public GitHub repository as the source of truth for framework content and revisions

It also contains additional detail that other controls frameworks typically don't, such as:

* Recommended tools for implementing said controls
* Best practice process flows (control models)
* Threats that the control is meant to protect against (threat models) to help better inform control implementations that aren't based purely on hypothetical or irrelevant threat scenarios
