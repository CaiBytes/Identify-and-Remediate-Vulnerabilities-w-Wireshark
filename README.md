# Identify and Remediate Vulnerabilities with Wireshark

## Objective

The Identify and Redmediate Vulnerabilities project aimed to establish a controlled environment for detecting network vulnerabilities in Wireshark and offering remediation solutions, as well as creating a report for a client. The primary focus was to ingest and analyze packet captures within Wireshark mimicing real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security and defensive strategies.

### Skills Learned

- Advanced understanding of Wireshark concepts and practical application.
- Proficiency in analyzing and interpreting packets.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.
- Effective communcation of cybersecurity concepts.

### Tools Used

- Wireshark for capturing and examining network traffic.

## Report

#### A.	There were a variety of vulnerabilities found on 10.168.27.0/24 while employing Wireshark. 



A1. Hypertext Transfer Protocol (HTTP) protocol found using GET instead of POST. 

![Wireshark1](https://github.com/CaiBytes/Identify-and-Remediate-Vulnerabilities-w-Wireshark/assets/160355470/ff3c59e2-8fbc-4f2b-8464-bd19dac8bcf1)

A2. File Transfer Protocol (FTP) showing username and password in the clear. 

![Wireshark2](https://github.com/CaiBytes/Identify-and-Remediate-Vulnerabilities-w-Wireshark/assets/160355470/14803ff3-731c-45db-9366-df13e06a9df4)

A3. Using outdated Secure Sockets Layer (SSL) instead of the current Transport Layer Security (TLS) encryption.

![Wireshark3](https://github.com/CaiBytes/Identify-and-Remediate-Vulnerabilities-w-Wireshark/assets/160355470/275c6dc9-4023-47aa-a0f2-d2aa26b3344f)


A4. HTTP being utilized instead of encrypted Hypertext Transfer Protocol Secure (HTTPS).

![Wireshark1](https://github.com/CaiBytes/Identify-and-Remediate-Vulnerabilities-w-Wireshark/assets/160355470/24b22942-d1d0-4469-8fbe-46fb6354fea3)


#### B.	Potential Implications
B1. The GET HTTP request is an insecure way to send data over HTTP. With GET, the data is sent in-the-clear which allows an attacker to easily intercept and steal sensitive information, perform on-path attacks, or DNS hijacking. 

B2. FTP showing usernames and passwords in-the-clear could allow an attacker to access user accounts, view sensitive information, and possibly perform lateral movement or privilege escalation. 

B3. SSL was created in 1996 as a security feature to secure connections across networks; however, SSL was since deprecated and replaced by TLS. Using SSL poses a security risk as it supports old encryption technology and alert messages are unencrypted. This is another pathway to which an attacker could intercept data. 

B4. HTTP is unencrypted and sends communications in plaintext allowing attackers to intercept data, perform on-path attacks, or DNS hijacking.

#### C.	Mitigation Recommendations

C1.   To mitigate the risk to using GET, the only HTTP request used should be POST. Unlike GET, POST doesn’t store data in web server logs or browser history or send any data in-the-clear. Users should only utilize the HTTPS protocol which encrypts and verifies digital certificates. 

C2.  To mitigate the risk of FTP showing usernames and passwords in the clear, only File Transfer Protocol with TLS (FTPS) and SSH File Transfer Protocol (SFTP) should be used.

C3.  To mitigate the risk of using depreciated SSL, only current version TLS should be used. TLS uses strong, modern encryption and establishes and secures connections faster than SSL. 

C4. To mitigate the risk of HTTP, only HTTPS should be utilized. HTTPS establishes a secure connection before transferring data. 


