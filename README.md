# 🔥 Task 4 — Windows Firewall Configuration & Testing

![Cybersecurity](https://img.shields.io/badge/Internship-Cybersecurity-blue)
![Platform](https://img.shields.io/badge/Platform-Windows%2011-lightgrey)
![Firewall](https://img.shields.io/badge/Windows%20Firewall-Configured-success)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Overview

This task demonstrates the basic configuration and testing of the
**Windows Defender Firewall** using the Windows Command Prompt and PowerShell.

The main objective was to understand how a firewall can control network
connections by creating a rule that blocks incoming TCP traffic on
**Port 23**, which is commonly associated with Telnet.

The task also demonstrates how to verify the firewall rule, test whether
the port is accessible, and finally remove the temporary rule.

---

## 🎯 Objectives

The objectives of this task were:

- Understand Windows Firewall profiles.
- Check the status of Domain, Private, and Public firewall profiles.
- Create an inbound firewall rule.
- Block TCP Port 23.
- Verify the firewall rule.
- Test the blocked port.
- Remove the temporary firewall rule.
- Understand basic networking and firewall terminology.

---

## 🖥️ Environment

| Item | Details |
|---|---|
| Operating System | Windows |
| Architecture | 64-bit |
| Processor | Intel Core i5-1240P |
| RAM | 8 GB |
| Firewall | Windows Defender Firewall |
| Tools | Command Prompt, PowerShell |
| Protocol | TCP |
| Port Tested | 23 |
| Port Service | Telnet |

---

# 🔹 Step 1 — Check Firewall Profiles

### Command

```cmd
netsh advfirewall show allprofiles
