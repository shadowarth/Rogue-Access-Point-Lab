# Fake AP / Rogue Access Point Lab

A repository documenting the implementation and testing of rogue access point (Fake Wi-Fi) techniques on Kali Linux for educational and security research purposes.

> ⚠️ **Disclaimer**: This project is intended strictly for educational purposes, security research, and authorized penetration testing on network infrastructure you own or have explicit permission to audit. Misuse of these tools is illegal under local, federal, and international cybercrime laws.

---

## 📋 Overview

This repository demonstrates the setup of a captive portal / rogue AP using Kali Linux. It illustrates how clients automatically reconnect to known Wi-Fi SSIDs and highlights vulnerabilities in unencrypted or improperly configured wireless networks.

### Features
- **Monitored Wireless Interface**: Configuration of wireless cards in monitor mode.
- **Rogue AP Deployment**: Broadcasting custom or target SSIDs.
- **Captive Portal Integration**: Lightweight web server to simulate network authentication screens.
- **Traffic Interception**: Basic DHCP/DNS routing for client redirection.

---

## 🛠️ Prerequisites & Hardware

### Requirements
- **OS**: Kali Linux 2024.x or later
- **Hardware**: External USB Wireless Adapter supporting **Monitor Mode** and **Packet Injection** (e.g., Alfa AWUS036ACH, TP-Link TL-WN722N v1, or Atheros AR9271). currently using for this lab MediaTek "MT7612U"
- **Dependencies**: `aircrack-ng`, `hostapd`, `dnsmasq`, `lighttpd` / `apache2`.

---

## 🚀 Quick Start Guide

### 1. Identify and Enable Monitor Mode
Find your wireless network interface and set it to monitor mode:

```bash
# List available network interfaces
iwconfig

# Put the wireless interface into monitor mode
sudo ip link set wlan0 down
sudo iw dev wlan0 set type monitor
sudo ip link set wlan0 up
