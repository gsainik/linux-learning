
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

# 7 Layers of OSI Model

## OSI Layers

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

## OSI Layers and Data Units

| OSI Layer | Layer Name | Data Unit |
|---|---|---|
| Layer 7 | Application | Data |
| Layer 6 | Presentation | Data |
| Layer 5 | Session | Data |
| Layer 4 | Transport | Segment |
| Layer 3 | Network | Packet |
| Layer 2 | Data Link | Frame |
| Layer 1 | Physical | Bits |

---

### Explanation
```Layer 7, Layer 6, Layer 5``` are handled and taken care by Browser.

| Layer | Data Unit Meaning |
|---|---|
| Data | Actual application information |
| Segment | Transport layer divided data |
| Packet | IP-routed unit |
| Frame | Local network transmission unit |
| Bits | Binary signals transmitted physically |

---



### Data Encapsulation Flow

```text
Application Data
        ↓
Transport Segment
        ↓
Network Packet
        ↓
Data Link Frame
        ↓
Physical Bits
```


## Layer 7 — Application Layer

### Purpose
Provides network services directly to end users and applications.

### Responsibilities
- Web browsing
- Email communication
- File transfer
- DNS queries

### Protocols
- HTTP
- HTTPS
- FTP
- DNS
- SMTP

### Example
```text
Opening google.com in a browser
```

---

## Layer 6 — Presentation Layer

### Purpose
Formats, encrypts, and compresses data.

### Responsibilities
- Data translation
- Encryption/Decryption
- Compression

### Examples
- SSL/TLS
- JPEG
- PNG
- ASCII

### Example
```text
HTTPS encryption before data transfer
```

---

## Layer 5 — Session Layer

### Purpose
Establishes, maintains, and terminates communication sessions.

### Responsibilities
- Session management
- Authentication
- Connection control

### Examples
- NetBIOS
- RPC

### Example
```text
Maintaining a user login session
```

---

## Layer 4 — Transport Layer

### Purpose
Provides reliable or fast communication between systems.

### Responsibilities
- End-to-end delivery
- Error checking
- Flow control
- Segmentation


Large data is broken into smaller units called:

```Segments```

Example:

```text
Large File
   ↓
Split into multiple TCP Segments
   ↓
Sent over network

Then reassembled at destination.
```

### Protocols
- TCP
- UDP

### TCP
- Reliable
- Connection-oriented

### UDP
- Faster
- No delivery guarantee

### Example
```text
TCP used for banking applications
UDP used for video streaming
```

---

## Layer 3 — Network Layer

### Purpose
Handles routing and logical addressing.

### Responsibilities
- IP addressing
- Packet routing
- Path selection

### Protocols
- IP
- ICMP

### Devices
- Routers

### Example
```text
Routing packets from your laptop to Google server
```

---

## Layer 2 — Data Link Layer

### Purpose
Transfers frames within the same local network.

### Responsibilities
- MAC addressing
- Frame delivery
- Error detection

### Devices
- Switches

### Protocols
- Ethernet

### Example
```text
Communication between devices in the same LAN
```

---

## Layer 1 — Physical Layer

### Purpose
Physically transmits binary data.

### Responsibilities
- Signal transmission
- Cable communication
- Electrical/optical signaling

### Devices
- Hubs
- Cables
- Fiber optics

### Example
```text
Data traveling through Ethernet cable or WiFi signals
```


