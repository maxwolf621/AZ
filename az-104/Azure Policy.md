{%hackmd @Edixon/dracula %}
# Azure Policy

[TOC]

Azure Policy enforces Organizational Standards and to assess compliance at-scale
> Policies DO NOT RESTRICT access, THEY ONLY OBSERVE for compliance

Policy Definitions
- A policy definition is a JSON file used to describe business rules(condition) to control access to resources.

Policy Assignment
- The scope of a policy can effect. 
- Assigned to a user, a resource group or management group.

Policy Parameters
- Values you can pass into your Policy definition so your Policies are more flexible for re-use.

Initiative Definitions
- An initiative definition is a collection of policy definitions, that you can assign. e.g. A group of policies to enforce PCI-DSS compliance

## Cheatsheet 

Policies do not restrict access, they only observe for compliance.  
Once a policy is assigned it will evaluate for the compliance state periodically.  
The rules of a policy are describe in a JSON file and is known as a policy definition.  
Policy definition can be grouped together which is known as a policy initiative (formally known as a policy set)  

---
{%youtube 9WO4EBgUJXk %}