# Syllabus discussion

### Date: 08-17-2020

- Routing TCP/IP Vol 1

# IPv4 Subnetting

## Rules for subnetting

- The subnet binary bits cannot be all 1's or all 0's
- The host binary bits cannot be all 1's or all 0's
- The subnet mask should be contiguous 1's

---

| Class of IP       | Designation                        |
| ----------------- | ---------------------------------- |
| Class A addresses | 001.hhh.hhh.hhh to 126.hhh.hhh.hhh |
| Class B addresses | 128.001.hhh.hhh to 191.254.hhh.hhh |
| Class C addresses | 192.000.001.hhh to 223.255.254.hhh |
| Class D addresses | 224.000.000.000 to 239.255.255.255 |

---

<br> 
<!-- Line break -->

**Q.** How to identify the network and the host portion of an address using a mask?<br>

> Ex IP address - 129.18.128.12 and the mask is 255.255.0.0

---

To get the network IP address perform an AND operation between the binary values of the IP address and the mask

---

<br/>

### Date: 08-24-2020

## Address Resolution Protocol

- Ethernet Frame

  - Preamble: Syncs everything up.
  - Destination and Source address - MAC address. Ethernet doesn't know about IP address. MAC addresses are on the NIC (Network Interface Card).
  - Data Unit: Data and Source & Destination IPs

- Process:

  1. ARP requests the MAC address of an IP address
  2. Places that in a table.
     1. If the MAC address is unknown the host will send out an ARP request with a broadcast MAC address as the destination.
  3. The ethernet type field will be 0x806 designating it as an ARP type process.

- Proxy ARP is a security risk. Not used anymore.
- Gratuitous ARP to broadcast new ARP address.
- When a destination address is a FFF.FFF.FFF, every device will listen to it.

---

<br/>

### Date: 08-26-2020

## MAC address table

For switches, holds MAC addresses, VLANs, and ports on which the interfaces are connected.

1. Router gets an IP packet with source and destination IP address
2. Checks the destination IP address in its ARP table
3. Assembles the ethernet packet with DESTINATION and SOURCE MAC address.
4. Sends it the link.
5. If a switch is present, it'll check the MAC Address table
6. Forward the packet accordingly.

## Spanning Tree Protocol

> Root Bridge: Connects all the bridges. If a bridge cannot access a node directly, it goes through the root bridge.

> Root bridge negotiation: All the bridges send out their IDs, and the one with the lowest ID becomes the root bridge.

## VLANs

1. Allow you to take a switch and carve it into subnets, and keep them isolated.
