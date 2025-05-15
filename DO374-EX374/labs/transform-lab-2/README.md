# 🧪 Ansible Lab – Filtering Complex Data Structures

## Overview
This lab focuses on using advanced Jinja2 filters (`selectattr`, `map`, `select`) and lookup plugins to transform complex data into useful outputs.

It simulates a real-world scenario where:
- User records are provided via variables
- Department metadata is loaded externally
- Filters extract useful subsets of information

## Objectives
- Use `selectattr` to filter users and departments by attributes
- Use `map` to extract emails or usernames
- Load external data using `lookup('file') | from_yaml`
- Practice manipulating structured nested data

## Tasks Summary

```
📘 Tasks in playbook.yml
Each of the following tasks is defined as a prompt inside the playbook. Your job is to write the logic for each task using Ansible filters like selectattr, select, and map.

✅ Task 1 – Select Only Active Users
From the users list (loaded from vars/user_data.yml), filter only the users where active is set to true.
Save the result in a variable called active_users.

✅ Task 2 – Extract Usernames of Active Users
Using the active_users list from Task 1, extract just the username field from each user.
Store this list as active_usernames.

✅ Task 3 – Select Users in Department "ops"
From the full users list, filter only the users where the department is equal to "ops".
Store this filtered list as ops_users.

✅ Task 4 – Map Email Addresses of Ops Users
Using the ops_users list from Task 3, extract each user's email address.
Store this list as ops_user_emails.

✅ Task 5 – Show Departments from External Data
Load department data using a lookup plugin from the file files/departments.yml.
Extract the name field from each department and display the result.

✅ Task 6 – Select Only Active Departments
From the loaded department data, filter only the departments where status is equal to "active".
Store this filtered list as active_depts.

✅ Task 7 – Show Department Heads of Active Departments
From the active_depts list created in Task 6, extract the head value of each department.
Display the final list of department heads.
```


## How to Run

```bash
ansible-playbook playbook.yml --ee false

