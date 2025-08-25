## What it Does

Gathers Facts (gather_facts: yes) → Ansible automatically collects system information like OS family, memory, CPU, etc.

## Installs NTP/Chrony depending on the OS:

If os_family == "CentOS" → installs chrony

If os_family == "Ubuntu" → installs ntp

Starts and Enables Services:

For CentOS → starts chronyd

For Ubuntu → starts ntp

## (Optional but commented) → Ensures these tasks only run if free RAM > 40% using facts like ansible_facts['memfree_mb'].

## 🔹 Why This is Useful

Portability → Same playbook works across multiple OS types.

Resource-aware Deployment → You can prevent installations on under-provisioned systems (low RAM).

Dynamic Playbooks → Instead of hardcoding, you use system facts to make decisions.
