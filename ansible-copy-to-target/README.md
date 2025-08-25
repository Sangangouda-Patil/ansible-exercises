# Ansible Copy to Target Machines

This project contains two Ansible playbooks:

1. **Webserver Setup (`web.yaml`)**

   - Installs **Apache (httpd)**
   - Starts and enables the service
   - Demonstrates the **`copy` module** by transferring a local `index.html` file to `/var/www/html` on the target web servers

2. **Database Setup (`db.yaml`)**
   - Installs **MariaDB Server** and **PyMySQL**
   - Starts and enables the MariaDB service
   - Creates a database named `accounts`
   - Creates a user `admin` with full privileges

---

## ⚙️ Prerequisites

- Ansible installed on the control node
- Target servers accessible via SSH
- A valid SSH private key (`.pem`) configured in the `inventory` file

---

## ▶️ Running the Playbooks

Run the **webserver setup**:

```bash
ansible-playbook -i inventory web.yaml
```
