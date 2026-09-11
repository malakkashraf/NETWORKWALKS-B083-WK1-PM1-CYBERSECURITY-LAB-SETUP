# 🔐 Virtual Cybersecurity Lab

> Building and configuring a controlled Kali Linux environment for cybersecurity learning.

<p align="center">
  <img src="./screenshots/04-kali-desktop.png" width="850">
</p>

---

## 🧭 Project Overview

This project documents the creation of a personal cybersecurity laboratory using **Oracle VirtualBox** and **Kali Linux**.

The goal was to build a safe, isolated environment where networking concepts and security tools can be explored without interacting with unauthorized systems.

The laboratory is designed to be expandable, allowing additional virtual machines to be introduced later for controlled security-testing exercises.

---

## 🎯 Project Goals

The laboratory was created with the following goals:

- 🖥️ Set up a virtualization environment using VirtualBox
- 🐉 Install and configure Kali Linux
- 🌐 Build a dedicated virtual network
- ⚙️ Configure Kali's network interface
- 🔌 Establish reliable network connectivity
- 📡 Verify IP addressing, gateway access, and DNS
- 💾 Create a clean recovery point using a VM snapshot
- 🐛 Troubleshoot configuration and connectivity issues
- 📝 Document the setup process and verification results
- 🚀 Prepare the environment for future cybersecurity exercises

---

## 🧰 Environment & Technologies

| Category | Configuration |
|---|---|
| 💻 Host Operating System | Windows 10 |
| 🧰 Virtualization Platform | VirtualBox 7.2 |
| 🐉 Security Distribution | Kali Linux 2026.2 |
| 🧠 Host Memory | 8 GB |
| ⚡ Processor | Intel Core i7 |
| 🧠 Kali Memory | 2048 MB |
| 🌐 Network Mode | NAT Network |
| 📡 Network | `10.0.0.0/24` |
| 🐧 Kali Address | `10.0.0.2/24` |
| 🚪 Gateway | `10.0.0.1` |
| 🌍 DNS | `8.8.8.8` / `10.0.0.1` |

---

## 🏗️ Laboratory Architecture

The initial laboratory consists of a Windows host machine running VirtualBox and a Kali Linux virtual machine connected to a dedicated NAT Network.

```text
┌───────────────────────────────────┐
│          Windows Host             │
│                                   │
│          VirtualBox 7.2           │
│                 │                 │
│                 ▼                 │
│        ┌────────────────┐         │
│        │   NAT Network  │         │
│        │   10.0.0.0/24  │         │
│        └───────┬────────┘         │
│                │                  │
│                ▼                  │
│        ┌────────────────┐         │
│        │   Kali Linux   │         │
│        │   10.0.0.2/24  │         │
│        └────────────────┘         │
│                                   │
└───────────────────────────────────┘
```

---

## 🌐 Network Configuration

### 📡 Intended Network Configuration

The intended configuration for the Kali Linux virtual machine was:

| Setting | Value |
|---|---|
| IPv4 Address | `10.0.0.2` |
| Subnet Mask | `255.255.255.0` |
| Gateway | `10.0.0.1` |
| DNS Server | `8.8.8.8` |

---

# 🪜 Laboratory Setup

The following steps document the configuration of the Kali Linux cybersecurity laboratory, from creating the virtual network to taking the final recovery snapshot.

---

## 🔹 Step 01 — Configure the NAT Network

I created a dedicated NAT Network in VirtualBox and configured its IPv4 network address as `10.0.0.0/24`.

This network provides the foundation for communication between the virtual machines in the laboratory.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/01-nat-network.png" width="750">
</p>

---

## 🔹 Step 02 — Connect Kali Linux to the NAT Network

I configured the Kali Linux virtual machine to use the **NAT Network** option in VirtualBox rather than the standard NAT option.

This allows the VM to participate in the dedicated virtual network created for the laboratory.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/02-nat-network-vm.png" width="750">
</p>

---

## 🔹 Step 03 — Access the Kali Linux System

After starting the virtual machine, I reached the Kali Linux password screen and logged into the system to continue the network configuration.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/03-kali-login.png" width="750">
</p>

