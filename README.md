# Security+ SYO-701 Digital-Certificates

## What are Digital certificates?
A digital certificate is a file or electronic password that uses public key infrastructure (PKI) and cryptography to probe and also verify the legitimacy of a device, server, or user. Organizations guarantee that only users and devices can connect to their networks with digital certificate authentication. Verifying a website's legitimacy to a web browser is another typical usage for digital certificates and is most commonly referred to as secure sockets layer or SSL certificates.

This includes identifying information about a device, including its Internet Protocol (IP) address or serial number, as well as information about the user, organization, or department. Digital certificates provide a copy of the certificate holder's public key, which must match a matching private key.
## Real Example of Digital certificate
<img width="1222" height="973" alt="Screenshot (38)" src="https://github.com/user-attachments/assets/c3861bba-cd79-46e9-9b4a-22cde63305b2" />


## This lab demonstrates how to create a self signed digital certificate
## Lab Steps
### 1. Generate Public/Private key-pair
```bash
openssl genrsa -out private.key 2048
```
### 2. Extract public.key from Private.key
```bash
openssl rsa -in private.key -pubout -out public.key
```
### 3. Make a CSR (certificate signing request)
```bash
openssl req -new -x509 -key private.key -out certificate.crt -days 365
```
##### In this command `x509` tells OpenSSL that instead of just creating a CSR, create x509 certificate.
###### After this OpenSSL will Ask you to share some information like Country name, Company name, Email etc. Just fill-up the Information and your certificate will be created.
### 4. View your certificate
###### After creation certificate will not be in human readable form so you can`t read the certificate info with just ``cat `` command. So type this command to view your certificate.
```bash
openssl x509 -in certificate.crt -text -noout
```
### 5. Verify your certificate
```bash
openssl verify -CAfile certificate.crt certificate.crt
```
## My Lab results:
### Key-pair Generation
<img width="1920" height="951" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/fe50b6b1-d105-4032-ae5d-24489e5feef9" />

### Extracting public.key
<img width="1920" height="957" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/d9b96478-d282-4fba-a524-03736e4e8f3e" />

### Making a CSR
<img width="1920" height="948" alt="Screenshot (35)" src="https://github.com/user-attachments/assets/4c544c04-df16-4396-ae97-7e1088c18575" />

### View certificate
<img width="1920" height="954" alt="Screenshot (36)" src="https://github.com/user-attachments/assets/2cc1cda5-cbee-4dba-8f14-25ef3a55cd8b" />

### Certificate verification
<img width="1920" height="948" alt="Screenshot (37)" src="https://github.com/user-attachments/assets/19b0e8a8-42c1-4882-bc3d-599191db79fe" />




