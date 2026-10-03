# 03 — Computer Networks: TCP 3-Way Handshake, UDP & RFC 9110 HTTP

> **Track:** CS Fundamentals Level 1  
> **Module:** 03 — Computer Networks  
> **Format:** Real-Life Systems Mental Models + RFC Technical Invariants + High-Frequency MCQ Traps  
> **Target Velocity:** 60 Seconds per MCQ

---

## 🏛️ Module Overview: The 3 Core Pillars

```
┌────────────────────────────────────────────────────────────────────────┐
│                      NETWORKING CORE ARCHITECTURES                     │
├──────────────────────────┬─────────────────────────────┬───────────────┤
│ 1. TCP 3-Way Handshake   │ 2. TCP vs. UDP Protocols    │ 3. HTTP Specs │
│    SYN ➔ SYN-ACK ➔ ACK   │    Reliability, Framing &   │    RFC 9110   │
│    Sequence Number Sync  │    Congestion Controls      │    401 vs 403 │
└──────────────────────────┴─────────────────────────────┴───────────────┘
```

---

## 🤝 1. The TCP 3-Way Handshake (RFC 793 / RFC 9293)

### 🎙️ The Real-Life Analogy: The Military Walkie-Talkie Check
Imagine two radio operators, **Alice (Client)** and **Bob (Server)**, communicating over static-filled airwaves:
1. **Alice presses talk:** *"Bob, this is Alice. Do you hear me? (Over)."* $\implies$ **`SYN`**
2. **Bob hears Alice and responds:** *"Alice, I hear you loud and clear! Can you hear ME? (Over)."* $\implies$ **`SYN-ACK`**
3. **Alice confirms:** *"Bob, I hear you loud and clear too! Commencing mission briefing."* $\implies$ **`ACK`**

Both sides now have **$100\%$ mathematical certainty** that both the transmit ($\text{TX}$) and receive ($\text{RX}$) channels work in both directions.

---

### ⚙️ The Technical Sequence & State Machine

```
CLIENT (Active Open)                                             SERVER (Passive Open)
  │                                                                 │ [LISTEN]
  │──────────────── 1. SYN (Flags: SYN=1, ACK=0) ──────────────────►│
  │                  ISN_client = x                                 │ Allocates TCB buffer
  │                  State: SYN_SENT                                │ State: SYN_RCVD
  │                                                                 │
  │◄─────────────── 2. SYN-ACK (Flags: SYN=1, ACK=1) ───────────────│
  │                  ISN_server = y, ACK_num = x + 1                │
  │                  State: ESTABLISHED                             │
  │                                                                 │
  │──────────────── 3. ACK (Flags: SYN=0, ACK=1) ──────────────────►│
  │                  SEQ_num = x + 1, ACK_num = y + 1               │
  │                  (Can piggyback HTTP request data!)             │
  │                                                                 │
[ESTABLISHED]                                                 [ESTABLISHED]
```

#### Step-by-Step Packet Breakdown
* **Step 1 (`SYN`):** Client picks a random **Initial Sequence Number ($\text{ISN} = x$)**. Sends packet with `SYN = 1`, `ACK = 0`.
* **Step 2 (`SYN-ACK`):** Server acknowledges client's sequence number by setting $\text{ACK} = x + 1$. Server generates its own random **Initial Sequence Number ($\text{ISN} = y$)** and sets `SYN = 1`, `ACK = 1`.
* **Step 3 (`ACK`):** Client acknowledges server's sequence number by setting $\text{ACK} = y + 1$ and $\text{SEQ} = x + 1$.  
  *(Important Exam Fact: Step 3 is allowed to carry application data, e.g., the first `GET / HTTP/1.1` request!)*

---

### 🚨 Why a 2-Way Handshake Fails (The Half-Open Connection Disaster)

> **Exam Question:** *"Why can't TCP establish a connection using only 2 packets (`SYN` $\to$ `SYN-ACK`)?"*

