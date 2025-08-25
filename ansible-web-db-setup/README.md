# Ansible Web & DB Setup

This Ansible playbook automates the setup of:
- **Apache Web Server (httpd)** on all hosts in the `websrvgrp`
- **MariaDB Server** on all hosts in the `dbsrvgrp`

It also copies a custom `index.html` file to the web servers.

---

## ⚙️ Prerequisites
- Ansible installed on the control node
- Target servers (web + db) accessible over SSH
- A valid SSH private key (`.pem` file) to connect to instances

---

## ▶️ Running the Playbook
Run the playbook with the following command:

```bash
ansible-playbook -i inventory web_db.yaml
```