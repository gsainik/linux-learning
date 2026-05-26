# Networking Concepts Index

1. CIDR Range (Classless Inter-Domain Routing)
2. DNS Resolution and TCP Handshake

---

# CIDR Range (Classless Inter-Domain Routing)

A CIDR range consists of a base IP address, a slash (/), and a number. This number dictates how many bits are used for the network prefix. The fewer bits assigned to the network, the more bits left for devices (hosts), meaning a larger range of available IPs.
Formula: 
- The number of IP addresses available in a range is calculated using the formula \(2^{(32-\text{CIDR})}\). 

- (For IPv6, it is \(2^{(128-\text{CIDR})}\)).For example, a /24 range leaves \(32 - 24 = 8\) bits, allowing \(2^8 = 256\)

CIDR is a way to represent:
- an IP address
- and how many devices/networks belong to it


### Example

```text
192.168.1.0/24
```

Here:
- `192.168.1.0` → Network address
- `/24` → Number of bits used for network portion

---

### Why CIDR Exists

Earlier, networks used fixed classes:
- Class A
- Class B
- Class C

This wasted many IP addresses.

CIDR allows flexible network sizes.

| Before CIDR | Problem | CIDR Solution |
|---|---|---|
| Fixed Class A, B, C networks | Wasted many IP addresses | Flexible network sizing |
| Large unused address blocks | Poor IP utilization | Efficient allocation |
| Difficult routing management | Large routing tables | Better route aggregation |

---

## CIDR Format

```text
IP_ADDRESS / PREFIX
```

### Examples

```text
10.0.0.0/8
172.16.0.0/16
192.168.1.0/24
```

---

## Understanding `/24`

IPv4 address has 32 bits.

Example:

```text
192.168.1.0/24
```

Means:
- First 24 bits → Network part
- Remaining 8 bits → Host part

---

## Common CIDR Ranges

| CIDR | Subnet Mask | Total IPs | Usable Hosts |
|---|---|---|---|
| /8 | 255.0.0.0 | 16,777,216 | 16,777,214 |
| /16 | 255.255.0.0 | 65,536 | 65,534 |
| /24 | 255.255.255.0 | 256 | 254 |
| /25 | 255.255.255.128 | 128 | 126 |
| /26 | 255.255.255.192 | 64 | 62 |
| /27 | 255.255.255.224 | 32 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /29 | 255.255.255.248 | 8 | 6 |
| /30 | 255.255.255.252 | 4 | 2 |
| /32 | 255.255.255.255 | 1 | 1 |

---

### Example: `/24`

```text
192.168.1.0/24
```

### Range

```text
192.168.1.0    -> Network Address
192.168.1.1
192.168.1.2
...
192.168.1.254
192.168.1.255  -> Broadcast Address
```

### Usable Hosts

```text
192.168.1.1 - 192.168.1.254
```

---

## Network Address vs Broadcast Address

In every subnet:
- First IP → Network Address
- Last IP → Broadcast Address

These addresses cannot be assigned to devices.


# Network Connection Establishment Process

Before any data can traverse the OSI model's layers, your computer must:
1. Locate the server via DNS.
2. Establish a connection via a TCP handshake. 

These two essential steps convert a domain name into an active, reliable pathway for the actual data transmission.

## 1. DNS Resolution (The Digital Phonebook)

When you type a URL, your device cannot route traffic using letters.

It needs a numerical IP address.

Example:

```text
google.com -> 142.250.183.14
```

---

## DNS Resolution Flow

### Local Check

Your computer first checks:
- Browser cache
- OS cache
- Hosts file

If the IP already exists locally, DNS lookup stops here.

---

### Recursive Query

If not found locally, your device sends the request to a:

- Recursive DNS Resolver

Usually provided by:
- ISP
- Google DNS
- Cloudflare DNS

Examples:

```text
8.8.8.8      -> Google DNS
1.1.1.1      -> Cloudflare DNS
```

---

### Name Server Lookup

The resolver communicates with:

1. Root Name Servers
2. TLD (Top-Level Domain) Servers
3. Authoritative Name Servers

To find the exact IP address.

Example:

```text
google.com -> 142.250.x.x
```

---

### Caching and Return

The resolved IP address is:
- Returned to the browser
- Stored in cache for future requests

---

## DNS Flow Diagram

```text
Browser
   ↓
Local Cache
   ↓
Recursive Resolver
   ↓
Root Server
   ↓
TLD Server
   ↓
Authoritative DNS Server
   ↓
IP Address Returned
```

---

# 2. TCP Handshake (The Virtual Introduction)

Once the browser has the server’s IP, it must establish a reliable, connection-oriented session before sending the actual HTTP payload. 
This is handled by the Transmission Control Protocol (TCP) via a *3-Way Handshake*

TCP = Transmission Control Protocol

---

## Why TCP Handshake is Needed

TCP ensures:
- Reliable communication
- Ordered data transfer
- Error checking
- Connection establishment

---

## TCP 3-Way Handshake

### Step 1 — SYN  (Synchronize)
The client sends a SYN packet to the server to initiate communication, proposing an initial sequence number.

Meaning:

```text
"Can we start communication?"
```

---

### Step 2 — SYN-ACK (Synchronize-Acknowledge)
The server receives the SYN, acknowledges it, and responds with its own SYN and a matching acknowledgment number.
Server responds with:
- SYN
- ACK

Meaning:

```text
"Yes, I received your request."
```

---

### Step 3 — ACK (Acknowledge)
The client receives the SYN-ACK and sends back an ACK packet


Client sends ACK back.

Meaning:

```text
"Connection established."
```

---

## TCP Handshake Flow

```text
Client                  Server
   | ------ SYN ------> |
   | <--- SYN-ACK ---- |
   | ------ ACK ------> |
```

Connection is now established.

---

# Real Website Example

When opening:

```text
https://google.com
```

The process is:

1. DNS converts domain to IP
2. TCP handshake establishes connection
3. HTTPS communication starts
4. Browser receives webpage data

---

# Important Ports

| Protocol | Port |
|---|---|
| HTTP | 80 |
| HTTPS | 443 |
| DNS | 53 |

---

# OSI Layers Involved

| Process | OSI Layer |
|---|---|
| DNS | Application Layer |
| TCP Handshake | Transport Layer |
| IP Routing | Network Layer |

---

# Key Takeaway

Before data transfer begins:
1. DNS finds the server IP address
2. TCP establishes a reliable connection
3. Actual communication starts


# OSI Model (Open Systems Interconnection)

The OSI Model is a conceptual framework used to understand how data travels across a network.

Before any data can traverse the OSI model's layers, your computer must locate the server via DNS and establish a connection via a TCP handshake

It divides network communication into **7 layers**.

Each layer has a specific responsibility.

---

## Why OSI Model Exists

- Standardize network communication
- Help different systems communicate
- Simplify troubleshooting
- Separate networking functions into layers

---

## 7 Layers of OSI Model

| Layer Number | Layer Name | Main Function | Examples |
|---|---|---|---|
| 7 | Application | User interaction with network services | HTTP, HTTPS, FTP, DNS |
| 6 | Presentation | Data formatting and encryption | SSL/TLS, JPEG, ASCII |
| 5 | Session | Manages communication sessions | NetBIOS, RPC |
| 4 | Transport | Reliable data transfer | TCP, UDP |
| 3 | Network | Routing and IP addressing | IP, ICMP, Routers |
| 2 | Data Link | MAC addressing and frame transfer | Switches, Ethernet |
| 1 | Physical | Physical transmission of data | Cables, Signals, Hubs |

---