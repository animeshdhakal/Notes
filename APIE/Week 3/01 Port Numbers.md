# 01 Port Numbers
### 1. Role of Port Numbers
- IP address + Port number = Uniquely identifies communication between applications.
- Applications use TCP/UDP with port numbers to establish reliable communication.
- Applications don’t need to manage congestion/flow; TCP handles it → **Internet transparency**.

### 2. Port Number Discovery
- **Initial idea (not used):** Systems would ask each other dynamically, e.g., “Which port is email?”
- **Actual method (used):** Fixed port numbers assigned to specific services worldwide.

### 3. Well-Known Port Numbers (0–1023)
Common Internet services use **system ports**:
- 20 → FTP (data transfer)
- 21 → FTP (control)
- 22 → SSH (secure remote login)
- 23 → TELNET (remote login, unencrypted)
- 25 → SMTP (email sending)
- 53 → DNS (domain name service)
- 80 → HTTP (web browsing)

### 4. Port Number Categories
- **0–1023 → System Ports (Well-known ports)**
- **1024–49151 → User Ports (Registered ports)** – For new applications; must register with IANA.
- **49152–65535 → Dynamic/Ephemeral Ports** – Temporary use by clients, released after session ends.

### 5. Management of Port Numbers
- Managed by **IANA** (part of ICANN).
- Applications can be configured to use custom ports (not always restricted to system port).

### 6. Client-Server Model
- One side provides service (server).
- Other side requests service (client).
- Communication established via **IP + Port** pair through TCP.