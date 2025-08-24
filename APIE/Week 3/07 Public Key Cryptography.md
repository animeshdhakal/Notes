# 07 Public Key Cryptography

### The Importance of Cryptography
Public key cryptography is a foundational technology for the modern internet, enabling secure social and commercial activities like e-commerce. Along with TCP/IP and the World Wide Web, it's considered one of the internet's most crucial inventions.

### 1. The Predecessor: Symmetric Key Cryptography
This is the traditional method of encryption, where the same key is used for both encrypting and decrypting data.
*   **How it works:** A sender uses a secret key to encrypt a message. The receiver must have the *exact same* secret key to decrypt it.
*   **Analogy:** Placing a treasure in a safe, locking it with a key, and sending the safe. The receiver needs an identical key to open it.

#### The Core Flaw: The Key Distribution Problem
The main challenge with symmetric key cryptography is safely sharing the key.
*   You cannot send the key over an unsecured channel (like the internet) because an eavesdropper could intercept it, rendering the encryption useless.
*   Using a separate, secure channel (like physical mail) is impractical and undermines the goal of creating a self-contained, secure system on the internet.

### 2. The Breakthrough: Public Key Cryptography
This revolutionary method uses a pair of different but mathematically linked keys, solving the key distribution problem.
*   **Public Key:** This key is made available to everyone. It is used **only to encrypt** data.
*   **Private Key:** This key is kept secret by its owner. It is used **only to decrypt** data that was encrypted with its corresponding public key.

**The Workflow:**
1.  Anyone can find your public key and use it to encrypt a message to you.
2.  Once encrypted with your public key, the message can **only** be decrypted by your unique private key.
3.  Even if the encrypted message is intercepted, it is useless without the private key.

This system eliminates the need to share a secret key beforehand.

### 3. A Real-World Example: The RSA Cryptosystem
RSA is a widely used public key cryptosystem, forming the backbone of much of the internet's security.
*   **Named After:** Its three inventors (Rivest, Shamir, Adleman).
*   **How it Works:** Its security is based on the mathematical difficulty of **prime factorization**. It's easy to multiply two large prime numbers together, but extremely difficult and time-consuming (even for computers) to find the original prime factors from the resulting number.
*   **Key Length & Security:**
    *   Security is not absolute but relies on the massive amount of time required to break the encryption.
    *   Key length determines the strength. Early internet keys were 1024 bits, but **2048 bits** is now the standard to stay ahead of increasing computer power.
    *   **Trade-off:** Longer keys are more secure but require more processing time to encrypt and decrypt.

### 4. The Practical Application: Hybrid Cryptography
In practice, modern secure protocols like **HTTPS** (for websites) and **SFTP** (for file transfers) use a hybrid approach that combines the best of both methods.
1.  **Public Key Cryptography** is used first to securely exchange a temporary, single-use symmetric key.
2.  **Symmetric Key Cryptography** is then used with that temporary key to encrypt the actual data for the rest of the communication session.
This is done because symmetric encryption is much faster and more "light-weight" for encrypting large amounts of data, while public key encryption provides the unmatched security for the initial key exchange.