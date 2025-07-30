# Firewall-Rules-Testing-using-pfSense-in-Virtualized-Network-Environment
Securing virtual network using pfSense firewall with simulated attack scenarios
# 📘 Abstract

This project focuses on the implementation and testing of firewall rules using **pfSense**, an open-source firewall and router software, in a **virtualized network environment**. The primary objective is to simulate and analyze the behavior of network traffic when protected by pfSense under various configurations and potential attack scenarios.

The network setup is designed using **Oracle VirtualBox**, consisting of multiple virtual machines to replicate real-world conditions. The pfSense firewall acts as the central security appliance, configured with two network interfaces:
- An internal network connected to **Kali Linux** and **Windows 10** machines, representing internal users.
- An external bridged network connected to an **Ubuntu** machine, representing an external attacker.

The Ubuntu VM is used to simulate malicious activities such as **port scanning**, **brute force**, and **unauthorized access attempts**, while the pfSense firewall is configured with specific rules to detect and block such intrusions. Meanwhile, legitimate traffic from internal machines is allowed based on defined policies.

This project demonstrates the effectiveness of pfSense in securing internal systems, managing traffic, and preventing unauthorized access. It also provides insights into firewall rule management, network segmentation, and the practical implementation of cybersecurity controls in virtualized environments.


# 📘 Introduction

In today’s rapidly evolving digital landscape, ensuring robust network security is essential. Firewalls play a critical role in protecting internal systems from unauthorized access and external threats. This project focuses on designing, implementing, and evaluating firewall rules using **pfSense**, an open-source firewall and routing platform.

To simulate a real-world enterprise environment, a virtual network is created using **Oracle VirtualBox**, where multiple machines represent internal users and external attackers. The internal network includes **Kali Linux** and **Windows 10** systems, while the external network is simulated using an **Ubuntu** machine configured as the attacker.

Through this project, we aim to understand how firewalls manage traffic flow, prevent attacks, and enforce network segmentation. By configuring and testing rules on pfSense, we gain hands-on experience in **network security management** and **threat mitigation**.


# 🎯 Project Objectives and Tools Used

## ✅ Objectives

1. To set up a secure virtual network environment using **pfSense** as the firewall system.
2. To configure internal and external networks using **VirtualBox** virtual machines.
3. To simulate attacks from an external network (**Ubuntu attacker**) towards internal systems.
4. To implement and evaluate **firewall rules** that allow or restrict specific types of traffic.
5. To analyze the effectiveness of **pfSense** in detecting and blocking unauthorized access.
6. To document and report findings on **network behavior**, **rule impact**, and **system protection**.


## 🛠️ Tools and Technologies Used

| Tool/Technology     | Purpose/Use Case                                                  |
|---------------------|-------------------------------------------------------------------|
| **pfSense**         | Open-source firewall and router for traffic filtering and rule configuration |
| **Oracle VirtualBox** | Virtualization platform to host pfSense, Kali, Windows, and Ubuntu VMs |
| **Kali Linux**      | Internal machine used for security testing and traffic simulation |
| **Windows 10**      | Represents a regular user machine in the internal network         |
| **Ubuntu Linux**    | Used as the attacker machine on the external (bridged) network    |
| **Wireshark**       | Packet analysis and traffic monitoring tool                       |
| **Nmap**            | Network scanning and reconnaissance from the attacker machine     |
| **Netcat**          | For port testing and manual connection testing                    |


## Network Architecture
<img width="940" height="611" alt="image" src="https://github.com/user-attachments/assets/38c51b85-3be1-42f6-91f8-989f6d830d24" />


# 🧪 Lab Setup

This section explains how the virtual lab environment was built using VirtualBox and open-source operating systems to simulate a real-world network protected by pfSense.

---

## 🔗 Download Links

- **VirtualBox**: [Downloads – Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- **Windows 10**: [Download Windows 10](https://www.microsoft.com/software-download/windows10)
- **Kali Linux**: [Get Kali | Kali Linux](https://www.kali.org/get-kali/)
- **Ubuntu**: [Download Ubuntu Desktop | Ubuntu](https://ubuntu.com/download/desktop)
- **pfSense**: [Download pfSense Community Edition](https://www.pfsense.org/download/)

---

## 🎥 Installation Help

You can install each operating system and pfSense one by one using the tutorials available on my YouTube channel.

👉 **Watch Installation Videos Here:** [Visit My YouTube Channel](#)  
*(Replace `#` with your actual channel link if available)*

---

## 🔄 Next Step

After completing the VM installations, we proceed to configure the firewall settings in pfSense. The firewall configuration will be explained **step-by-step with screenshots** in the next section.


