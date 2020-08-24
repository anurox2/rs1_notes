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

## TCP Trace example
