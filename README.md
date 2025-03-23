# CST 8919 – DevOps: Security and Compliance  
## Lab Report: Grafana Installation and Dashboard Creation for Ubuntu Server Performance

### 👨‍💻 Student Name: Savas Erturk  
### 📅 Date: March 2025  

---

## 🧪 Lab Overview

This lab focused on installing Grafana on an Ubuntu server, connecting it to Azure Monitor using managed identity, and visualizing server performance metrics on a custom dashboard. The objective was to demonstrate secure monitoring setup and real-time performance visualization.

---

## ✅ Tasks Completed

### Task 1: Prepare Ubuntu Server

- Updated and upgraded the server using `apt-get`.
- Installed required packages: `apt-transport-https`, `software-properties-common`, and `wget`.

### Task 2: Install Grafana

- Added Grafana’s official GPG key and APT repository.
- Installed Grafana and enabled its systemd service.
- Verified that Grafana was running on port 3000 and allowed the port through the firewall using `ufw`.

### Task 3: Connect Grafana to Azure Monitor

- Enabled **System-Assigned Managed Identity** on the Azure VM.
- Assigned **Monitoring Reader** role on Azure Monitor and **Reader** role on the subscription to the VM.
- Edited `/etc/grafana/grafana.ini` to enable `managed_identity_enabled = true`.
- Restarted the Grafana service.
- Logged into Grafana using the default credentials and added **Azure Monitor** as a data source using Managed Identity authentication.
- Successfully tested and saved the data source.

### Task 4: Create a Grafana Dashboard

- Created a new dashboard and added panels using Azure Monitor metrics.
- Visualized key performance indicators including:
  - CPU Utilization
  - Memory Usage
  - Disk I/O
  - Network In/Out
- Customized the panels with labels and thresholds.
- Saved the dashboard.

---

## 🖼️ Screenshots

> 📸 Include screenshots in a `screenshots/` folder in your repo, and reference them like this:

- **Grafana Service Running**  
  ![Grafana Running](./screenshots/ss1.png)

- **Azure Role Assignments**  
  ![Azure Role Assignment](./screenshots/ss2.png)

- **Azure Monitor Data Source Setup**  
  ![Data Source](./screenshots/ss3.png)

- **Final Grafana Dashboard**  
  ![Dashboard](./screenshots/ss4.png)

---

## 🛠️ Issues Encountered & Solutions

| Issue | Solution |
|------|----------|
| Grafana service didn’t start at first | Ran `systemctl daemon-reload` and verified syntax in the config file |
| Azure Monitor data source failed to connect | Re-checked role assignments and ensured the VM had correct permissions |
| No data displayed initially | Adjusted time range and selected correct resource group/metrics in panel config |

---

## 🔗 Submission

- **GitHub Repo Link**: [Insert your GitHub link here]
  https://github.com/savaserturk/grafana-azure-monitor
---

## 📌 Notes

- Used default Grafana port `3000` for access.
- Made sure to restart Grafana after every config change.
- Data was visualized using Azure Monitor via managed identity for secure authentication.

