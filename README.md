# Introduction to Ansible

## What is Ansible?

**Ansible** is an open-source automation tool that simplifies IT operations by automating tasks such as configuration management, application deployment, and task orchestration. It allows you to define automation tasks using simple, human-readable YAML files known as playbooks.

## Key Features

- Agentless: Ansible operates over SSH or WinRM, eliminating the need to install agents on remote machines.
- Declarative: You define the desired state, and Ansible ensures that the system matches that state.
- Idempotent: Ansible tasks can be run multiple times without causing unintended side effects.
- Extensible: Ansible supports custom modules, roles, and plugins for flexibility.

## Installation on Linux

To install Ansible on a Linux-based system, follow these steps:

1. **Update Package List**: Ensure your package list is up-to-date.

```
   sudo apt update  
   sudo apt install ansible

```

