# 06 Passwords

## Introduction to Secure Communication
- **Role of the Internet**: A platform for social activities requiring secure communication to handle sensitive information.
- **Focus**: Understanding the role of passwords in accessing computers, resources, and services online.

## Multi-User Systems and Time Sharing System (TSS)
- **TSS Mechanism**:
    - Developed alongside UNIX in the early Internet era.
    - Allows multiple users to share a single computer by allocating CPU time sequentially (e.g., user A, then B, then C, cycling back to A).
    - Advances tasks incrementally for simultaneous multi-user access.
- **Resource Management**:
    - Memory separation per user to prevent unauthorized access.
    - Data for inactive users (e.g., user C) stored on SSD/HDD for later retrieval (Fig. 2).
    - Ensures user A’s data is protected from access by user B without permission.

## Authentication and Authorization
- **Key Concepts** (Fig. 3):
    - **Authentication**: Verifies the identity of a user (“Who is this person?”).
    - **Authorization**: Grants access to specific resources based on identity.
    - Together, these processes form the “login” procedure.
- **Login Process**:
    - **Username**: Declares user identity.
    - **Password**: A secret string (letters/numbers) known only to the user to prove identity.

## Passwords and Internet Security Risks
- **Challenges with Internet-Based Authentication** (Fig. 4):
    - Passwords and usernames transmitted over the Internet as packets are vulnerable to interception by malicious users.
    - Data accessible only to specific users (e.g., user A) can also be intercepted during transmission.
- **Example: FTP (File Transfer Protocol)**:
    - Early Internet application for file transfers.
    - Risk of files being viewed by unauthorized parties during transfer.

## Evolution of Internet Security Awareness
- **Early Internet (circa 1990)**:
    - Primarily used for exchanging research papers and software within a university-based community.
    - Security was less critical due to a trusted, transparent environment where users could easily communicate.
- **Growth in the 1990s**:
    - As the Internet expanded into broader society, security became a priority.
    - **IETF (Internet Engineering Task Force) Mandate (1993)**:
        - Required all technical specifications to include “Security Considerations.”
    - Increased focus on securing communication channels and reexamining password-based authentication.

## Key Takeaways
- Passwords are critical for authentication and authorization in multi-user systems like UNIX with TSS.
- Internet communication introduces risks of data interception, necessitating secure channels.
- The 1990s marked a shift toward prioritizing security in Internet standards, driven by the IETF’s mandate.
