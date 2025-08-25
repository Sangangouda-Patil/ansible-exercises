# Ansible Facts Demo

This playbook demonstrates how to use **Ansible facts** to gather system information and make decisions based on host properties.

---

## 📖 About Facts

- **Facts** are system information automatically collected by Ansible from managed hosts when a playbook runs.
- Examples: OS details, IP addresses, memory, CPU, SELinux status, etc.
- These can be used in conditions (`when:`), templates, and decision-making tasks.

You can list all facts with:

```bash
ansible all -i inventory -m setup
```

## ⚙️ What the Playbook Does

Prints OS distribution name

Prints SELinux mode

Prints memory details

Prints available RAM

Prints processor details

## ▶️ Running the Playbook

ansible-playbook -i inventory facts_demo.yaml

## 📝 Example Use Cases

Run tasks only if the OS is CentOS or Ubuntu etc

Install packages based on distribution

Apply different configurations depending on available RAM or CPU

Enable/disable services depending on SELinux status
