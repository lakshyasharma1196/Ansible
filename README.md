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

## Importtant topics

# Inventory

An inventory is a list of target hosts or nodes on which Ansible will perform automation tasks. It defines the machines or servers that Ansible should manage or interact with. The inventory can be a simple text file, an INI file, or even a dynamic inventory script that generates the list of hosts dynamically.

# Useful Parameters for Inventory File

```
   ansible_host

   ansible_connection

   ansible_port

   ansible_user

   ansible_ssh_pass    # for connecting Linux based OS

   ansible_password    # for connecting windows

   ```

## Playbooks

Playbook is a YAML file that defines a set of automation tasks to be executed on remote hosts. It serves as a high-level orchestration script for Ansible, specifying what should be done on target systems.

```
---
- name: play1
  hosts: localhost #target_group
  become: yes  # Optionally, if tasks require privilege escalation
  tasks:
    - name: Task 1
      <module_name>:
        <module_parameters>
      # Optionally, add conditionals, loops, or other task options here

---
- name: play2
  hosts: node01 #target_group
  become: yes  # Optionally, if tasks require privilege escalation
  tasks:
    - name: Task 1
      <module_name>:
        <module_parameters>
      # Optionally, add conditionals, loops, or other task options here

```

## 'name' 

A descriptive name for the playbook. This is for documentation purposes and helps identify the playbook's purpose.

## 'hosts'

Specifies the target hosts or groups of hosts on which the playbook tasks will be executed. You can use host patterns, such as specific hostnames or group names defined in the inventory.

## Play

Play is a section within a playbook that groups related tasks together. It defines a set of actions to be taken on a specific group of hosts. Plays are executed sequentially.

## Task
A task is a single unit of work within a play. It represents a specific action or command to be executed on remote hosts. Tasks are defined in a YAML format and can include details like the module to use, module parameters, and conditionals.

## Module

A module is a reusable and self-contained piece of code in Ansible that performs specific tasks on remote hosts. Modules can manage system components, install software, configure settings, and more. They are used within tasks to achieve various automation goals.


## Playbook Execution Syntax:

```
ansible-playbook -i inventory playbook.yaml

ansible-playbook -i inventory playbook.yaml --check  # Check Mode
```
## Note

Ansible should be install in a master mode called ansible-controller, From this node all traget nodes should be connected using ssh to run the playbook commands. We will provide the traget nodes information on inventory file.




