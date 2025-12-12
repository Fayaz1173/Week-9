An IP Address (Internet Protocol Address) is a unique numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. It serves two main purposes:

1. Identifying a device on the network.
2. Locating the device to enable communication with other devices over a network like the Internet.

## What Is IP (Internet Protocol)?

The **Internet Protocol** is a set of rules for how data is sent and received over the internet.

It ensures that:

1. Data packets know **where they’re going** (destination IP),
2. And **where they came from** (source IP).

Every time you browse a website, send an email, or ping a server:

- Your device **uses IP** to identify itself.
- The website’s server **uses IP** to send the reply back.

An **IP address** can be classified in **different ways**, depending on **what** we’re talking about:

1. **Based on scope or reachability** → Public, Private, Loopback, etc.
2. **Based on how it’s assigned** → Static or Dynamic.
3. **Based on protocol version** → IPv4 and IPv6.
4. **Special-purpose IPs** → Broadcast, Multicast, etc.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/39c91257-3eb1-4d7a-8b2c-1c9b4bcffdaf" />

### Public IP Addresses

A Public IP address is assigned to every device that directly accesses the internet. This address is unique across the entire internet. Uniqueness & Accessibility are its key characteristics & are assigned by Internet Service Providers. When you connect to the internet through an ISP, your device or router receives a public IP address. These addresses can be static or dynamic.

### Private IP Addresses

Private IP addresses are used within private networks and are not routable on the internet. This means that devices with private IP addresses cannot directly communicate with devices on the internet without a translating mechanism like a router performing Network Address Translation (NAT). These are only required to be unique within their own network & are used for communication between devices within the same network

- **Defined ranges for IPv4:** 10.0.0.0 to 10.255.255.255, 172.16.0.0 to 172.31.255.255, 192.168.0.0 to 192.168.255.255
- **Defined ranges for IPv6:** Addresses starting with FD or FC

### IPv4

This is the most common form of IP Address. It consists of four sets of numbers(octets) separated by dots. This format can support over 4 billion unique addresses. Each octet represents eight bits, or a byte, and can take a value from 0 to 255. This range is derived from the possible combinations of eight bits (28 = 256 combinations).
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/598d50c3-6d46-4d78-9c41-87986047480a" />

<img width="800" height="350" alt="image" src="https://github.com/user-attachments/assets/383aad83-a698-452b-9493-be6b929e40a1" />


### IPv6:

IPv6 addresses were created to deal with the shortage of IPv4 addresses. They use 128 bits instead of 32, offering a vastly greater number of possible addresses. These addresses are expressed as eight groups of four hexadecimal digits, each group representing 16 bits. The groups are separated by colons.

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/162164fb-81b4-470f-91c0-5ba1712e2550" />


| Feature | IPv4 | IPv6 |
| --- | --- | --- |
| Address Size | 32 bits | 128 bits |
| Format | Decimal | Hexadecimal |
| Address Space | 4.3 billion | 340 undecillion |
| Header Size | Variable | Fixed (40 bytes) |
| Security | Optional (IPsec) | Built-in IPsec |
| NAT Required | Yes | No |
| Auto Configuration | DHCP | SLAAC (Stateless Address Auto Configuration) |
| Fragmentation | Sender and router | Sender only |
| Routing | Complex | Simplified |
| Broadcast | Yes | No (uses multicast instead) |

### Static IP Addresses

- Static IP Addresses are permanently assigned to a device, typically important for servers or devices that need a constant address.
- Reliable for network services that require regular access such as websites, remote management.

### Dynamic IP Addresses:

- Temporarily assigned from a pool of available addresses by the Dynamic Host Configuration Protocol (DHCP).
- Cost-effective and efficient for providers, perfect for consumer devices that do not require permanent addresses.

### **Unicast Address**

In unicast, data is sent from one sender to one specific receiver identified by a unique IP address. It is the most common type of communication used in networks. Its Purpose is One-to-one communication.

- **Example:** Sending an email or loading a webpage - your computer directly communicates with a specific server.
- **Use Case:** Regular web browsing, file transfers (FTP), email (SMTP), etc.

### Broadcast Address

In broadcast, a message is sent from one device to all devices in the same network segment. Every device in the network receives and processes the broadcast message. Its Purpose is One-to-all communication within a network.

- **Example:** An ARP (Address Resolution Protocol) request uses broadcasting to find a device’s MAC address on the local network.
- **Use Case:** Network discovery, DHCP requests, ARP queries