**The Real-Life Problem: The Delayed Letter to the Bank.**  
Suppose you send a letter to open a bank account (`SYN`), but it gets delayed in the post for 3 weeks. You give up and open an account elsewhere. Three weeks later, the delayed letter finally arrives at the bank.  
- If a **2-Way Handshake** was used, the bank would read the letter, open an account for you, allocate memory/vault space, and consider the contract active (`ESTABLISHED`). But you are already gone! The bank wastes memory on a **Half-Open Phantom Connection**.
- In a **3-Way Handshake**, the bank replies with `SYN-ACK`. Because you never send the final `ACK`, the bank automatically drops the half-open connection after a timeout.

---

## 📦 2. TCP vs. UDP Protocols

### 🚚 Real-Life Analogy: Registered Postal Mail vs. Live Stadium Megaphone

| Feature | **TCP** (Registered Mail with Tracking) | **UDP** (Stadium Megaphone) |
| :--- | :--- | :--- |
| **Real-Life Scenario** | Buying a laptop online / Bank Wire Transfer | Live football commentary / Shouting in a crowd |
| **Delivery Model** | Every single box is signed for. If Box #2 drops off the truck, the carrier halts delivery and re-ships Box #2. | The commentator speaks continuously. If a loud plane flies over and you miss 2 words, the game doesn't pause. |
| **Pacing** | Delivery slows down if your driveway is full of snow (Congestion & Flow Control). | Blasts audio at constant speed regardless of who is listening. |

---

### ⚡ Technical Comparison Matrix

| Architectural Dimension | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| :--- | :--- | :--- |
| **RFC Standard** | RFC 793, RFC 9293 | RFC 768 |
| **Connection Paradigm** | **Connection-Oriented:** Requires explicit 3-way setup and 4-way teardown (`FIN`). | **Connectionless:** Transmits immediately with zero prior handshake. |
| **Data Framing** | **Byte Stream:** Continuous stream of bytes. No application message boundaries (packet segmentation handled by MSS). | **Datagrams:** Discrete message packets. Preserves application boundaries exactly. |
| **Reliability Mechanism** | **Guaranteed:** Checksums, Positive ACKs, Cumulative ACKs, Selective Repeat (SACK), and Automatic Retransmission (ARQ). | **Unreliable / Best-Effort:** No ACKs, no retransmission. Packets can be lost, duplicated, or arrive out of order. |
| **Flow & Congestion Control**| **Yes:** Sliding window ($rwnd$) prevents buffer overflow; Congestion Window ($cwnd$) prevents network collapse. | **None:** Transmits at whatever rate the application pushes to the socket. |
| **Header Overhead** | **$20 - 60\text{ Bytes}$** (Variable: 20 bytes fixed + optional fields like Window Scaling, SACK). | **Fixed $8\text{ Bytes}$** (`Source Port [16b]`, `Dest Port [16b]`, `Length [16b]`, `Checksum [16b]`). |
| **Typical Use Cases** | HTTP/HTTPS (Web), SSH (Terminal), SMTP (Email), FTP (File Transfer). | DNS (Port 53), DHCP (Port 67/68), NTP (Port 123), VoIP, Live Video Streams, Online Multiplayer Games. |

---

## 🌐 3. HTTP Protocol Status Codes (RFC 9110 Standards)

### 🚪 Real-Life Analogy: The Exclusive Nightclub & The Restaurant

```
               1xx: Informational (Hold on, processing)
               2xx: Success (Here is your order)
               3xx: Redirection (The party moved down the street)
               4xx: Client Error (YOU did something wrong)
               5xx: Server Error (WE screwed up in the kitchen)
```

---

### 🔥 The Single Biggest Exam Trap: `401 Unauthorized` vs. `403 Forbidden`

Imagine trying to enter a high-security research facility:

