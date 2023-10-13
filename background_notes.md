# Notes

# Contents

- [Security by Design](#security-by-design)
- [Ethical Standards](#ethical-standards)
- [Deploying Web Apps to the Web](#deploying-web-apps-to-the-web)


# Security by Design

## OWASP Top Ten Risk Areas

https://owasp.org/www-project-top-ten/

1. CRYPTOGRAPHICALLY FAILIURE

save passwords? care if the hash should match

Hashing and matching rather than saving password in plain text

Hashing - hash function will take plain text input and turn into cipher text of some sort based on an algorithm, same input gives same output

Salt - added to hash function which randomises some characters in the hashed password

2. 

CAUTION WHEN USING OPEN SOURCE SOFTWARE

BROKEN ACCESS CONTROL

mkdirall what if there is a directory there with 0777? doesnt check if the directory exists

3.

INPUT VALIDATION AND DATA VALIDATION

0 or negative numbers for time, logging it all, expect minutes or hours but what if the input is very low, you can crash the system

## Permissions

- rwxrwxrwx

Read, Write, Execute, `-` represents no permission

owner (first three and so on), group, all others

ls -ld shows permissions 

0700 - owner, group, all others
7 is read and write for the owner
5 is read or traverse

chmod 750 [Filename] to change permissions
can recursively do it (chmod -r 750) for all files inside a directory
common to have group and all others the same number

## DevSecOps

Developer, Security, Operations

Security is not an afterthought but integral part of the development process

Role of security in traditional process is usually at the end

Everytime you change something, every single test is ran again, therefore security tests should be built in rather at the end. Rather than a separate team, this improves the continuous delivery rather than blocking the flow of elements through a pipeline

Testing alone is not enough but is a good start

Need an effective deployment pipeline to be compliant

Pipelines are automated processes to build, test and deploy the code and make sure its safe, deployment pipeline is the process of code from version control and make it readily available to users

Is the change of the code safe?
Can we learn from the mistakes?
Show your working!

Pipeline should include security tests but we should build the code to be secure before admitting it the pipeline

Unit Testing - method tests
Integration Testing - unit interacts with another
Acceptance/End-to-End Testing - testing how the software actually works 
Manual Testing  

## Why Bother?

Data is core to a business
Personal information about customers and staff
Legally obliged to secure data
Could ruin business

## Encryption

Essential part of keeping data safe

Plaintext into unreadable ciphertext to prevent unauthorised access

Uses mathematical algorithms with a unique key to scramble the data

Prime numbers?

Two types of encryption - 
* symmetric - same key for encryption and decryption
* asymmetric - both keys are different

### Symmetric Encryption

Problem is that how to share the key needed to decrypt the file or message that you encrypted

### Asymmetric Encryption

Mailbox, location is public but the owner has the key to read the messages

Generate private and public key using RSA algorithm, mathematically linked

Address is the public key
Start by exchanging public keys, giving addresses
Alice encrpyts it with the Bobs public key then Bob decrypts it using his private key

### Cryptography Concepts

HASH - chop and mix, returns fixed length, same input, same input

node crypto hash module, createHash algorithm sha256, argon2
input, digest into hexadecimal

**RAINBOW TABLE** - hash translation of the most common passwords

SALT - random value introduced into hash

salt is random hex, store salt and hash password

Timing attacks are attacks that abuses the time between operations

ENCRYPTION - always randomised

advanced encryption standard 256

DIGITAL SIGNATURE

sign with private key rsa-sha256 to make sure its not tampered with

### AtBash

A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
Z Y X W C U T S R Q P O N M L K J I H G F E D C B A 

Z NZIGRMR. HSZPVM, MLG HGRIIVW

A MARTINI. SHAKEN, NOT STIRRED

## Securing Files

Use AxCrypt to keep file encrypted at "REST" and in "TRANSIT"

- REST is on local computer
- TRANSIT is when sending file over

Windows encrypting has a key and you need the key to use the files. When sending the files over, it decrypts the files automatically and uploads them.

AxCrypt on the other hand makes sure that it is encrypted all the way.

AxCrypt costs money therefore,

Open source encryption tools:

7-zip (AES-256)
VeraCrypt
GnuPG
DiskCryptor

## HTTPS

Encrypts the data you communicate with the server

Server provides public key then you send data that is encrypted with the servers public key

## Common Attacks

SQL injection
DDoS
Cross Site Scripting
XSS

AWS WAF

# Ethical Standards

Some pointers to start:

***What are compliance frameworks, international standards, and protocols?***

- **Compliance Frameworks** - rules made by people that ensure legal, regulations, industry codes and organisational doctrines are met

- **International Standards** - ISO/IEC 12207 and ISO/IEC 15288 standards are the most important for software development and can be replaced by each other, both referring to the Software life cycle processes.

- **Protocols** - what to do in different scenarios

***What behaviour do these standards target?***

![gdps](/images/GDPR.webp)

***How do different standards differ e.g. how long data should be stored for? GDPR vs CCPA?***

![gdpr vs ccpa](/images/CCPA-VS-GDPR.png)

***What are the penalties for breaching standards, and who enforces them?***

*(look above)*

***Find a couple of case studies of companies breaching GDPR***

**Uber**

After hackers stole the personal information of 2.7 million Uber customers, the ridesharing company paid the attackers $100,000 in exchange for a pledge to destroy the data. Uber did not inform anyone of the breach for more than a year. It was this failure to notify customers and regulators, as well as the size of the breach, that resulted in a £385,000 fine.

The attackers gained access to the information by using “credential stuffing”, in which usernames and passwords have already been compromised, and the attacker simply tries them on a multitude of websites until they manage to gain access to an account. Once they had gained access, the attackers downloaded information including names, email addresses, and phone numbers. They also gained access to records of almost 82,000 drivers, the journeys they’d made and the fares they’d been paid.

In addition to the fine imposed by the ICO, the Dutch Data Protection Authority (DPA) also imposed their own fine of €600,000 (£532,000) as 172,000 Dutch customers were amongst those affected.

***How might the programs you have built so far, breach regulations?***

## Deploying Web Apps to the Web

Tools required:

- Git
- Docker
- flyctl (fly.io terminal tool)

### Fly.io

`flyctl launch --local-only` - generates docker file

docker build -t website .

docker run

`flyctl deploy --local-only`

### GitHub Actions

- CI/CD service provided by GitHub

[Back To Top](#notes)