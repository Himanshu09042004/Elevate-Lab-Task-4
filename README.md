# Elevate-Lab-Task-4
Configured and tested firewall rules using UFW on Kali Linux. Blocked Telnet (port 23), allowed SSH (port 22), and verified rule functionality. Gained hands-on experience in managing inbound traffic and understanding firewall behavior for secure networking.

# 🔐 Task 4 - Setup and Use a Firewall on Linux

## 📌 Objective
Configure and test basic firewall rules using **UFW (Uncomplicated Firewall)** to block and allow traffic on specific ports. This task helps build fundamental knowledge in **firewall management** and **network traffic filtering**.

---

## 💻 Tools Used
- **Operating System**: Kali Linux
- **Firewall Tool**: UFW (Uncomplicated Firewall)
- **Terminal Utility**: telnet (for testing)

---

## 🧠 Key Concepts
- **Firewall**: A system that monitors and controls incoming and outgoing network traffic based on predetermined security rules.
- **UFW**: A frontend for `iptables` aimed at simplifying firewall configuration.
- **Port**: A communication endpoint (e.g., port 22 for SSH, 23 for Telnet).
- **Inbound/Outbound Rules**: Control traffic flowing in or out of your system.
- **Telnet Blocking**: Port 23 is commonly blocked due to its lack of encryption.

---

## 🪜 Step-by-Step Instructions

```bash
# 1. Install UFW (if not already installed)
sudo apt update
sudo apt install ufw -y

# 2. Enable UFW
sudo ufw enable

# 3. Check Firewall Status
sudo ufw status verbose

# 4. Add a Rule to Block Port 23 (Telnet)
sudo ufw deny 23

# 5. Allow SSH on Port 22 (to avoid getting locked out)
sudo ufw allow 22

# 6. Test Port 23 Block with Telnet
telnet localhost 23
# ❗️Expected Result: Connection refused or failed (indicating block is successful)

# 7. Remove the Telnet Block Rule
sudo ufw delete deny 23

# 8. Check Rules Again
sudo ufw status numbered

