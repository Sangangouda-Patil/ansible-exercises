## 🔄 loop in Ansible

The loop keyword iterates over a list of items.

Each value from the list is temporarily assigned to the variable item.

Inside the task, you can reference {{ item }} to use the current value.

## Example from your playbook

## 1️⃣ Installing multiple packages

- name: Install chrony on CentOS
  yum:
  name: "{{ item }}"
  state: present
  when:
  - ansible_distribution == "CentOS"
    loop:
  - ntp
  - wget
  - unzip
  - zip
  - git

👉 Here:

The task is executed 5 times, once for each value in the loop list.

First run: installs ntp

Second run: installs wget

Third run: installs unzip

… and so on.

So instead of writing 5 separate tasks, you just loop over the package list.

## 2️⃣ Adding multiple users

- name: Add users
  user:
  name: "{{ item }}"
  state: present
  groups: devops
  loop: "{{ username }}"

  👉 Here:

You’re looping through a variable username (probably defined in group_vars/all or host_vars).

If username: [alice, bob, charlie], then:

First run: creates user alice

Second run: creates user bob

Third run: creates user charlie

## 🔑 Difference between item and username

item is default loop variable (like a placeholder).

You can override it with loop_control if you want a more descriptive name:

```bash
- name: Add users
  user:
    name: "{{ myuser }}"
    state: present
    groups: devops
  loop: "{{ username }}"
  loop_control:
    loop_var: myuser
```

## 👉 In short: loop makes tasks reusable and concise.

Instead of duplicating tasks, you just iterate over a list of values.
