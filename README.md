Basic Network Scanning with Nmap
Project Overview
This project demonstrates basic network reconnaissance using Nmap (Network Mapper). The objective was to scan an authorized local network device, identify open ports and running services, perform operating system detection, and assess potential security risks.

The target was my own home Wi-Fi router.

Objectives

* Install and verify Nmap.
* Perform a basic network scan.
* Identify open ports and services.
* Detect service versions.
* Estimate the target operating system.
* Analyze potential security risks.
* Document findings and recommendations.

Tools Used
* Operating System: Parrot OS
* Scanning Tool: Nmap 7.98
* Target: Home Wi-Fi router (192.168.0.1)

Nmap Installation

Nmap was verified on the system using:
* nmap --version

If installation is required on a Debian-based Linux distribution:
* sudo apt update
* sudo apt install nmap

Scanning Methodology

Three scan types were performed against the authorized target.
1. Basic Network Scan
* nmap -T4 -oN nmap-scan.txt 192.168.0.1

This scan identified open TCP ports and their associated services.
2. Service Version Detection
* nmap -sV -T4 -oN service-versions.txt 192.168.0.1
This scan attempted to identify the services and software versions running on open ports.

3. Operating System Detection
* nmap -O -T4 -oN OS-detection.txt 192.168.0.1

This scan estimated the target device’s operating system based on its network responses.

* KEY FINDINGS
The scans identified the following services:
Port        Service        Finding
53/tcp       DNS         dnsmasq 2.90 identified
80/tcp       HTTP       HTTP response detected
443/tcp      HTTPS      HTTPS service detected
  
* Nmap also estimated that the target runs a Linux-based operating system, with a possible kernel range of Linux 4.15 to 5.19.


Some ports were reported as filtered during service detection.

Note: Different scan types reported slightly different port results. The findings are documented separately in the individual scan output files.

Security Analysis
A detailed assessment of the identified services, potential risks, and recommended security measures is available in security-analysis.md

Project Files
* nmap-public.txt - Basic scan results.
* service-public.txt - Service version detection results.
* OS-detection-public.txt - Operating system detection results.
* security-analysis.md - Security analysis and recommendations.
* screenshots/ - Screenshots documenting the scanning process.

Learning Outcomes
Through this project, I gained practical experience with:

* Network reconnaissance.
* TCP port scanning.
* Service and version detection.
* Operating system fingerprinting.
* Interpreting Nmap scan results.
* Identifying potential network security risks.
* Documenting security findings.

Ethical Considerations
All scanning activities were conducted against a device on my own home network with authorization.
Nmap should only be used on systems and networks that you own or have explicit permission to assess.

Conclusion
This project provided practical experience in using Nmap to examine network exposure, identify running services, and evaluate potential security concerns. It also strengthened my understanding of basic network reconnaissance and security assessment.
