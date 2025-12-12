# **1. MAC Addresses**

A **MAC (Media Access Control) address** is a **unique 48-bit hardware identifier** assigned to every network interface card (NIC).

It operates at **Layer 2 (Data Link Layer)** of the OSI model and ensures proper local communication within a LAN.

### **1.1 Structure of a MAC Address**

A MAC address is written in hexadecimal, e.g.:

**AA:BB:CC:DD:EE:FF**

- **First 24 bits (AA:BB:CC)** → *OUI* (Organizationally Unique Identifier).
    - Identifies the manufacturer (Intel, Cisco, TP-Link, etc.).
- **Last 24 bits (DD:EE:FF)** → *Device-specific ID*.

Together, these ensure the NIC has a **globally unique address**.

### **1.2 Characteristics**

- **Burned-in** at the factory (but can be overridden in software).
- Used for **Ethernet communication** on LANs.
- Required for switch operation: switches build **MAC tables** to forward frames efficiently.
- Does not change across networks (unlike IP addresses, which are logical and changeable).

### **1.3 Importance in Networking**

- Enables frame delivery within a LAN.
- Used by protocols like **Ethernet, Wi-Fi, ARP**.
- Critical for device authentication on networks (e.g., MAC filtering on Wi-Fi routers).

---

# **2. ARP (Address Resolution Protocol)**

ARP is essential for IPv4 communication within LANs. It resolves a device’s **IP address to its corresponding MAC address**.

IPv4 cannot communicate directly over Ethernet; it must first convert logical addresses (IP) into physical addresses (MAC).

### **2.1 How ARP Works**

### **Step-by-Step Process:**

1. **Host A needs to send data to Host B** (IP: 192.168.1.10).
2. Host A checks its **ARP cache** for an entry.
3. If no entry exists, Host A broadcasts an **ARP Request**:
    
    *“Who has 192.168.1.10? Tell 192.168.1.5.”*
    
4. All devices on the LAN receive the request, but only Host B responds.
5. Host B replies with an **ARP Reply**:
    
    *“192.168.1.10 is at MAC XX:YY:ZZ:AA:BB:CC.”*
    
6. Host A stores this mapping in its ARP table and sends the data.

### **2.2 ARP Cache**

Devices save IP-to-MAC entries temporarily to reduce broadcast traffic.

Example entry:

```
192.168.1.10    XX:YY:ZZ:AA:BB:CC    dynamic

```

### **2.3 Limitations and Vulnerabilities of ARP**

ARP has **no authentication mechanism**.

Any device can reply to any ARP request, making ARP vulnerable to attacks:

- **ARP Spoofing/Poisoning**: attacker sends fake ARP replies to redirect traffic.
- Enables **MITM (Man-in-the-Middle)** attacks.
- Used for session hijacking or sniffing unencrypted traffic.

---

# **3. MAC Address Spoofing**

**MAC address spoofing** is the act of changing a device’s MAC address via software.

It overrides the factory-set address with a user-defined one.

### **3.1 How Spoofing Works**

Operating systems allow NICs to use a custom MAC address:

Examples:

- Linux:
    
    ```
    ifconfig eth0 hw ether XX:XX:XX:XX:XX:XX
    
    ```
    
- Windows: through network adapter settings.

The NIC uses the new MAC address for all outgoing frames.

### **3.2 Legitimate Uses**

MAC spoofing is not always malicious. Some valid reasons include:

- **Privacy**: hides your real hardware ID on public Wi-Fi.
- **Testing networks**: network engineers simulate multiple devices.
- **Bypassing MAC filtering**: if a router allows only specific MACs.
- **Continuity**: when replacing NIC hardware but needing the old MAC address.

### **3.3 Malicious Uses**

Attackers use spoofing for:

- **ARP poisoning attacks**
- **Impersonating another device** to gain unauthorized access
- **Evading MAC-based network security**
- **Tracking evasion** on public networks

Spoofing makes it difficult to rely on MAC filtering as a sole security measure.

---

# **4. Relationship Between MAC, ARP, and Spoofing**

### **ARP relies on MAC addresses**

ARP requires accurate MAC addresses to deliver packets locally. Without correct mapping, communication fails.

### **MAC spoofing disrupts ARP-based trust**

Since ARP has no authentication:

- A spoofed MAC address can answer ARP requests dishonestly.
- This leads to traffic redirection or interception.
- ARP poisoning becomes possible due to spoofing.

### **Network devices mitigate this using:**

- Dynamic ARP Inspection (DAI)
- DHCP Snooping
- Port security on switches
- Static ARP entries in sensitive environments

These measures validate ARP packets and help restrict spoofed MAC addresses.

---

# **5. Summary**

### **MAC Addresses**

- Unique hardware identifiers used for LAN communication.
- Essential for Ethernet switching.

### **ARP**

- Resolves IP addresses to MAC addresses.
- Broadcast-based and lacks authentication.
- Vulnerable to spoofing attacks (ARP poisoning).

### **MAC Spoofing**

- Software-based modification of MAC address.
- Has legitimate and malicious applications.
- Often used in network attacks that exploit ARP weakness.

Together, these technologies form the foundation of LAN communication—**but they also highlight the security challenges of older, trust-based network protocols.**
