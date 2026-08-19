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

Only secret to be kept in a *sound* cryptosystem is the key. 

>Problem of transmitting the encrypted code secretly, changes to transmitting the **key** secretly.

## Simple Symmetric Encryption / The Substitution Cipher

Substitution means substitution of each letter with another. 

>Substitution cipher is NOT secure at all!! 

Attacks include:
1. **Brute force** attack: Manually, all possible *keys* are tried  
    - Treated cipher as a *black box* 
    - Incorrect keys can give wrong conclusions, which might still make sense
    - Cypher is said to be *computationaly secure* against brute force attacks if testing all keys takes a long time 
    - Calculation of sample-space: if letter 'a' is assigned any random letter out of 26 alphabets (including a itself), there are 2^88w(26 factorial) possibilities!! excluding assigning all caps letters (a is B, instead of b)) 

2. **Letter Frequency Analysis**: Involves analysis of the cypher
    - If letter 'z' appears frequently, then 'z' is assigned to a 'frequently used letter in English' like e (11-13%), t (9%) etc and vica-versa. 
    - 'q' is *mostly* frequented by 'u' 
    - By chance, if word separators like blanks and spaces are found, short words like 'the' and 'and' van be de-crypted. 