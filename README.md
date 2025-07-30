# Cybersecurity-beginner-level-tasks

This project involved performing basic yet crucial security assessments on a sample vulnerable website to understand and identify common web application flaws. As a part of my internship, I carried out 3 main tasks:

Port Scanning

Brute Force Directory Enumeration

Network Traffic Interception

Each task helped me strengthen my hands-on skills in identifying potential attack surfaces and understanding how attackers exploit them.

Task 1: Port Scanning Objective: To identify open ports that might expose services vulnerable to attack.

Tools Used: Nmap

Steps: Ran the command: nmap -Pn testphp.vulnweb.com

Found port 80 (HTTP) open.

Impact: Port 80 uses unencrypted HTTP, which is vulnerable to eavesdropping and data interception.

Mitigation: Websites should avoid using HTTP for anything sensitive. Switching to HTTPS ensures data like passwords or personal info stays private and secure during transmission.

Task 2: Brute Force Directory Enumeration Objective: To Discover hidden directories that could expose sensitive files or functionalities.

Tools Used: Gobuster

Steps: Ran: gobuster dir -u http://testphp.vulnweb.com/ -w /usr/share/wordlists/dirb/common.txt

Discovered directories like: Sensitive: /admin, /vendor, /cvs, /secured General: /images, /AJAX, /Templates, /Flash

Impact: Exposed directories like /admin or /secured could be exploited if not properly protected, leading to unauthorized access or information leakage.

Mitigation: It’s important to hide or restrict access to such folders. Only authenticated users should be allowed in. If a folder isn’t needed publicly, it shouldn’t be visible at all.

Task 3: Network Traffic Interception Objective: To Capture and analyze credentials being transmitted during login.

Tools Used: Wireshark

Steps: Started Wireshark and selected the appropriate network interface. Opened the site’s login page: http://testphp.vulnweb.com/login.php Entered test credentials and submitted the form. Captured the network packets and located the plaintext username and password in the HTTP request.

Impact: The login data was visible in plain text due to lack of encryption. Any attacker on the same network could easily steal these credentials.

Mitigation: Websites must use HTTPS for login pages. Sending usernames and passwords without encryption is risky — it’s like writing your password on a postcard. We need sealed envelopes (encryption) instead.
