# Ansible DB Setup with group_vars/all

This playbook demonstrates how to use **Ansible variable files** (`group_vars/all`) to manage configuration for database setup.  
Instead of hardcoding values in the playbook, variables such as **database name**, **user**, and **password** are stored centrally in `group_vars/all`.

---

## 📂 group_vars/all

The `group_vars/all` file is a special location in Ansible where you can define variables that are **accessible to all hosts** in your inventory.  
It helps to separate configuration (variables) from logic (playbooks).

Example file:

```yaml
# group_vars/all
dbname: accounts
dbuser: testadmin
dbpass: admin123
```

## 🔑 Why use group_vars/all?

Keeps playbooks clean and reusable

Centralizes variable management

Follows Ansible’s variable precedence rules
(vars in playbook or CLI -e will override group_vars/all)

## ⚙️ What the Playbook Does

Installs MariaDB Server and PyMySQL

Starts & enables the MariaDB service

Creates a database using {{ dbname }}

Creates a user using {{ dbuser }} with password {{ dbpass }}

Demonstrates register by storing the task result in dbout and printing it with debug

▶️ Running the Playbook

```bash
ansible-playbook -i inventory db_with_group_vars.yaml
```
