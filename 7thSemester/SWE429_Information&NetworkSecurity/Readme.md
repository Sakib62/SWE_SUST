<h1 align="center">Information and Network Security</h1>

**Book :**
- Cryptography and Network Security : principles and practice by William Stallings
- Introduction to Computer Security by Goodrich, Tamassia

[✅**Book Link**][book]

[book]: https://drive.google.com/drive/folders/1_IBMwGkua52g4yEUajKonqdwKZWEpMW8?usp=drive_link

[✅**Resource Link**](https://drive.google.com/drive/folders/104Afe-RU1yegZI9Ijhk8UV_w1tnpVhlA?usp=drive_link)

**Question :** [**Exam.md**](Exam.md)

<br><hr><br>

### Lecture-2

- The security of a system, application, or protocol is always relative to
    - A set of desired properties
    - An adversary (attacker) with specific capabilities
- **Security Goals (C.I.A)**
    - **Confidentiality:** Keeping information secret from all but those who are authorized to see it.
        - 2 dimensions for confidentiality: Secrecy and & Privacy
        - Tools of confidentiality - Encryption, Access Control, Authentication, Authorization, Physical Security
    - **Integrity:** Ensuring information has not been altered by unauthorized or unknown means.
        - 2 dimensions for integrity: data integrity & system integrity
        - Tools of integrity - Backups, Checksums, Data correcting codes
    - **Availability:** Data/information is available when required.
        - Tools - Physical protections, Computational redundancies
- **Additional security properties:**
    - Authenticity
    - Accountability/Non-repudiation
    - Anonymity
- **Security attacks**
    - Passive
        - Eavesdropping
        - Traffic analysis
        - Observe, analyze and then replay
    - Active
        - Masquerading
        - Modification
        - Denial-of-Service (DoS)

<br><hr>

### Lecture-3

- **10 Security Principles**
    1. Economy of mechanism
    2. Fail-safe defaults
    3. Complete mediation
    4. Open design [Kerckhoffs’s Principle]
    5. Separation of privilege
    6. Least privilege
    7. Least common mechanism
    8. Psychological acceptability
    9. Work factor
    10. Compromise recording
- **Access control mechanism**
    1. Access control matrices
    2. Access control lists
    3. Capabilities
    4. Role-based Access Control (RBAC)

<br><hr>

### Lecture-4

- Cryptosystem components
- Caesar cipher - shifting
-  **Symmetric key distribution**
    - Both sender & receiver has same secret key
    - For n parties, n(n-1)/2 keys
    - Fast & efficient but problem is key distribution
- **Public key distribution (asymmetric)**
    - Every person has private and public key
    - For n person: 2n keys
    - Secure but slower and larger key lengths
- **Combining both**
    - Public-key cryptosystems are often used in practice to exchange a shared secret key
    - Once exchanged, the shared secret key can be used for communication, encrypted with a symmetric encryption scheme
- **Digital Signature**
    - Public key crypto systems allow reversing the order in which encryption and decryption is carried out.
    - E<sub>PB</sub>(D<sub>SB</sub>(M)) = M
    - This concept is leveraged to create digital signatures.
- **Simple attacks on crypto system**
    - Man In The Middle (MITM)
    - Brute Force
        - Unicity Distance

<br><hr>

### Lecture-5

- Hash functions
- Message Authentication Code (MAC)
- **Digital Signature vs MAC**
- Digital Certificate
- Attack type
    - Dictionary Attack
    - Social Engineering
    - Pretexting
    - Baiting
    - Quid pro quo

<br><hr>

### Lecture-6

- Substitution cipher
    - Vigenère cipher
    - One-Time Pads
    - **Hill cipher**
- **Playfair Cipher**
- Block Cipher (e.g., AES, DES)
- **Block cipher modes:**
    - Electronic Codebook (ECB)
    - Cipher–block Chaining (CBC)
    - Cipher Feedback (CFB)
    - Output Feedback (OFB)

<br><hr>

### Lecture-8

- **Number theory:** GCD, Primality test, Modular Arithmetic, Euclid’s GCD, Multiplicative Inverse, Modular Exponentiation, Euler’s Theorem, Fermat’s Little Theorem, Repeated Squaring
- **RSA Correctness**
- RSA Determinism

<br><hr>

### Lecture-9

- **Elgamal cryptosystem**
- **Diffie-Hellman** key exchange protocol (DH protocol)
- Hash function - deterministic, one-way, and collision-resistant
- Hash function attack - Birthday attack, Rainbow Table attack