
# **BranchLink Network Enterprise**

## Enterprise Network Design Using VLAN, OSPF, DHCP & Layer 3 Switching

### 📁 Project Overview

**BranchLink Network Enterprise** is a robust and scalable enterprise network simulation built using **Cisco Packet Tracer**. The project features two branch offices, each designed with **VLAN segmentation**, **Inter-VLAN Routing**, **DHCP for dynamic IP assignment**, and **OSPF** for dynamic routing between routers. Switch port configuration and trunking are applied to ensure proper VLAN propagation across access switches.

---

### 🧱 **Network Topology Summary**

* **2 Branch Offices** connected via routers
* **2 Multilayer Switches (MLSW1 & MLSW2)** handling Inter-VLAN Routing
* **2 ISR Routers (R1 & R2)** running OSPF for dynamic routing
* **8 Access Switches**
* **16 PCs**, dynamically assigned IPs via DHCP
* **OSPF Area 0** for router communication
* **VLANs with Trunk Links** between switches

---

### 🧩 **VLAN Configuration**

| VLAN ID | Department | IP Subnet       | Default Gateway | Color Code     |
| ------- | ---------- | --------------- | --------------- | -------------- |
| 10      | HR         | 192.168.10.0/24 | 192.168.10.1    | Light Cyan     |
| 20      | IT         | 192.168.20.0/24 | 192.168.20.1    | Bright Green   |
| 30      | Sales      | 192.168.30.0/24 | 192.168.30.1    | Light Purple   |
| 40      | Marketing  | 192.168.40.0/24 | 192.168.40.1    | Bright Yellow  |

> VLANs are implemented on access and trunk ports to segment traffic and enforce security.

---

### 🌐 **IP Addressing Scheme**

| Device    | Interface          | IP Address   | Subnet |
| --------- | ------------------ | ------------ | ------ |
| **R1**    | G0/0/0             | 192.168.1.1  | /24    |
|           | G0/0/1             | 192.168.12.1 | /24    |
| **R2**    | G0/0/0             | 192.168.2.1  | /24    |
|           | G0/0/1             | 192.168.12.2 | /24    |
| **MLSW1** | SVI/VLAN Interface | 192.168.1.2  | /24    |
| **MLSW2** | SVI/VLAN Interface | 192.168.2.2  | /24    |

---

### 🔄 **Dynamic Routing - OSPF**

* OSPF is implemented between **R1** and **R2** over network **192.168.12.0/24**
* Area: **0 (Backbone)**
* Enables **dynamic route advertisement** between branch sites

---

### 🔁 **Inter-VLAN Routing**

* Configured on **Multilayer Switches (MLSW1 & MLSW2)** using **SVIs**
* Ensures communication across VLANs within each branch

---

### 🧠 **DHCP Configuration**

* **DHCP services** are configured on Multilayer Switches to assign dynamic IPs to PCs
* Each VLAN is assigned its own **DHCP pool** with proper IP range and default gateway

---

### 🔌 **Trunking and Switch Port Modes**

* **Trunk Ports**: Enabled between access switches and MLSW for VLAN propagation
* **Access Ports**: Assigned to respective VLANs for end devices
* VLAN tags are preserved across switches via **802.1Q trunking**

---

### ⚙️ **Key Features**

* ✅ Logical Network Segmentation with VLANs
* ✅ Dynamic IP assignment using DHCP
* ✅ Inter-VLAN Routing via Layer 3 Switches
* ✅ OSPF Dynamic Routing across branch routers
* ✅ Trunk Port Configuration for VLAN propagation
* ✅ Static and Dynamic Routing Hybrid
* ✅ Fully Scalable Design for Enterprise Needs

---

### 🔐 **Security & Optimization**

* VLANs isolate broadcast traffic
* Gateway-on-a-stick Inter-VLAN Routing eliminated using MLS for efficiency
* OSPF provides faster convergence and automatic route updates
* DHCP avoids manual IP configuration errors

---

### 📂 File Structure

```
BranchLink_Network_Enterprise/
├── BranchLink Network Enterprise.pkt       # Cisco Packet Tracer file
├── README.md                    # Project documentation
```
---

### 🖼️ **Network Topology**

![BranchLink Network Topology](/Assest/BranchLink%20Network%20Enterprise.png)

---

### 🔧 **How to Test**

1. **Open** the `.pkt` file in Cisco Packet Tracer.
2. **Check VLANs**: `show vlan brief` on switches.
3. **Verify DHCP**: PCs should receive IPs automatically.
4. **Test Routing**:

   * Ping between VLANs inside the same branch (Inter-VLAN Routing).
   * Ping across branches (Inter-Branch via OSPF).
5. **View OSPF Tables**: `show ip route ospf` or `show ip protocols` on routers.

---

### 👤 **Author**

**Designed by:** Satyajeet Jena

**Date:** July 2025

**Tool:** Cisco Packet Tracer

---

### 📝 License

Free to use for **educational purposes**. Not intended for commercial deployment.

---