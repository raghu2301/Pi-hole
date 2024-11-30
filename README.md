# Pi-hole
## Overview
Pi-hole is a network-level ad blocker designed to block advertisements and unwanted content across all devices connected to a network. It functions as a DNS (Domain Name System) sinkhole, filtering out requests to known advertising, tracking, and malicious domains before they reach your devices. Here's an overview:

**Key Features of Pi-hole:**
1.	**Ad Blocking:** Blocks ads across websites, mobile apps, and smart devices without requiring additional software on individual devices.
2.	**Privacy Protection:** Prevents trackers and malicious domains from collecting data.
3.	**Network-Wide Coverage:** Protects all devices on the network, including smartphones, tablets, smart TVs, and IoT devices.
4.	**Customizable:** Allows users to add or remove blocklists and whitelist specific domains as needed.
5.	**Lightweight and Efficient:** Designed to run on low-power devices, such as a Raspberry Pi, but also works on other hardware or virtual machines.
6.	**Monitoring and Analytics:** Provides a web-based dashboard with insights into DNS queries, blocked domains, and overall network activity.
   
**How Pi-hole Works:**
- **DNS Sinkholing:** Pi-hole acts as a DNS server, intercepting DNS queries from devices on your network. If the query matches a domain on the blocklist, Pi-hole prevents it from resolving, effectively blocking the content.
- **Default or Custom Blocklists:** By default, Pi-hole uses popular blocklists but allows users to add their own lists for enhanced customization.

**Benefits:**
- Reduces data usage by preventing unnecessary content from loading.
- Improves browsing speed by eliminating ads and trackers.
- Increases privacy and security by blocking malicious domains.

**Common Use Cases:**
- Home networks for ad-free browsing.
- Small offices to protect multiple devices.
- Enhancing security on IoT-heavy networks.

## Objective
Pi-hole is an open-source project, and its ease of installation and configuration makes it a popular choice for those looking to enhance their network's functionality and security.
How to setup a pi hole and start monitoring DNS requests while adding some network protection in our home network.

**Prerequisite:**
- Ubuntu Server
- VM

Update repository and library
```
sudo apt-get update && sudo apt-get upgrade -y
```

Change IP to static IP

**To Install Pi-hole**

One-Step Automated Install

```
curl -sSL https://install.pi-hole.net | bash
```

Alternative 1: Clone our repository and run
```
git clone --depth 1 https://github.com/pi-hole/pi-hole.git
cd "Pi-hole/automated install/"
sudo bash basic-install.sh
```

Alternative 2: Manually download the installer and run
```
wget -O basic-install.sh https://install.pi-hole.net
```
![image](https://github.com/user-attachments/assets/f0e66cc9-3f61-49cd-b651-8183df1635c1)

```
sudo bash basic-install.sh
```
![image](https://github.com/user-attachments/assets/64480b8c-5bea-4ef3-81e1-999f0ee8bc3d)

![image](https://github.com/user-attachments/assets/1ff66e2d-ff31-4154-a921-f5543e2788f1)

We got out Pi-hole Automated Installer

![image](https://github.com/user-attachments/assets/3446ed89-8a60-4617-853c-de623a0c93e0)

Press **OK**


For **Static IP Needed** press continue

![image](https://github.com/user-attachments/assets/399c5c5a-8981-4177-8beb-84f8ccc04333)


Select the **upstream DNS Provider**

![image](https://github.com/user-attachments/assets/64b74b7f-98c3-4c6d-afd3-f97dfa13e733)

Select **Yes** for **Blocklists**

![image](https://github.com/user-attachments/assets/69872854-3797-4302-8edd-6d26f80e26b3)


Press **Yes** in **Admin Web Interface**

![image](https://github.com/user-attachments/assets/813eb4d4-adc0-4bda-9e08-4306bf291450)

Press **Yes** for **Web Server**

![image](https://github.com/user-attachments/assets/1a75fa5b-834f-404e-8c7d-806e0f936406)

Press **Yes** for **Enable Logging**

![image](https://github.com/user-attachments/assets/6fb07084-da35-4052-a49f-012861fc8720)


Press **Continue** for **Select a privacy mode**

![image](https://github.com/user-attachments/assets/a24eba4c-6d87-4a98-b735-2b22a74f8ed7)

When Installtion is complete you will be provided with a link for **web interface** and **password**

![image](https://github.com/user-attachments/assets/4f2d3d17-b76e-46d2-b645-b5c610eeef31)

Save it for later use.

Last thing to do is
set our host to point to this pi-hole dns server.

On our host:
- Goto **network**
- Goto **change adapter setting**
- Click on **properties**

![image](https://github.com/user-attachments/assets/824dc735-99c5-48fb-a2b1-6a7cd245c116)

**Use the following DNS server addressess**
set the DNS to pi-hole DNS

Open the **Web Interface** of the **pi-hole**

![image](https://github.com/user-attachments/assets/d23e2a28-764d-4d86-bf12-f9cece3b008c)

Enter the **password** which was provided at the end of the installation of pi-hole

![image](https://github.com/user-attachments/assets/89e69782-04ba-4e65-aeed-4cb85d606256)

And log in

![image](https://github.com/user-attachments/assets/69f7bd94-2e8e-4408-98b0-c188db14626e)

This pi-hole dashboard.
It says 9 queries blocked.


Click on Adlist

![image](https://github.com/user-attachments/assets/e076d7d4-0ab2-4408-9562-a70483526eef)

This is where we can add additional locklist if we want pi-hole automatically block dns request for us.

For example there are some blocklist I can contain the websites which are known to host malware, we can copy that and paste in our pi-hole to have our pi-hole automatically block malicious website.


Click on query log

![image](https://github.com/user-attachments/assets/e78d82f5-e838-44f7-8425-6e04475b0401)


To see which domain were blocked or allowed

<img width="691" alt="image" src="https://github.com/user-attachments/assets/5266e398-6ee3-440d-b4e5-bfed797d19b4">







