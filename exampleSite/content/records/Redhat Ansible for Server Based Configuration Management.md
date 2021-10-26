---
title: Redhat Ansible for server based Configuration Management
categories: ['Configuration Management']  
domain: Configuration
ownership: Apps & Tools
status: Active
stack: Applications & Tooling
type: Decision
tags: ['#iac','#devops','#dsc','#coding'] 
date: 2021-10-24T11:01:10+01:00
draft: false
image: "images/configman.jpg"
---

#### Decision
Redhat Ansible is our preferred tool for server automation of server based configuration management.

----
#### Context
On the provisioning of infrastructure, using Infrastructure as Code (IaC) ideally, the next step is to configure the application stack and its dependencies, using a Desired State approach.

The tool must

- be capable of managing desired state and be idempotent
- be operating system independent
- be agent-less (primary use case)
- be configuration based (declarative) ideally

#### Rationale
Ansible meets most of the known tasks we need to do today and probably tomorrow. It is actively developed and maintained, open source, with a large community and ecosystem. It is commercially backed, if support agreements are required.

It is yaml based, so in theory, a lower barrier to entry than 'pure' code. It also works with Powershell Desired State Configuration if needed.

The initial adoption feedback says usage and uptake is positive.

#### Caveats
Inventory management is using static yaml files (in the main) and are outside a central management system for easy retrieval, grouping and filtering. This makes inventory much harder to manage.

Job output is in a proprietary almost json like format, making it hard integrate or view results in an easy digestible way that both a computer and human can understand without conversion tooling.

Pulumi may well win in the future, but as we are not targeting 'preferred software language' engineers, it was felt that declrative (using yaml) was a lower barrier to entry.
