## 📌 Exercise Overview

This exercise focuses on Ansible Roles, which are a way to organize and reuse automation code.
Roles break down complex playbooks into modular, reusable, and structured components.

By the end of this exercise, you will:

Understand the purpose of roles in Ansible.

Learn the standard directory structure of a role.

Create and use roles in playbooks.

Reuse roles across multiple projects for better maintainability.

## 📂 Role Directory Structure

Each role follows a predefined standard structure:

```bash

roles/
  └── <role_name>/
      ├── tasks/          # Main list of tasks to be executed
      │   └── main.yml
      ├── handlers/       # Handlers triggered by tasks
      │   └── main.yml
      ├── templates/      # Jinja2 templates (e.g., configs)
      │   └── file.conf.j2
      ├── files/          # Static files to be copied
      ├── vars/           # Variables with higher precedence
      │   └── main.yml
      ├── defaults/       # Default variables (lowest precedence)
      │   └── main.yml
      ├── meta/           # Role metadata (dependencies, author info)
      │   └── main.yml
      └── README.md       # Documentation about the role


```

## ▶️ Using Roles in a Playbook

Once you have a role created, you can use it in a playbook:

- hosts: all
  become: yes
  roles:
  - ntp
  - users

## ✅ Benefits of Roles

Better organization of playbooks.

Code reusability across different projects.

Easier collaboration among team members.

Standardized structure makes projects more maintainable.
