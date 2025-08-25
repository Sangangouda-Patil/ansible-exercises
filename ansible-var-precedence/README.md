# Ansible Variable Precedence

This playbook demonstrates **Ansible variable precedence** by creating a user with variables defined at different levels (`group_vars`, `host_vars`, playbook vars, and extra vars).

---

## 📖 About Variable Precedence

Ansible decides which variable value to use based on **precedence rules**.  
From lowest → highest priority:

1. `group_vars/all`
2. `group_vars/<group>`
3. `host_vars/<host>`
4. Variables defined in a playbook (`vars:` section)
5. Extra vars provided via CLI (`-e` flag)

➡️ The variable defined at the **highest level** overrides others.

---

## ⚙️ What the Playbook Does

- Defines variables `USRNM` and `COMM` inside the playbook (`vars:` block).
- Creates a Linux user using the values of those variables.
- Demonstrates overriding by:
  - Defining variables in `group_vars/all`
  - Defining variables in `host_vars/<hostname>`
  - Overriding with CLI arguments (`-e`)
- Prints the final values applied using `register` + `debug`.

---

## 📂 Example Setup

### group_vars/all

```bash
USRNM: groupuser
COMM: variable from group_vars/all
```

## host_vars/web01

```bash
USRNM: hostuser
COMM: variable from host_vars/web01
```

## Inside Playbook

```bash
vars:
  USRNM: playuser
  COMM: variable from playbook
```

## CLI Extra Vars

```bash
ansible-playbook -i inventory var_precedence.yaml -e "USRNM=extravar COMM='variable from CLI'"
```

## ▶️ Running the Playbook

```bash
ansible-playbook -i inventory var_precedence.yaml
```

## ➡️ Try changing variables in group_vars, host_vars, or add -e to see which value is finally used.
