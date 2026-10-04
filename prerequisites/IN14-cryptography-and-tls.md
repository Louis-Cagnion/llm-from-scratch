# IN14. Cryptography and TLS

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 7. Cryptography, security and cloud | MA26, IN09, IN12 | IN15 |

## Why this module

Downloading training data means speaking HTTPS, and in this project the TLS 1.3 client is written by hand (L39), along with every primitive it uses. Hashes also serve deduplication and prompt-cache keys, HMAC protects API keys and sessions, and secure random numbers protect tokens. This module teaches applied cryptography from the primitives to the full TLS 1.3 handshake.

## Objectives

After this module, you can implement and test the cryptographic primitives TLS 1.3 needs, explain the security goals they serve, avoid the classic implementation mistakes, and describe the TLS 1.3 protocol message by message.

## Competences evaluated

1. State the security goals (confidentiality, integrity, authenticity) and match each with the primitive that provides it.
2. Implement SHA-256 and SHA-1 by hand and check them against official test vectors; explain the properties of a hash function and why SHA-1 is broken for collisions.
3. Implement HMAC and HKDF, and explain their constructions.
4. Explain password hashing (PBKDF2, memory-hard functions) and why plain hashes are not enough.
5. Obtain secure random numbers from the operating system, and explain why a statistical generator such as PCG must never produce keys or tokens.
6. Implement AES-128 encryption by hand, and the CTR and GCM modes (with GHASH), and check them against test vectors.
7. Implement X25519 key exchange and explain Diffie-Hellman.
8. Verify RSA signatures (PKCS#1 v1.5 and PSS) and ECDSA P-256 signatures.
9. Encode and decode base64, parse ASN.1 DER structures and X.509 certificates, and validate a certificate chain (signatures, names, validity dates, trust anchors).
10. Write constant-time code for secret comparisons and explain timing attacks.
11. Describe the TLS 1.3 handshake (ClientHello, ServerHello, extensions, key schedule, certificate verification, Finished messages), the record layer and alerts.

## Notions, in learning order

1. **Security goals and threat models**: what cryptography can and cannot do.
2. **Hash functions**: properties, Merkle-Damgård construction, SHA-1, SHA-256, length extension attacks.
3. **Message authentication**: MACs, HMAC, key derivation with HKDF.
4. **Passwords**: salting, slow and memory-hard functions.
5. **Randomness**: entropy sources, CSPRNG, operating system interfaces.
6. **Symmetric encryption**: block ciphers, AES rounds (SubBytes, ShiftRows, MixColumns in GF(2⁸)), modes of operation, CTR, authenticated encryption with GCM.
7. **Key exchange**: Diffie-Hellman, elliptic-curve Diffie-Hellman, X25519.
8. **Signatures**: RSA PKCS#1 v1.5 and PSS, ECDSA, verification.
9. **Encodings and certificates**: base64, ASN.1 DER, X.509 structure, certificate chains, trust stores.
10. **Implementation safety**: constant-time code, test vectors, never inventing one's own cryptography for production.
11. **TLS 1.3**: handshake flow, extensions (SNI, ALPN, key share), key schedule, record protection, alerts, session resumption (overview).

## Practice

- Each primitive implemented in Python, then the performance-critical ones (SHA-256, AES-GCM) in C, all validated against official test vectors (NIST, RFCs).
- Parsing a real certificate chain downloaded with a browser, and verifying every signature in it.
- Following a TLS 1.3 handshake captured from a real connection, message by message, with the RFC open.

## Evaluation format

One practical session, about 4 hours: implement a primitive never implemented during learning or a variant of one, decode a provided ASN.1 structure, explain a TLS 1.3 handshake trace, and answer questions on security goals and attacks. Pass mark 100 %.

## References

- Dan Boneh and Victor Shoup, *A Graduate Course in Applied Cryptography* (free book).
- RFC 8446 (TLS 1.3), RFC 5869 (HKDF), RFC 7748 (X25519), FIPS 180-4 (SHA), FIPS 197 (AES), NIST SP 800-38D (GCM), RFC 8017 (RSA PKCS#1), RFC 5280 (X.509) (all free).
- Michael Driscoll, *The Illustrated TLS 1.3 Connection* (free website).
