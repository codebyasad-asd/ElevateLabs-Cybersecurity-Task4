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


netsh advfirewall show allprofiles
What does this command do?

This command displays the configuration and status of all Windows Firewall
profiles.

It shows:

Domain Profile
Private Profile
Public Profile
Firewall state
Firewall policy
Logging settings
Remote management settings
Result

The three firewall profiles were found to be:

Domain Profile  → ON
Private Profile → ON
Public Profile  → ON

This confirms that Windows Firewall was enabled for all three profiles.

🔹 Step 2 — Create a Firewall Rule
Command
netsh advfirewall firewall add rule name="Block Telnet Port 23" dir=in action=block protocol=TCP localport=23
Explanation

This command creates a new Windows Firewall rule.

Part	Meaning
netsh	Windows network configuration utility
advfirewall	Accesses advanced firewall configuration
firewall	Specifies Windows Firewall
add rule	Creates a new firewall rule
name=	Gives the rule a name
dir=in	Applies the rule to incoming traffic
action=block	Blocks matching traffic
protocol=TCP	Applies the rule to TCP traffic
localport=23	Applies the rule to local port 23
Important Concept

The rule was designed to block incoming TCP connections to Port 23.

🔹 Step 3 — Verify the Firewall Rule
Command
netsh advfirewall firewall show rule name="Block Telnet Port 23"
Purpose

This command displays the configuration of the firewall rule that was
created in the previous step.

Important Results

The rule showed:

Enabled:     Yes
Direction:   In
Profiles:    Domain,Private,Public
Protocol:    TCP
LocalPort:   23
Action:      Block

This confirms that the rule was correctly configured.

🔹 Step 4 — Test TCP Port 23
Command
powershell -Command "Test-NetConnection 127.0.0.1 -Port 23"
Explanation

This command uses PowerShell's Test-NetConnection utility to test
whether a TCP connection can be established to port 23.

Part	Meaning
powershell	Starts PowerShell
-Command	Tells PowerShell to execute the following command
Test-NetConnection	Tests network connectivity
127.0.0.1	Localhost / current computer
-Port 23	Tests TCP port 23
Result

The test produced:

TcpTestSucceeded : False

This means that the TCP connection to port 23 was not successfully
established.

The result is consistent with the firewall rule blocking the connection.

🔹 Step 5 — Delete the Temporary Firewall Rule

After testing, the temporary rule was removed.

Command
netsh advfirewall firewall delete rule name="Block Telnet Port 23"
Explanation
Part	Meaning
netsh	Windows network configuration utility
advfirewall	Advanced Firewall configuration
firewall	Windows Firewall
delete rule	Removes a firewall rule
name=	Specifies which rule should be removed
Result
Deleted 1 rule(s).
Ok.

The temporary firewall rule was successfully removed.

📚 Technical Terms
🔥 Firewall

A firewall is a security mechanism that controls network traffic based
on predefined rules.

It can allow or block network connections.

🌐 Network Traffic

Network traffic is data moving between computers, devices, applications,
or networks.

📥 Inbound Traffic

Inbound traffic is network traffic coming into a computer.

Example:

Other Computer
      ↓
  Incoming Traffic
      ↓
Your Computer
📤 Outbound Traffic

Outbound traffic is network traffic leaving a computer.

Example:

Your Computer
      ↓
 Outgoing Traffic
      ↓
Other Computer
🔌 Port

A port is a logical communication endpoint used by network applications.

Ports help the operating system determine which application or service
should receive network traffic.

Examples:

Port	Common Association
22	SSH
23	Telnet
80	HTTP
443	HTTPS
📡 TCP

TCP stands for Transmission Control Protocol.

TCP provides reliable, connection-oriented communication between devices.

🖥️ Telnet

Telnet is a network protocol traditionally associated with TCP Port 23.

Telnet does not provide the same encryption protections as secure
protocols such as SSH, so exposing Telnet services can create security
risks.

🏠 127.0.0.1

127.0.0.1 is the IPv4 loopback address, commonly called
localhost.

It refers back to the same computer.

⚙️ netsh

netsh stands for Network Shell.

It is a Windows command-line utility used to configure and inspect
network-related settings.

💻 PowerShell

PowerShell is Microsoft's command-line shell and scripting environment.

It provides commands and tools for system administration, networking,
automation, and security tasks.

🧠 What I Learned

Through this task, I learned:

How to check Windows Firewall profiles.
How to create a firewall rule using the command line.
How inbound firewall rules work.
How TCP ports are used for network communication.
How to verify a firewall rule.
How to test network connectivity using PowerShell.
How to remove a firewall rule after testing.
Why unused or insecure network services should be restricted.
🔐 Security Importance

Firewall rules are an important part of endpoint security.

Blocking unnecessary network ports can reduce the number of services
that are exposed to other systems.

In this task, TCP Port 23 was blocked as an example of restricting
incoming network traffic associated with Telnet.

In a real environment, firewall rules should be created according to
the organization's security requirements and should be tested before
being deployed widely.

📸 Evidence

The following screenshots were captured during the practical:

1. Firewall Profiles

Shows Domain, Private, and Public firewall profiles enabled.

2. Firewall Rule Creation

Shows the successful creation of the
Block Telnet Port 23 rule.

3. Firewall Rule Verification

Shows the rule configuration including:

Direction: In
Protocol: TCP
Local Port: 23
Action: Block
4. Port Testing

Shows:

TcpTestSucceeded : False
5. Rule Removal

Shows that the temporary firewall rule was successfully deleted.

✅ Final Result

The Windows Firewall was successfully inspected and configured.

An inbound firewall rule was created to block TCP Port 23.
The rule was verified and the port connectivity test returned:

TcpTestSucceeded : False

After completing the test, the temporary firewall rule was removed
successfully.

🎓 Conclusion

This task provided practical experience with Windows Firewall and basic
network security concepts.

It demonstrated how command-line tools can be used to inspect firewall
settings, create security rules, verify their configuration, test network
connectivity, and safely remove temporary configurations.

The task also helped build a basic understanding of TCP, ports, inbound
traffic, Telnet, PowerShell, and Windows network security.

👨‍💻 Internship Task Status

Task 4 — COMPLETED ✅

Practical firewall configuration, verification, testing, and cleanup
successfully completed.