```
Scenario A (401 Unauthorized):
You walk up to the security guard with NO ID badge on your chest.
Guard: "I don't know who you are! Present your badge or log in."
👉 401 Unauthorized = AUTHENTICATION FAILURE (Identity Unknown).
   Response MUST include the `WWW-Authenticate` header challenge.

Scenario B (403 Forbidden):
You present a perfectly valid Employee Badge that scans correctly. 
Your identity is confirmed: "Kilani Sai Nikhil, Junior Engineer".
You try to open the Server Core Room door.
Guard: "I know exactly who you are, Nikhil, but you do NOT have permission to enter this room."
👉 403 Forbidden = AUTHORIZATION FAILURE (Identity Verified, Permission Denied).
   Re-authenticating with the same login will NEVER grant access!
```

---

### 🚨 502 Bad Gateway vs. 504 Gateway Timeout (The Restaurant Waiter)

In modern web architecture, users talk to a Reverse Proxy (like **Nginx** or an API Gateway), which forwards requests to a backend microservice (**Node.js / Python Flask**):

* **`502 Bad Gateway` (The Chef Threw a Broken Plate):**  
  The waiter (Nginx) walked into the kitchen (Node.js backend), but the backend crashed, closed the connection abruptly, or returned garbled/invalid HTTP headers.
* **`504 Gateway Timeout` (The Chef Froze):**  
  The waiter walked into the kitchen and ordered the dish. The waiter stood waiting for $30\text{ seconds}$, but the backend database was hung and never answered. The waiter returns to the customer saying: *"The upstream server took too long to reply."*

---

### 📋 High-Frequency RFC 9110 Status Codes Cheatsheet

| Code | Standard Name | Meaning | Real-Life Parallel |
| :---: | :--- | :--- | :--- |
| **`200`** | **OK** | Request succeeded; payload returned. | Food delivered to your table. |
| **`201`** | **Created** | POST request succeeded; new resource created. | New account or record created on disk. |
| **`204`** | **No Content** | Request succeeded, but response body is empty. | DELETE request successfully executed. |
| **`301`** | **Moved Permanently** | Resource permanently relocated; browser caches new URL. | Store permanently moved to a new address. |
| **`304`** | **Not Modified** | Client cached copy is still fresh (`ETag` matched). | "You already have the newest version, don't download again." |
| **`400`** | **Bad Request** | Malformed syntax, invalid JSON, missing required body. | Ordering food in an unreadable foreign language. |
| **`401`** | **Unauthorized** | Missing or invalid authentication token. | No ID card presented at the security checkpoint. |
| **`403`** | **Forbidden** | Valid credentials, but insufficient permissions (RBAC). | Presenting a valid student ID to enter the faculty lounge. |
| **`404`** | **Not Found** | The target URI does not match any server route. | Knocking on a door address that doesn't exist. |
| **`500`** | **Internal Server Error** | Unhandled exception crashed backend code. | The kitchen stove exploded. |
| **`502`** | **Bad Gateway** | Proxy received an invalid response from upstream backend. | Waiter received a broken plate from the chef. |
| **`503`** | **Service Unavailable**| Server temporarily overloaded or down for maintenance. | Restaurant closed for scheduled pest control. |
| **`504`** | **Gateway Timeout** | Upstream server failed to respond within timeout window. | Chef took 1 hour and never handed the dish to the waiter. |

---

## ⚡ 60-Second MCQ Trap-Detector

```
                       Quick MCQ Elimination Checklist
 ┌───────────────────────────┬─────────────────────────────────────────────────────────┐
 │ Exam Question             │ The Instant Elimination Rule                            │
 ├───────────────────────────┼─────────────────────────────────────────────────────────┤
 │ Step 2 Handshake Seq/Ack? │ Server sends seq = y, ack = x + 1. (Always increments!).│
 │ Can Step 3 carry data?    │ YES. The final ACK packet can piggyback application data│
 │ Fixed UDP Header Size?    │ Strictly 8 bytes (4 fields of 16 bits = 64 bits = 8B).  │
 │ DNS / DHCP transport?     │ UDP. (Low latency, single request-response).            │
 │ 401 vs 403 distinction?   │ 401 = Missing/Invalid login. 403 = Role forbidden.      │
 │ 502 vs 504 distinction?   │ 502 = Invalid response. 504 = Timed out waiting.        │
 └───────────────────────────┴─────────────────────────────────────────────────────────┘
```
