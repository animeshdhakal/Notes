# 02 Client-Server Model

## Overview
- The **client-server model** simplifies Internet applications by dividing roles:
  - **Client** → Requests the service.
  - **Server** → Provides the service.
- The client requests a service at a known **IP address + port number**.
- Example:  
  - Web server listens on **port 80**.  
  - Browser (client) sends request → server sends page (response).  
- After the response, the **TCP connection closes**.

✅ This simplicity contributed to the **rapid growth of the Internet**.

## Server Processing
- A server handles requests from **multiple clients**.  
- Problems with sequential processing:
  - Clients may wait in a queue.
  - Server resources are underutilized if it can handle multiple requests.
  
## Cloning Mechanism
- To improve performance, servers use **clones** (process copies) to handle requests:
  1. Server waits at a port.
  2. Client A sends a request.
  3. Server creates a **clone** to handle Client A.
  4. Original server continues listening for new requests.
  5. Clone processes request → sends response → then terminates.

## Limitations
- If:
  - A clone takes too long, or  
  - Too many clients request service simultaneously →  
  → Many clones run at once → **system slowdown or failure**.
  
## Key Takeaway
- The client-server model’s simplicity made the Internet grow fast.  
- **Cloning & request distribution** help maintain smooth services.  
- However, resource limitations of servers remain a challenge.
