# SSH Notes

SSH (Secure Shell) is a cryptographic network protocol used to securely access and manage remote computers over an unsecured network.
This was made as a replacement for older programs such as 
- telenet
- rlogin
- ftp

SSH encrypts all communication between server and user. This prevents
- eavesdropping
- password theft
- session hijacking

---

## Why SSH Is Important

SSH is important for 
- protecting login credentials
- enabling secure remote system administration
- encrypting transmitted data
- protecting from man-in-the-middle attacks
- supporting tunneling and port forwarding
- allowing secure file transfers such as SCP and SFTP

Without SSH, remote administration would be much less safe.

---

## How It Works

1. Client initiates connection to server on port 22
2. Server sends its public key to the client.
3. Client verifies server authenticity.
4. A secure encrypted session is established.
5. User authenticates (password or key-based).
6. Secure communication begins.

SSH uses:

- Symmetric encryption (session data)
- Asymmetric encryption (key exchange)
- Hashing (integrity checking)

---

## Authentication methods

### Password Authentication

- The user enters username and password
- Encrypted during transmission
- Less secyre

### Pub Key Authentication

Uses two types of keys
- Public which is stored on the server
- Private which is kept by the client

How this form of authentication works:
- The server checks if the client's public key exists in ```authorized_keys```.
- The client then proves it owns the matching private key.
- No password is transmitted.

Public Key Authentication is much more secure and harder to brute force

---

## Common commands

Connecting to a remote server
```
ssh username@ipaddress
```

Specify Port
```
ssh -p 2222 username@ipaddress
```

Specific private key
```
ssh -i privatekey.pem username@ipaddress
```

Key generation
```
ssh-keygen
```

Here is the recommended option for keygen
```
ssh-keygen -t ed25519
```

File transfer
```
scp file.txt username@ip:/path
```

---

## Lab Questions

1. myraptor

2. 169.139.243.218

3. 56.13.188.38

4. 30.167.206.91

5. harvey

6. 30.167.206.91
