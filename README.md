# A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security.

## 💡This enterprise-level network project showcase a highly available and secure campus network using:-
* **🌀 Multi-Layer Switching(L3 Switches)**
* **🔁 HSRP Gateway Redundancy**
* **🚀 Dynamic Routing (EIGRP 100)**
* **🌐 DHCP + DNS Centralized Services**
* **🌎 NAT / PAT for Internet**
* **🛂 VLAN Segmentation + Security Controls**
* **🔐 Port Security**

### ⏳ Project Summary:-

| **Feature**         |    **Implementation**           |
|---------------------|---------------------------------|
|   🌎Network Type    |   Enterprise LAN + WAN + ISP    |
|   🛣️ Routing        |   EIGRP (AS 100)                |
|   🎗️ VLANs          |   10, 20, 30, 40, 50            |
|🚨High Availability  |   HSRP on COre Switches         |
| 🧩Services          |   DHCP + DNS                    |
| 🔐 Security         |   SSH, Port Security            |
|   🌐 NAT            |   WAN Internet via Edge Router  |

## 🔐 VLANs IP & HSRP Virtual Gateway Table:- 
| VLAN |   CoreSW1   |    CoreSW2    |        Subnet   |         VIP    |    Department |  
|------|-------------|---------------|-----------------|----------------|--------------|
| 10   |  10.10.10.1  | 10.10.10.2   |  255.255.255.0  | 10.10.10.254   | A1 & B1   |
| 20   |  10.10.20.1   | 10.10.20.2  |  255.255.255.0  | 10.10.20.254   |  A2 & B2   |
| 30   |  10.10.30.1   |  10.10.30.2  |  255.255.255.0  | 10.10.30.254  |  A3  & B3  |
| 40  |    10.10.40.1  |  10.10.40.2  |  255.255.255.0  |  10.10.40.254  | A4  & B4  |
|  50 |   10.10.50.1  | 10.10.50.2   |    255.255.255.0  |  10.10.50.254  | A5  & B5  |


## ⚙️ Technologies Used
### 🔌Hardware & Tools
* Cisco Catalyst 3560(Core) & 2960 (Access)
* Cisco 1941(ISP) 2911(EDGE) Routers
* Cisco Server-PT

## 🛂Protocols & 🔩 Configuration

|  **Technology**   |   **Purpose**  |
|--------------------|-------------|
| EIGRP           |     Dynamic Routing|
|  HSRP         |    Gateway Redundancy |
|  NAT/PAT    |     Internet Access  |
| VLAN + 802.1Q  |  Segmentation  |
|  Inter-VLAN SVI  | Layer-3 Switching  |
|    DHCP/DNS    |     Centralized Services |
|  Port-Security + SSH | Security |



## 📡 Core Features Explained

### 1️⃣🟢 High Availability with HSRP
* prevents network downtime (99.9% availability)
* **CoreSW1 Active: VLAN** 10, 20, 50
* **CoreSW2 Active: VLAN** 30, 40
  **🔄️ Automatic failover on link/device failure.**

### 2️⃣🔀 Inter-VLAN Routing on L3 Switch
* SVI Interface provide routing between VLANs
* No external router needed (Router-On-a-stick not used)

### 3️⃣🧩 Centralized DHCp + DNS
* DHCP & DNS hosted in VLAN 50
* Server IP: **10.10.50.3**

### 4️⃣🌏 NAT / PAT 
* EDGE router provides secure internet access via ISP
* WAN Network: 100.100.100.0/30


## Here are outputs of HSRP *Failover* "before & after" :-

### Before the HSRP failover
* **In these screenshots you can see how the Host/PC has got IP from DHCP**
* **How they are pinging with ISP**
* **And the most imp. "route"**

* VLAN-10 or 20
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.10'PC%20Otpt%20Before%20Act.%20chng.png
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.20's%20PC%20Otpt%20Before%20Act.%20chng.png

* VLAN-30 or 40
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.30's%20PC%20Otpt%20Before%20Act.%20chng.png
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.40's%20PC%20Otpt%20Before%20Act.%20chng.png

### Note:-
* See the difference between these output VLAN-10 or 20 has same route
* And VLAN-30 or 40 has same route in the **"tracert"** CMD

### Now after HSRP fail(forcefully shut down VLAN)
* VLAN-10 or 20 shut down in CoreSW1
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.10'PC%20Otpt%20After%20Act%20chng.png
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.20'PC%20Otpt%20After%20Act%20chng.png

* VLAN-30 or 40 shut down in CoreSW2
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.30'PC%20Otpt%20After%20Act%20chng.png
* https://github.com/rXchauhan/A-High-Availability-Multi-VLAN-Campus-Network-with-DHCP-DNS-NAT-Security/blob/5db15ec2a15742ed8b0120a5f8ce5d8594589122/03-%20ScreenShots/V.40'PC%20Otpt%20After%20Act%20chng.png

### Note:- 
* Now you can see in both case they are pinging with ISPs IP 100.100.100.1
* But the differnece is that route is change in both case because they have differnet-different Active & Standby in both case. 

## 🚀 Test the followinf:
* HSRP Active/Standby failover
* DHCP Auto IP Allocation
* Internet Ping via NAT
* VLAn Isolation & Inter-VLAN Communication

# 📌 If this project helped you, give it a ⭐ on Github!



    
