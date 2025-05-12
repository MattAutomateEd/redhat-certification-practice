# 🧪 EX374 Lab: Transform Data with Filters and Plugins

This lab is designed to prepare you for the **EX374 exam objective**:

> **Transform Data with Filters and Plugins**  

---

## 📂 Lab Layout

Create the following directory and file structure:

transform-lab-1/
├── inventory/
│ └── hosts
├── files/
│ ├── servers.json
│ └── subnets.yml
├── templates/
│ └── server_report.j2
├── vars/
│ └── external_vars.yml
├── playbook.yml
└── README.md ← (this file)



## Modify ansible.cfg
Update ansible.cfg remote_user to your user. (replace MattAutomateEd)


## RPM Requirements
ansible-automation-platform-common
ansible-navigator

## inventory/inventory
Update your inventory file

## Login into https://registry.redhat.io (podman)
podman login https://registry.redhat.io

## Solutions
See the solutions directory for the solution


---

## ✅ Task 1: Load Server Data from JSON File

**Goal**:  
Load structured data from the `files/servers.json` file using a lookup plugin, and store the parsed result in a variable called `servers`.  Use the existing playbook.yml and add task 1.  Try to use ansible-navigator if you have a execution environment.  However, ansible-playbook will work as well.

---

## ✅ Task 2: Load Subnet Data from YAML File

**Goal**:  
Load structured data from the `files/subnets.yml` file using a lookup plugin, and store the parsed result in a variable called `subnet_data`.

---

## ✅ Task 3: Extract Frontend Servers

**Goal**:  
From the list of servers in `servers`, extract only the entries where the `"role"` is `"frontend"`.  
Store the result in a variable called `frontend_servers`.

---

## ✅ Task 4: Extract Frontend IPs

**Goal**:  
From the `frontend_servers` list, extract only the `ip` values.  
Store this list of IPs in a variable called `frontend_ips`.

---

## ✅ Task 5: Filter IPs That Belong to Subnet

**Goal**:  
From the list of `frontend_ips`, identify and print only the IPs that belong to the `192.168.10.0/24` subnet.  
Use an appropriate filter for subnet logic and loop over the valid results.

---

## ✅ Task 6: Generate a Server Report from a Template

**Goal**:  
Render a report from the `templates/server_report.j2` template file using the full list of servers and their location metadata (from `vars/external_vars.yml`).

The report should include for each server: (and should look like)
- Hostname
  Role
  IP
  Location (based on hostname key from `locations` dictionary)

If no location is available for a given hostname, show `"Unknown"`.

Output the final report to:
/tmp/server_report.txt



---

## 🧠 Tip for Exam Study

Focus on:
- Using `lookup()` properly with `from_json` / `from_yaml`,
- Mastering `selectattr`, `map`, `select`, and `ansible.utils.ipaddr`,
- Rendering structured Jinja2 output from filtered data.


