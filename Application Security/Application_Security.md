# Application Security
Application Security is the practice of protecting software applications from security threats, vulnerabilities, and attacks. It ensures that an application and its data remain safe from unauthorized access, misuse, hacking, and data breaches. Application security involves secure coding, proper authentication and authorization, data encryption, input validation, and regular security testing throughout the application’s development and deployment lifecycle.

![Logo](https://www.atatus.com/glossary/content/images/2021/06/Application-Security--1-.jpeg)

---

## Network Security
Network Security is the practice of protecting a computer network and its data from unauthorized access, attacks, misuse, or disruption. It ensures that data traveling across the network is safe and that only authorized users and devices can access network resources. Network security uses tools like firewalls, intrusion detection/prevention systems, encryption, and access control to prevent threats such as hacking, malware, and data interception.

### Symmetric Encryption
Symmetric encryption is an encryption method where the same secret key is used to encrypt and decrypt data. Symmetric encryption is fast and efficient, but key management is risky.
 

#### Benefits
- Fast performance – very quick for large data
- Simple to use – one key only
- Low computational cost
- Widely used in systems like AES, DES

#### Problems / Limitations
- Key sharing problem – secret key must be shared securely
- If the key is stolen, security is broken
- Not scalable for many users
- No built-in authentication


---

### Public Key Encryption
Public Key Encryption is a security method where data is encrypted using a public key and decrypted using a private key.  Example: RSA encryption

### Process

#### Key Pair Generation
- Two keys are created:
Public Key → shared with everyone
Private Key → kept secret by the owner
- Both keys are mathematically related

####  Encryption
- Sender encrypts the data using the receiver’s public key
- Once encrypted, data cannot be read without the private key

#### Decryption
- Receiver decrypts the data using their private key
- Only the private key can decrypt data encrypted with the public key

---

### Secure Network Protocol (SSL/TLS)
SSL/TLS is a security protocol that protects data during communication over a network.
Result: Secure, fast, and encrypted communication over the network.

### Process

#### Transfer Public Key
The server sends its public key (certificate) to the client.

#### Generate & Transfer Symmetric Key
- The client generates a symmetric session key.
- This key is encrypted using the server’s public key and sent to the server.

#### Use Symmetric Key for Encryption & Decryption
Both client and server use the same symmetric key to encrypt and decrypt data securely.

---

### Hashing
Hashing is a process of converting input data (any size) into a fixed-size unique value called a hash using a hash function. It is mainly used for data integrity and password storage. Hashing is one-way, fast, fixed-length, and secure for data protection.

### Characteristics of a Hash Function

#### Deterministic
Same input always produces the same hash output

#### Fixed Output Size
Output hash length is always the same, no matter input size
Example: SHA-256 → 256-bit output

#### Efficient
Hash value is generated quickly, even for large data

#### Preimage Resistance
It is computationally impossible to find the original input from the hash

#### Collision Resistance
It is extremely hard to find two different inputs that produce the same hash

---

### Common Hashing Algorithms
- MD5 – Fast but not secure (broken)
- SHA-1 – Weak, not recommended
- SHA-256 – Secure, widely used
- SHA-512 – More secure, longer output
- SHA-3 – Latest and highly secure
- bcrypt – Used for password hashing
- Argon2 – Very secure, modern password hashing
- Note: For passwords, always use bcrypt or Argon2, not MD5 or SHA-1.

---

### Digital Signature
A Digital Signature is a cryptographic technique used to verify the authenticity, integrity, and non-repudiation of a digital message or document. Result: Confirms message is genuine and unchanged.

### Process of Digital Signature

#### Key Pair Generation
- A public key and a private key are generated
- Private key is kept secret, public key is shared

#### Digital Signature Creation
- Message is first hashed
- The hash is encrypted using the sender’s private key
- This encrypted hash is the digital signature

#### Digital Signature Attachment
The digital signature is attached to the original message/document

#### Digital Signature Verification
- Receiver decrypts the signature using the sender’s public key
- Receiver hashes the received message
- If both hashes match, the signature is valid

---

### Digital Certificate
A Digital Certificate is an electronic document that proves the identity of a person, organization, or website and links it to a public key. It is issued by a trusted Certificate Authority (CA) and is used to enable secure communication (like HTTPS).
A digital certificate verifies identity and ensures secure, encrypted communication.

---

### VPN 
A VPN (Virtual Private Network) is a technology that creates a secure and encrypted connection over the internet, allowing users to send and receive data safely as if they were on a private network. VPN ensures privacy, security, and safe internet communication through encrypted tunnels.

### Key Components of VPN

#### Tunneling
- Creates a secure tunnel between client and server
- Protects data from being intercepted

#### Encryption
- Encrypts data so attackers cannot read it
- Uses symmetric and asymmetric encryption

#### Authentication & Authorization
- Authentication: Verifies user identity (username, password, certificates)
- Authorization: Controls what resources the user can access

#### Protocols and Types
##### Common VPN Protocols:
- OpenVPN
- IPSec
- L2TP
- PPTP (weak, outdated)
- WireGuard

##### Types of VPN:
- Remote Access VPN
- Site-to-Site VPN

#### VPN Client and Server
- VPN Client: User’s device (PC, mobile)
- VPN Server: Connects client to the private network securely

#### Public and Private Keys
- Used for secure key exchange and authentication
- Public key encrypts data, private key decrypts it

--- 

### Firewall
A Firewall is a network security device or software that monitors, filters, and controls incoming and outgoing network traffic based on predefined security rules. It acts as a barrier between a trusted internal network and untrusted external networks (like the Internet). A firewall protects your network by controlling what traffic is allowed in and out.

#### Key Points
- Blocks unauthorized access
- Allows legitimate traffic
- Protects networks from attacks like malware, hacking, and intrusions

#### Types of Firewalls
- Packet-Filtering Firewall – Checks each data packet against rules
- Stateful Inspection Firewall – Monitors active connections and traffic state
- Proxy Firewall – Filters traffic at the application level
- Next-Generation Firewall (NGFW) – Advanced, includes intrusion detection, application control