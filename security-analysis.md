1. Overview
This project involved scanning my own home Wi-Fi router at IP address 192.168.0.1 using Nmap 7.98. The objective was to identify open ports, detect running services, estimate the operating system, and assess possible security risks.

3. Identified Open Ports and Services
Port 53 - DNS
Service: dnsmasq 2.90
Function: DNS translates domain names into IP addresses, allowing devices to access websites and other network services.
Security consideration: An improperly configured DNS service may allow unauthorized queries or DNS abuse. Access should be restricted to trusted network clients.

Port 80 - HTTP
Service: HTTP response detected. Nmap did not identify a specific software version.
Function: HTTP is used to communicate with web servers and web-based interfaces.
Security consideration: HTTP does not encrypt traffic. If sensitive information is transmitted over it, credentials or session data could be exposed. The scan alone does not establish whether this port hosts the router’s administration interface.

Port 443 - HTTPS
Service: HTTPS
Function: HTTPS provides encrypted communication between clients and web servers.
Security consideration: HTTPS helps protect data in transit, but the TLS configuration and certificate should still be checked to confirm that encryption is properly configured.

5. Operating System Detection
Nmap estimated that the target device runs a Linux-based operating system, with a possible kernel range of Linux 4.15 to 5.19.
Device type: General purpose
Network distance: 1 hop
This is an Nmap estimate based on network responses, not definitive confirmation of the router’s exact operating system or firmware.

7. Additional Observations
The service scan identified dnsmasq version 2.90 on port 53.
The HTTP response included security-related headers such as X-Frame-Options, X-Content-Type-Options, and Strict-Transport-Security.
Some ports were reported as filtered during the service scan. This means Nmap could not determine whether they were open or closed because their traffic appeared to be filtered.
Different scan types reported slightly different port results. These findings should be interpreted according to the individual scan outputs.

9. Security Recommendations
Keep the router firmware and DNS software updated.
Restrict DNS access to trusted devices on the local network.
Use HTTPS for web-based administration and avoid transmitting sensitive information over unencrypted HTTP.
Use a strong router administrator password.
Disable services and management interfaces that are not required.
Review router firewall settings and restrict unnecessary inbound connections.

11. Conclusion
The Nmap scans identified DNS, HTTP, and HTTPS services on the target router. The operating system detection suggested a Linux-based system. The findings provide a basic understanding of the router’s network exposure and highlight areas that should be reviewed to improve security.
This assessment is based on authorized scanning of my own home network. The scan results do not, by themselves, confirm that the identified services are vulnerable.
