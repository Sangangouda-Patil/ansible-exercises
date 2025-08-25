# Ansible Exercises – My DevOps Learning Journey

This repository contains my **Ansible practice exercises** as part of my DevOps learning journey.  
Each exercise builds on the previous one, covering important Ansible concepts like **modules, variables, facts, templates, loops, and roles**.

---

## 📚 Table of Contents

1. [Copying Files with Ansible Modules](#1-copying-files-with-ansible-modules)
2. [Variable Precedence (`group_vars`, host vars, play vars)](#2-variable-precedence-group_vars-host-vars-play-vars)
3. [Gathering Facts](#3-gathering-facts)
4. [Using Facts with Conditions](#4-using-facts-with-conditions)
5. [Loops in Ansible](#5-loops-in-ansible)
6. [Templates with Jinja2](#6-templates-with-jinja2)
7. [Controlling Playbook Execution (tags, steps, start-at-task)](#7-controlling-playbook-execution-tags-steps-start-at-task)
8. [Ansible Roles](#8-ansible-roles)

---

## 1. Copying Files with Ansible Modules

- Used the **`copy` module** to transfer files from control node to managed nodes.
- First hands-on with Ansible tasks.

---

## 2. Variable Precedence (`group_vars`, host vars, play vars)

- Practiced **variable resolution** in Ansible.
- Checked how values are picked from:
  - `group_vars/all`
  - host vars
  - play vars

---

## 3. Gathering Facts

- Used Ansible’s **facts** to fetch system information:
  - OS type
  - SELinux status
  - RAM & CPU details

---

## 4. Using Facts with Conditions

- Combined **facts** with `when` conditions.
- Example: installing different packages depending on OS family.

---

## 5. Loops in Ansible

- Implemented **loops** to avoid repetitive tasks.
- Example: creating multiple users with a loop.

---

## 6. Templates with Jinja2

- Practiced **Jinja2 templates** with the `template` module.
- Used variables inside configuration files.

---

## 7. Controlling Playbook Execution (tags, steps, start-at-task)

- Explored **playbook execution control** with:
  - `--tags`
  - `--step`
  - `--start-at-task`

---

## 8. Ansible Roles

- Learned to **structure Ansible projects using roles**.
- Broke down playbooks into:
  - `tasks/`
  - `handlers/`
  - `templates/`
  - `vars/`
  - `defaults/`
  - `files/`
- Improved **reusability and organization** of playbooks.

---

## Linux Cheat Sheet

Along with Ansible, I’ve been building strong Linux fundamentals and Terraform Fundamentals .  
👉 **[Check out my Linux Cheat Sheet here](https://github.com/Sangangouda-Patil/Linux-cheat-sheet)**

👉 **[Check out my Linux Cheat Sheet here](https://github.com/Sangangouda-Patil/sangangoudapatil-terraform)**

---

---

## 🚀 Final Note

This repo is a **step-by-step record of my Ansible learning journey**.  
It helped me understand the **core building blocks** of Ansible, making playbooks modular, reusable, and production-ready.

---
