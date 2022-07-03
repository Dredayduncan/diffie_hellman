# Dart Diffie-Hellman
Pure Dart implementation of modular DH groups

## Usage
```
DhPkcs3Engine dhEngine = DhPkcs3Engine.fromGroup(18);
DhPkcs3Engine otherDhEngine = DhPkcs3Engine.fromGroup(18);

DhKeyPair keyPair = dhEngine.generateKeyPair();
DhKeyPair otherKeyPair = otherDhEngine.generateKeyPair();

print('Public Key: ${keyPair.publicKey}');
print('Private Key: ${keyPair.privateKey}');
print('Other public Key: ${otherKeyPair.publicKey}');
print('Other private Key: ${otherKeyPair.privateKey}');


print('Secret Key: ${dhEngine.computeSecretKey(otherKeyPair.publicKey)}');
print('Other secret Key: ${otherDhEngine.computeSecretKey(keyPair.publicKey)}');
```

## DH Groups

| Group ID | Modulus length | Strength range (in bits) |
|----------|----------------|--------------------------|
| 1        | 768-bit        | -                        |
| 2        | 1024-bit       | -                        |
| 5        | 1536-bit       | 90-120                   |
| 14       | 2048-bit       | 110-160                  |
| 15       | 3072-bit       | 130-210                  |
| 15       | 4096-bit       | 150-240                  |
| 17       | 6144-bit       | 170-270                  |
| 18       | 8192-bit       | 190-310                  |