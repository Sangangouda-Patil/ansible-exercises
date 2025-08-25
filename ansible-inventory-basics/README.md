# Ansible Inventory Basics

This exercise demonstrates how to create and structure an **Ansible inventory file**.  
It includes defining hosts, grouping servers, and creating a group of groups.

---

## 📑 Inventory File Details

- **Hosts defined:**

  - `web01`
  - `web02`
  - `db01`

- **Groups:**
  - `webservers` → contains `web01`, `web02`
  - `dbservers` → contains `db01`
  - `dc_oregon` → combines `webservers` and `dbservers`

---

## ⚙️ Prerequisites

- Ansible installed on the control node.
- SSH access to the managed nodes using a private key (`client-kp.pem`).
- Replace `#PrivateIP` placeholders in the inventory file with actual IP addresses of your servers.

---

## ▶️ Usage

Run an Ansible ad-hoc command to test connectivity:

```bash
ansible -i inventory all -m ping
```

Target only web servers:

```bash
ansible -i inventory webservers -m ping
```

Target only DB servers:

```bash
ansible -i inventory dbservers -m ping
```

Target the entire datacenter group:

```bash
ansible -i inventory dc_oregon -m ping
```
