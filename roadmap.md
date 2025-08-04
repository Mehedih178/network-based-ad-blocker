# 🚫 Network-Wide Ad Blocker with AdGuard Home on Ubuntu 22.04 (UTM VM)

This project sets up a network-wide ad blocker using **AdGuard Home** on an **Ubuntu 22.04** virtual machine hosted with **UTM**. The goal is to route all DNS traffic through AdGuard for faster browsing, improved privacy, and blocking unwanted content across the entire network.

---

## 📌 Project Goals

- Deploy Ubuntu 22.04 on UTM
- Install and configure AdGuard Home
- Set the VM as the network DNS server
- Block ads, trackers, malicious domains network-wide
- Optionally secure with HTTPS & access logs

---

## 🗺️ Roadmap

### ✅ Phase 1: VM Setup (UTM)
- [x] Install UTM on macOS
- [x] Create a new VM with:
  - Ubuntu Server 22.04 ISO
  - 1-2 CPUs, 2+ GB RAM, 20+ GB storage
  - Bridged or Shared Network (for LAN access)
- [x] Install Ubuntu Server (SSH server optional)

---

### 🔧 Phase 2: AdGuard Home Installation
- [x] Update system packages:
  ```bash
  sudo apt update && sudo apt upgrade -y
 Download & install AdGuard Home:

bash
Copy
Edit
wget https://static.adguard.com/adguardhome/release/AdGuardHome_linux_amd64.tar.gz
tar -xvf AdGuardHome_linux_amd64.tar.gz
cd AdGuardHome
sudo ./AdGuardHome -s install
 Access web UI at:

cpp
Copy
Edit
http://<VM-IP>:3000
🌐 Phase 3: Initial Web Setup
 Walk through AdGuard Home setup wizard

Choose DNS server port (default: 53)

Choose admin panel port (default: 3000)

Set admin username & password

 Enable DNS logging & basic filters

🌍 Phase 4: Network Integration
 Assign the VM a static IP (via router or Netplan)

 Configure your router or devices to use the VM's IP as the DNS server

Option 1: Set DNS manually per device

Option 2: Change DNS in router DHCP settings

🔐 Phase 5: Optional Security & Extras
 Set up HTTPS using Let's Encrypt or self-signed cert

 Add custom blocklists (e.g. OISD, StevenBlack)

 Enable parental controls / safe search

 Configure logging, query filtering, and stats

 Create scheduled backups of config

🧪 Testing
Try accessing ad-heavy sites (e.g. Forbes, DailyMail)

Use tools like:

nslookup <domain> or dig to verify DNS resolution

AdGuard Test Page

📸 Screenshots (Coming Soon)
UTM VM Setup

AdGuard Dashboard

DNS Query Logs

Blocking Reports

📋 Requirements
Tool	Version / Notes
UTM	macOS virtualization app
Ubuntu Server	22.04 LTS
AdGuard Home	Latest (auto-update built in)
Local Network	Router must support custom DNS

🧠 Credits / Resources
AdGuard Home Docs

UTM for macOS

AdGuard Blocklists

🔒 Notes
Running your own DNS resolver can improve privacy, but also increases responsibility.

Monitor logs for unexpected queries (e.g. IoT devices calling home).

Consider pairing with Unbound or DoH/DoT for encrypted upstream DNS.

✅ Status
Project is active and under testing as of August 2025.
