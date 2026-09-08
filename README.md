# Wireless Audit Lab: Wifiphisher

A security research repository documenting the deployment, mechanics, and defensive analysis of automated rogue access point scenarios using **Wifiphisher** on Kali Linux.

> ⚠️ **Disclaimer**: This tool and repository are strictly intended for educational purposes, security awareness, and authorized wireless penetration testing on networks you own or have explicit written permission to audit. Any unauthorized deployment against public or third-party networks is strictly illegal under applicable cybercrime legislation.

---

## 📋 Overview

[Wifiphisher](https://github.com/wifiphisher/wifiphisher) is a rogue access point framework that automates social engineering and man-in-the-middle (MITM) attacks against Wi-Fi networks. 

This lab documentation details how Wifiphisher achieves client redirection using targeted deauthentication, automated DHCP/DNS routing, and customized phishing scenarios.

### Core Attack Mechanics
1. **Targeted Deauthentication**: Forces target clients off their legitimate access point using forged deauth packets.
2. **Rogue AP Association**: Spawns a twin AP broadcasting the target SSID to lure reauthenticating clients.
3. **Phishing & Captive Portal**: Serves victim devices tailored web pages (e.g., firmware updates, Wi-Fi password prompts, or OAuth login pages).

---

## 🛠️ Hardware & Prerequisites

### Required Hardware
* **Operating System**: Kali Linux 2024.x+
* **Wireless Adapters**: 
  * **Primary Adapter**: Supporting **Monitor Mode** and **Packet Injection** (e.g., Alfa AWUS036ACH, Atheros AR9271). currently using for this lab MediaTek "MT7612U"
  * **Secondary Adapter** *(Recommended)*: An additional interface for internet forwarding/bridging.

### Required Software Packages
```bash
sudo apt update
sudo apt install -y wifiphisher python3-pip hostapd dnsmasq
