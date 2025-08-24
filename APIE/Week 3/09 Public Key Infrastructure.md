# 09 Public Key Infrastructure

## The Core Problem: Trusting Public Keys
Public-key cryptography is powerful, but it has a fundamental challenge: How do you verify that a public key truly belongs to the person or server you think it does? How do you correctly identify the owner?

## The Solution: Public Key Infrastructure (PKI)
PKI is the technical framework of policies, standards, and systems that solves the trust problem. It allows us to securely use public-key cryptography in the real world, such as on the internet.

## Key Components of PKI
### 1. Digital Certificates
A digital certificate is a data file that binds a public key to an owner's identity. It acts like a digital passport.
*   **Standard:** Certificates are typically created using the **X.509** international standard.
*   **Contents:**
    *   **Public Key:** The public key being certified.
    *   **Owner Information:** Details like name, email address, and most importantly, the domain name (for web servers).
    *   **CA's Digital Signature:** A signature from a trusted third party (the CA) that verifies the information is correct.

### 2. Certificate Authorities (CAs)
A Certificate Authority is a trusted entity responsible for managing digital certificates.
*   **Primary Role: Issuing Certificates**
    1.  A server owner generates a key pair (public/private).
    2.  They send their public key and owner information to a CA.
    3.  The CA vets and verifies the owner's identity.
    4.  The CA uses its own private key to digitally sign the certificate, proving its authenticity.
*   **Secondary Role: Revoking Certificates**
    *   If a certificate is compromised or no longer trustworthy, the CA revokes it and makes this information public.
*   **The Hierarchy & Chain of Trust**
    *   **Root CA:** The ultimate authority. Their certificates are pre-installed and trusted by default in browsers and operating systems.
    *   **Intermediate CA:** CAs whose certificates are issued by a higher-level CA (like a Root CA). They act as a middle-man.
    *   **Chain of Trust:** A browser trusts a server's certificate because it was signed by an Intermediate CA, which in turn was signed by a Root CA that the browser already trusts.

## How PKI Works in Practice: The HTTPS/TLS Handshake
1.  **Server Setup:** A web server obtains a digital certificate from a CA and installs it.
2.  **Client Connects:** Your browser requests access to the secure server.
3.  **Server Sends Certificate:** The server sends its digital certificate back to your browser.
4.  **Browser Verifies Certificate:** The browser performs two critical checks:
    *   **Trustworthiness:** It checks the CA's signature and follows the "chain of trust" up to a Root CA it already trusts.
    *   **Identity:** It verifies that the domain name in the certificate (e.g., `www.google.com`) matches the domain name it is trying to access.
5.  **Secure Key Exchange:** If verification passes:
    *   The browser generates a new, temporary **common key** (symmetric key).
    *   It encrypts this common key using the server's **public key** (from the certificate).
    *   It sends the encrypted common key to the server.
6.  **Decryption:** The server uses its **private key** to decrypt the message and retrieve the common key.
7.  **Secure Communication:** Both the browser and server now share the same common key. All subsequent communication is encrypted using this fast and efficient symmetric key. This secure connection is standardized as **TLS (Transport Layer Security)**.
