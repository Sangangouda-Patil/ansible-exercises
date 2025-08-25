## 📂 Project Structure

```bash
├── group_vars/
│   └── all.yml              # Global variables for all hosts
├── templates/
│   ├── ntp_redhat.conf.j2   # NTP configuration template for RedHat/CentOS
│   └── ntp_debian.conf.j2   # NTP configuration template for Debian/Ubuntu
├── provisioning.yml         # Main playbook
└── README.md                # Documentation
```

## ⚙️ Features

Cross-platform support:

Installs NTP & common utilities on CentOS/RedHat and Ubuntu/Debian.

Service management:

Enables and starts NTP (ntpd for RedHat, ntp for Debian).

User & group management:

Creates a devops group.

Adds multiple users (defined in group_vars/all.yml) to the group.

Custom MOTD:

Adds a login banner to /etc/motd showing the managed OS.

Template-based NTP configuration:

Deploys ntp.conf from OS-specific Jinja2 templates.

Directory management:

Creates /opt/devdata with proper permissions.

Service restart:

Ensures NTP is restarted after configuration.

## ▶️ Running the Playbook

## Clone the repository:

```bash
git clone url
cd ansible-provisioning
```

## Update inventory file with your hosts:

[all]
server1 ansible_host=192.168.1.10 ansible_user=ubuntu
server2 ansible_host=192.168.1.20 ansible_user=centos

## Run the playbook:

```bash
ansible-playbook -i inventory provisioning.yml
```

## ✅ Expected Outcomes

Required packages installed (ntp, wget, git, zip, unzip).

NTP service installed, configured, and running.

Users (alice, bob, charlie) created under the devops group.

Banner message available in /etc/motd.

/opt/devdata directory created with 0775 permissions.

OS-specific NTP configuration applied.