---

## 🔹 Step 04 — Access the Kali Linux Desktop

After logging in successfully, the main Kali Linux desktop was displayed.

This confirmed that the virtual machine was running correctly and was ready for further configuration.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/04-kali-desktop.png" width="750">
</p>

---

## 🔹 Step 05 — Configure the Wired Connection

I configured **Wired Connection 1** with the network settings required for the laboratory.

| Setting | Configuration |
|---|---|
| IPv4 Address | `10.0.0.2` |
| Netmask | `24` |
| Gateway | `10.0.0.1` |

This gave the Kali Linux machine a consistent address within the `10.0.0.0/24` network.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/05-network-settings.png" width="750">
</p>

---

## 🔹 Step 06 — Verify Internet Connectivity

I opened Google to verify that the network configuration was working correctly and that the Kali Linux virtual machine had successful Internet connectivity.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/06-internet-connectivity.png" width="750">
</p>

---

## 🔹 Step 07 — Create the Final Snapshot

After completing the configuration and verifying the connection, I created a final VirtualBox snapshot.

This provides a documented recovery point that can be used to return to the completed setup in the future.

### 📸 Evidence

<p align="center">
  <img src="./screenshots/07-final-snapshot.png" width="750">
</p>

---

# 🐛 Challenges & Troubleshooting

## 🔹 Challenge 01 — NAT vs. NAT Network

At first, I confused **NAT** with **NAT Network** in VirtualBox. This caused some challenges while setting up the network for my Kali Linux machine.

### 💡 Solution

I checked the difference between the two options and changed my VirtualBox network setting to **NAT Network**.

After that, I continued with the network configuration successfully.

### 📚 What I Learned

I learned that NAT and NAT Network are different and that choosing the correct option is important when setting up a virtual laboratory.

---

## 🔹 Challenge 02 — Network Configuration

I also faced some difficulties while configuring the network settings inside Kali Linux.

### 💡 Solution

I checked the network settings and configured the correct IP address, netmask, and gateway.

I then opened Google to verify that the connection was working.

### 📚 What I Learned

I learned how the VirtualBox network settings and Kali Linux network settings work together to provide a working connection.

---

# 📚 What I Learned

Through this project, I gained practical experience with:

- Virtual machine creation and configuration
- Oracle VirtualBox networking
- NAT Network configuration
- Kali Linux network configuration
- IPv4 addressing and subnet masks
- Default gateways and DNS
- Basic network troubleshooting
- Virtual machine snapshots and recovery points
- Documenting technical configurations
- Building an isolated environment for cybersecurity learning

This project also gave me a foundation for expanding the laboratory with additional virtual machines and more advanced cybersecurity exercises.

---

# 🚀 Future Improvements

The laboratory can be expanded in the future by introducing additional virtual machines and controlled security-testing scenarios.

Potential future additions include:

- 🖥️ Additional Linux virtual machines
- 🪟 A Windows-based test machine
- 🌐 Multiple virtual network segments
- 🔎 Network traffic analysis
- 🛡️ Defensive security monitoring
- 🧪 Controlled vulnerability-testing exercises
- 📊 Network monitoring and logging

The goal is to gradually develop the laboratory into a more complete cybersecurity practice environment.

---

# 🔗 Resources

- [7-Zip](https://7-zip.org/download.html)
- [Oracle VirtualBox](https://virtualbox.org/wiki/Downloads)
- [Kali Linux](https://kali.org/get-kali)

---

# 👤 Project Author

**Malak Ashraf**

`Computer Science Student | Cybersecurity & Networking Enthusiast`

I created this project as part of my cybersecurity learning journey, focusing on building and configuring a controlled virtual laboratory using VirtualBox and Kali Linux.

---

## 🔗 Connect With Me

**LinkedIn:**  
[linkedin.com/in/malak-ashraf-196084370](https://www.linkedin.com/in/malak-ashraf-196084370)

---

<p align="center">
  ⭐ If you found this project interesting, feel free to explore the repository!
</p>
