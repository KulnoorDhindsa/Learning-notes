# Cryptography 
*Resources: Understanding Cryptography ~ Christof Paar and Jan Pelzl*

---
Cryptography ages back upto 2000 BC with earliest uses recorded in *scytale of Sparta* and the famous *Caesar cipher* of ancient Rome.

The most general term *cryptology* is divided into two branches:
1. **Cryptography**: Science of writing *secret writings* to hide messages.
    1. **Symmetric Algorithms**: Having encryption and decryption methods to convey secrets.
    2. **Asymmetric/Public-Key Algorithms**: Along with a secret key, there exists a public key with the user.
    3. **Cryptography Protocols**: Protocols to deal with applications having cryptographic algorithms.
        - e.g. TLS (Transport Layer Security, within every browser) 
2. **Cryptanalysis**: Science of *breaking* cryptosystems.
## Symmetric Cryptography
Symmetric Cryptography = Symmetric-key = Secret-key = Single-key schemes

*eavesdropping* is unauthorized listening.

>Strong encryption patterns look gibberish to malicious users eavesdropping onto our conversation !

|Important Variables|Names|
|-------------------|-----|
|`x`|Plaintext / Cleartext|
|`y`|Ciphertext|
|`k`|Key|
|`key space`|Set of all possible keys|