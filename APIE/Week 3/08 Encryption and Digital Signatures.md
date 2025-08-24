# 08 Encryption and Digital Signatures

## Encryption through Public Key Cryptography
This process allows a sender (A) to send a secure, encrypted message to a recipient (B).
### Process Flow
1.  **Key Generation:** B generates an RSA key pair (a public key and a private key).
2.  **Key Distribution:** B releases their **public key** but keeps the **private key** in a safe, secret place.
3.  **Key Acquisition:** A obtains B’s public key.
4.  **Encryption:** A encrypts the data using B’s public key.
5.  **Transmission:** A sends the encrypted data to B.
6.  **Decryption:** B uses their own private key to decrypt the data and read the original message.

> By encrypting data with the recipient's (B's) public key, only B, who holds the corresponding private key, can decrypt it. This ensures secure communication over a network.

### Key Considerations
There are two important challenges to consider:
-   **Public Key Authenticity:** How can A be certain that the public key they obtained truly belongs to B? A malicious actor could swap the key, leading to a security breach.
-   **Private Key Security:** How can B keep their private key safe from loss or theft? If the private key is compromised, the security of the entire system fails.

## Digital Signatures through Public Key Cryptography
Digital signatures are used to verify the authenticity and integrity of a digital document, much like a handwritten signature. They help answer questions like:
-   Is this email really from the person listed in the "From" field?
-   Has this document been tampered with since it was sent?
### Process Flow
1.  **Key Generation:** The sender (A) generates their own RSA key pair (public and private).
2.  **Key Distribution:** A releases their **public key** and keeps their **private key** secret.
3.  **Signing:**
    - A creates a unique digital fingerprint of the document, called a **digest**.
    - A encrypts this digest with their own **private key**. This encrypted digest is the **digital signature**.
4.  **Transmission:** A sends the original document along with the digital signature to B.
5.  **Key Acquisition:** B obtains A’s public key.
6.  **Verification:**
    - B uses A's **public key** to decrypt the signature and retrieve the original digest.
    - B independently generates a new digest from the document they received.
    - B compares the two digests. If they match, B can be sure the document is genuinely from A and has not been altered.

> **Key Reversal in Signatures:**
> Notice the difference from encryption:
> - **Encryption**: Encrypt with **public key**, decrypt with **private key**.
> - **Digital Signature**: Sign (encrypt) with **private key**, verify (decrypt) with **public key**.
> This ability to use either key for encryption is a unique feature of RSA.
