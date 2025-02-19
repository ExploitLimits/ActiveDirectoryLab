# 🖥️ Windows Server 2019 Lab Setup

This project documents my hands-on experience setting up a Windows Server 2019 lab in VirtualBox, configuring Active Directory, DHCP, and RAS/NAT, and troubleshooting network connectivity issues.

## 🚀 Project Overview
- **🛠️ Virtualization Tool**: VirtualBox
- **💻 Operating Systems**: Windows Server 2019, Windows 10
- **🔧 Core Components**: Active Directory, DNS, DHCP, Routing & Remote Access (NAT)
- **🎯 Objective**: Build a functional Windows domain environment and troubleshoot real-world issues

## 📝 Steps Taken
1. 🔹 **Installed and Configured Oracle Virtual Box**
2. 🔹 **Installed and Configured Windows Server 2019**
3. 🔹 **Set Up Active Directory & DNS**
4. 🔹 **Configured DHCP for Client Addressing**
5. 🔹 **Enabled RAS/NAT for Internet Access**
6. 🔹 **Automating user creation with PowerShell scripts**
7. 🔹 **Installed and Configured Windows Server 2019**
8. 🔹 **Connected a Windows 10 Client to the Domain**
9. 🔹 **Tested Connectivity and Troubleshot Issues**

## ⚠️ Challenges & Troubleshooting
Throughout the setup, I encountered several issues and resolved them as follows:

### ❌ Issue: Incorrect IP Address on Internal NIC
**🔍 Problem**: The domain controller's internal NIC was assigned the wrong IP address, preventing clients from connecting properly.
**✅ Solution**: Reconfigured the NIC with the correct static IP (172.16.0.1) and verified settings with `ipconfig /all`.

### ❌ Issue: Client Could Not Access the Internet
**🔍 Problem**: The client could ping `8.8.8.8` but could not resolve domain names.
**✅ Solution**: Fixed the DNS server configuration, ensuring the client used the DC's IP (172.16.0.1) as its primary DNS and set up DNS Forwarders to external resolvers.

### ❌ Issue: DHCP Scope Not Enumerating
**🔍 Problem**: Running `Get-DhcpServerv4Scope` returned a permission error.
**✅ Solution**: Adjusted permissions on the DHCP server role and restarted the service, then verified using `Get-DhcpServerv4Scope`.

## 📸 Screenshots
To illustrate my setup and troubleshooting steps, I included:
- 🖧 VirtualBox network settings
- 📜 Windows Server IP configuration (`ipconfig /all`)
- ⚙️ Active Directory & DHCP configurations
- 🌍 Routing & Remote Access settings
- ✅ Successful client connection to the domain
- 🛠️ Troubleshooting commands and their outputs

## 📚 Lessons Learned
- 🏗️ The importance of correctly configuring DNS for domain environments
- 🔄 How to set up and troubleshoot DHCP and NAT for client connectivity
- 🖥️ Using PowerShell for efficient server management and troubleshooting

## 🚀 Future Improvements
- 🤖 More Complex Network Topology: Move beyond a simple flat network. Implement subnets, VLANs, routing, and firewalls to simulate a more realistic enterprise environment.
- 🔥 Firewall Configuration: Set up and configure firewalls (Windows Firewall, or even virtualized pfSense or OPNsense) to control network traffic and practice security hardening.
- 🔎 Expanding the lab to include a SIEM tool for security monitoring
- 🏛️ Implementing Group Policy Objects (GPO) for policy enforcement

---
*This project showcases my problem-solving skills and foundational knowledge in Windows Server administration and networking.* 💡


