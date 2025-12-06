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


## Here I am explaning HSRP failover & more:-
* 

