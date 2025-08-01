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

## Firewall Configuration:

Go to this link download the pfsense firewall: [Download pfSense Community Edition](https://www.pfsense.org/download/)
<img width="940" height="421" alt="image" src="https://github.com/user-attachments/assets/7aa918b4-13e6-4229-9784-9ae8299eef6f" />

After that open the VirtualBox. 

<img width="940" height="470" alt="image" src="https://github.com/user-attachments/assets/a0e287c0-cea3-471b-9213-6344fe15acf7" />

Then click on the New Button. Look like this.

<img width="940" height="607" alt="image" src="https://github.com/user-attachments/assets/9bb8f05d-81a2-43c8-8680-5075e9eddacf" />

After that fill the all details like Name of work , Path of folder where you want to store, select the ISO image, then edition , Type ,version also configure the hardware and hard disk.

<img width="940" height="603" alt="image" src="https://github.com/user-attachments/assets/0d8dce83-ff83-4d55-8415-75daf5fa2789" />

For the individual environment it was take default configuration like RAM 1gb hard disk 16 gb. 
Then click on the <b>finish button.</b>

<img width="940" height="604" alt="image" src="https://github.com/user-attachments/assets/24a25be7-5001-4f5e-9acb-eac951646388" />

After Click on the <b>setting Icon.</b>

<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/e5008c6b-a89e-4b6a-a2a9-832a663a4b71" />

And do some configuration in <b>network section.</b>

In the network section there are four Adapter option. So click on the first adapter and then enable it and click on attached to and select the Bridge Adapter. Because it adapter connecting to External network with WAN.

<img width="940" height="591" alt="image" src="https://github.com/user-attachments/assets/921a3bdd-9d4f-42ca-a241-af79b21d3c4c" />

Click on the <b>Adapter 2. </b>

Enable Network adapter and then click on the Attached to Internal Network. Because it is internal network form the adapter connect all internal Server and computer. Like kali Linux and Windows 10.

<img width="940" height="591" alt="image" src="https://github.com/user-attachments/assets/1a8cd6f2-65e1-4171-a6d8-a69a58412b6c" />

Then Click on the **start button** and start to **installation of Pfsense Firewall.**

<img width="940" height="304" alt="image" src="https://github.com/user-attachments/assets/cfe893bf-b474-4e30-a1d1-5054da60d565" />

Start the installation of Pfsense Firewall.

<img width="940" height="614" alt="image" src="https://github.com/user-attachments/assets/4de09e07-1fc9-48db-97f5-82678f80ee9d" />

Then comes on popup of **copyright and trademarks notices.** Click enter for **accept**.

<img width="940" height="621" alt="image" src="https://github.com/user-attachments/assets/03272d55-afbd-466d-9cf3-4fa8d23f1640" />

Then click and move **next.**

<img width="940" height="618" alt="image" src="https://github.com/user-attachments/assets/fcfe4b04-199b-438a-ab36-3df06d335835" />

Select UFS and click on **OK.**

<img width="940" height="613" alt="image" src="https://github.com/user-attachments/assets/7e21d411-b5ed-45ee-bb10-993d650e1fa0" />

Then click on **entire Disk.**

<img width="940" height="619" alt="image" src="https://github.com/user-attachments/assets/100b9e99-4ea2-47f4-92ff-4f35bb2c9eaf" />

Then popup partition Scheme. Then select **MBR Dos partitions** because all latest hard disk coming with MBR.

<img width="940" height="616" alt="image" src="https://github.com/user-attachments/assets/19411387-43ea-4848-9396-e38356ed291e" />

Then click on **Finish.**

<img width="940" height="614" alt="image" src="https://github.com/user-attachments/assets/1bc44e88-d8a7-4e97-a86f-c79695f0cea9" />

Then asking for the **commit** conformation. 

<img width="940" height="619" alt="image" src="https://github.com/user-attachments/assets/38ac5713-7866-448f-a2c5-54de72d866ee" />

Then Checksum verification it was take some second. 

<img width="940" height="610" alt="image" src="https://github.com/user-attachments/assets/eee249ff-05fe-4bdf-ac5a-281fe59f9c2c" />

Then Click on **reboot**. Once reboot complete you successful install the pfsense firewall. 

<img width="940" height="614" alt="image" src="https://github.com/user-attachments/assets/c8499a42-72e9-42b7-b93b-b97b5e18b11a" />

And now you pfsense install.

<img width="940" height="616" alt="image" src="https://github.com/user-attachments/assets/fde4ffaf-90d5-4079-a3b6-eeb83600b8a7" />

## Internal Server Configuration 

Now can go to the my server machine and try to access the Pfsense firewall in a Web.

But before that go the server machine and connect with internal network for pfsense firewall.

Go to kali machine click on the setting and move to Network setting and select Adapter 2 and Attached with internal Network.

<img width="940" height="587" alt="image" src="https://github.com/user-attachments/assets/cfcb6a31-bdc5-4906-b7a9-3a3074d0e277" />

Then start the kali machine. 

<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/f786f3c7-d1d9-4e45-88ca-63739d8a87f3" />

Now you can see my internal network connect with pfsense firewall LAN connection. So now I can access the pfsense firewall in web browser.

Pfsense default **login and password** credentials **admin:pfsense**

<img width="940" height="484" alt="image" src="https://github.com/user-attachments/assets/bd7893de-8fe3-46a8-831d-c46789299cd6" />

Now we have to do some pfsense setup and you don’t have to change anything simply move next.

<img width="940" height="470" alt="image" src="https://github.com/user-attachments/assets/a9c498e1-9ae1-4b1e-aa59-d7143689305a" />

So continue move next until you reached admin password section. In Step 2 you can see the password so you change the password here.

<img width="940" height="488" alt="image" src="https://github.com/user-attachments/assets/6853431a-891d-409a-b313-46666b9fbc75" />

Now you can see you successful configure the firewall and complete the firewall.

<img width="940" height="489" alt="image" src="https://github.com/user-attachments/assets/ac3432a5-897e-4ad8-8e9c-47588835e0ca" />

After click on the Finish you come to Status Dashboard. 

In this dashboard you can see the some many things like Name of pfsense and username system virtulization.

<img width="940" height="464" alt="image" src="https://github.com/user-attachments/assets/49ac91ad-883b-44a1-a977-54feec9a2a8b" />

Then go to the firewall section and set the Rules of firewalls.

<img width="940" height="376" alt="image" src="https://github.com/user-attachments/assets/5db7b7f8-a08c-42a9-aafe-55623fa73867" />

Click on the add button. 
Set the Rule which is allow the access the private network.

