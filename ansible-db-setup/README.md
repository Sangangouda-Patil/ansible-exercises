# Ansible DB Setup

This Ansible playbook installs **MariaDB**, creates a new database, and provisions a database user.

---

## ⚙️ What It Does

- Installs **MariaDB Server** on hosts in the `dbsrvgrp`
- Installs **PyMySQL** (required for Ansible’s MySQL modules)
- Starts & enables the **MariaDB service**
- Creates a database named `accounts`
- Creates a database user `admin` with full privileges

---

## ⚙️ Prerequisites

- Ansible installed on the control node
- Target DB server accessible over SSH
- A valid SSH private key (`.pem`) configured in the `inventory` file

---

## ▶️ Running the Playbook

```bash
ansible-playbook -i inventory db_setup.yaml
```
