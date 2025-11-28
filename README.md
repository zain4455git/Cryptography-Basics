<p align="center">
  <img src="https://raw.githubusercontent.com/Firas-Belarbi/Cryptography-Basics/main/Fondations%20de%20la%20Cryptographie%20Moderne.png" 
       alt="Cryptography Banner" width="100%">
</p>


<h1 align="center">Cryptography Basics — Summary Notes</h1>

<p align="center">
  <em>Foundations of modern encryption, written from the perspective of a cybersecurity student.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-brightgreen" alt="Status: Active">
  <img src="https://img.shields.io/badge/Topic-Cryptography-blue" alt="Topic: Cryptography">
  <img src="https://img.shields.io/badge/TryHackMe-Learning%20Path-red" alt="TryHackMe">
</p>





# Cryptography Basics — Summary Notes

Cryptography is a fundamental pillar of cybersecurity. It ensures **Confidentiality**, **Integrity**, and **Authenticity** of data in environments where attackers may intercept or manipulate information. These concepts shape how modern secure communication works across the internet.

Encryption is everywhere around us:
- Logging into platforms (e.g., TryHackMe login) uses encrypted passwords.
- SSH establishes encrypted tunnels.
- Online banking uses certificates to ensure you're talking to the legitimate server.
- File downloads use hash functions to guarantee file integrity.

---

## 1. Core Concepts in Cryptography

### **Plaintext**
The original readable data before encryption.

### **Ciphertext**
The unreadable encrypted data after applying encryption.

### **Cipher**
The algorithm used to transform plaintext into ciphertext.

### **Key**
A secret value that controls encryption and decryption.

### **General Encryption Model**

```
Ciphertext = Encryption(Plaintext, Key)
```

Depending on the system, decryption uses the same key (symmetric) or a different key (asymmetric).

---

## 2. Caesar Cipher (Shift Cipher)

The Caesar Cipher is one of the simplest classical encryption methods. It shifts each letter in the plaintext by a fixed number of positions.

Example:
- Plaintext: `TRYHACKME`
- Key = 3
- Ciphertext: `WUBKDFNPH`

Because the English alphabet has 26 letters, the cipher only has 25 possible keys → easily breakable by brute force.

### **Real Example Solved**
Given ciphertext:
```
XRPCTCRGNEI
```
Trying all shifts revealed:
```
ICANENCRYPT
```
when shifting letters back by 15 → **Key = 15**.

---

## 3. Symmetric Encryption

Symmetric encryption uses **the same key** for both encryption and decryption.

### **Pros**
- Very fast  
- Suitable for large data (files, disks, VPNs, Wi-Fi)

### **Cons**
- Key distribution problem  

### **Examples**

| Algorithm | Key Size | Status |
|----------|----------|--------|
| **DES**  | 56-bit   | Broken |
| **3DES** | 3 × DES  | Slow, deprecated |
| **AES**  | 128/192/256-bit | Global standard |

---

## 4. Asymmetric Encryption

Asymmetric encryption uses **two different keys**:

- **Public Key**  
- **Private Key**

This model solves the key distribution problem and enables:
- HTTPS  
- SSH  
- SSL certificates  
- Digital signatures  

### **Examples**
- **RSA** (2048–4096 bits)  
- **Diffie-Hellman**  
- **ECC** (strong with short keys)

---

## 5. Mathematical Foundations

### **5.1 XOR Operation (⊕)**

| A | B | A ⊕ B |
|---|---|--------|
| 0 | 0 |   0    |
| 0 | 1 |   1    |
| 1 | 0 |   1    |
| 1 | 1 |   0    |

Properties:
- `A ⊕ A = 0`  
- `A ⊕ 0 = A`  

Used in simple symmetric encryption:
```
C = P ⊕ K
P = C ⊕ K
```

---

### **5.2 Modulo (mod)**

Modulo returns the remainder of division.  
Modern crypto algorithms (RSA, DH, ECC) rely heavily on mod arithmetic with very large numbers.

---

## 6. Final Thoughts

Cryptography is a blend of:
- mathematics  
- logic  
- secure key management  
- protocol design  

These principles power the modern secure internet and will be the basis for the next topic:  
**Public Key Cryptography Basics**.

---
