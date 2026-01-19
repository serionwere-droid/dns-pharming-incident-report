# Security Incident Report – DNS Pharming

## Section 1: Network Protocol Involved
DNS (Domain Name System) is a network protocol used to translate human-readable domain names into IP addresses that computers can understand.  
This incident involves pharming, where attackers redirect users to a malicious website in order to steal credentials and distribute malware.

## Section 2: Incident Documentation
1. A user’s browser initiates a DNS request to resolve yummyrecipesforme.com.
2. The DNS server responds with the legitimate IP address of the company website.
3. The browser initiates an HTTP request to yummyrecipesforme.com.
4. The compromised website prompts users to download a malicious executable file disguised as a browser update.
5. The downloaded malware slows down the user’s system.
6. The malware initiates a DNS request for greatrecipesforme.com.
7. The DNS server responds with the IP address for greatrecipesforme.com.
8. The browser is redirected and initiates an HTTP request to greatrecipesforme.com.
9. A security analyst creates a sandbox environment to analyze the suspicious website.
10. Network traffic is analyzed using tcpdump.
11. Malicious JavaScript code is discovered prompting users to download an executable file.
12. Investigation reveals the web server was compromised through a brute force attack by a former employee.
13. The attacker succeeded due to default administrator credentials and lack of brute force protections.

## Section 3: Recommended Remediation
To prevent brute force attacks, the organization should implement multifactor authentication (MFA), enforce strong password policies (minimum 12 characters with complexity), enable account lockout and rate limiting, and remove default credentials.

## Disclaimer
This report is based on a simulated lab scenario and does not involve real production systems.
