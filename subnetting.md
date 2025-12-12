# **Subnetting**

Subnetting is the process of dividing a large network into smaller networks called subnets. Each subnet provides its own space for devices to communicate, improving network performance, security, and management.

**Example:** In a company, different departments (Sales, HR, IT) can have their own subnets, keeping their traffic separate and organized.

<img width="400" height="200" alt="image" src="https://github.com/user-attachments/assets/59bbccbc-f6b6-4508-9d6d-d5a37f27c50e" />

# Why Subnetting is Important

Let's consider a company that follows classful addressing, it has a **Class C network (192.168.1.0/24)** with **256 IP addresses**. It has three departments:
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/d93cc3ad-a6b9-449c-8189-a2b17ef9358c" />
# 

Without subnetting, all departments share the same network, and all **256 IP addresses** are available to everyone, which leads to:

- **IP Waste:** Only 80 devices used out of 256 addresses i.e 176 wasted.
- **Performance Issues:** All traffic floods the same network, slowing communication.
- **Security Risks:** Devices from different departments can access each other freely.

**With Subnetting**, we split the network into three subnets, allocating just enough IP addresses for each department:

| **Department** | **Devices** | **IPs Allocated (after subnetting)** |
| --- | --- | --- |
| Sales | 20 | 32 (`192.168.1.0/27`) |
| HR | 10 | 16 (`192.168.1.32/28`) |
| IT | 50 | 64 (`192.168.1.48/26`) |

By subnetting, we:

- **Efficient IP usage:** Only 112 addresses used, leaving space for growth.
- **Better performance:** Traffic stays within each subnet.
- **Improved security:** Each department is isolated.

# Key Concepts in Subnetting

### IP Addressing

An [**IP address**](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) is made up of different parts, each serving a specific purpose in identifying a device on a network. An IPv4 address consists of four parts called "octets," separated by dots (e.g., 192.168.1.1). It has two main sections:

- **Network Portion**: Identifies the network the device belongs to.
- **Host Portion**: Uniquely identifies a device within the network.

IPv4 addresses are divided into classes based on the length of the network and host portions:

- **Class A**: 8-bit network ID, 24-bit host ID.
- **Class B**: 16-bit network ID, 16-bit host ID.
- **Class C**: 24-bit network ID, 8-bit host ID.
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/9d08f9cb-60ef-4697-96b6-7413b5a1cb17" />

### What is a Subnet Mask?

A [**subnet mask**](https://www.geeksforgeeks.org/computer-networks/role-of-subnet-mask/) is a 32-bit number used in IP addressing to separate the network portion of an [**IP address**](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) from the host portion. It helps computers and devices determine which part of an IP address refers to the network they are present, and which part refers to their specific location or address within that network.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/23b8c092-8ef9-4e7d-a59f-1cea35c09fca" />

