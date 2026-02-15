# Network Security Assessment Report

## 1. Introduction

This report presents the findings of a security assessment performed on a test network. The assessment was conducted using Nmap for port scanning and Wireshark for traffic analysis.

## 2. Tools Used

- Nmap
- Wireshark

## 3. Scope

The assessment was performed on an authorized test system within a controlled lab environment.

Target IP: 10.129.49.248

---

## 4. Nmap Scan Results

### Open Ports Identified

| Port | Service | Version | Risk Level |
|------|----------|----------|------------|
| 22   | SSH      | OpenSSH 7.6p1 | Medium |
| 80   | HTTP     | Apache 2.4.29 | Medium |

### Observations

- SSH service is exposed to the network.
- Apache web server is running.
- Majority of ports are closed or filtered, indicating firewall usage.

---

## 5. Wireshark Traffic Analysis

The following protocols were observed:

- ARP
- TCP
- HTTP
- DNS
- DHCP
- ICMPv6

### HTTP Analysis

- HTTP GET requests observed.
- HTTP responses included 200 OK and 503 Service Unavailable.
- Traffic was transmitted in plaintext.

Risk:
Unencrypted HTTP traffic may expose sensitive data.

### DNS Analysis

DNS queries were observed for multiple domains.
This reveals browsing activity and external connections.

---

## 6. Identified Security Risks

1. SSH exposed on port 22  
   Risk: Brute-force attack possibility.

2. HTTP running without HTTPS  
   Risk: Data interception and sniffing.

3. Service Version Disclosure  
   Risk: Attackers can exploit known vulnerabilities in outdated software.

---

## 7. Recommendations

- Implement SSH key-based authentication.
- Disable root login over SSH.
- Enable HTTPS instead of HTTP.
- Regularly update Apache and OpenSSH.
- Configure firewall to restrict unnecessary access.
- Use intrusion detection systems (IDS).

---

## 8. Conclusion

The network security assessment successfully identified active services and potential vulnerabilities. While the firewall configuration appears effective, exposed services such as SSH and HTTP present moderate security risks. Implementing recommended controls will improve the overall security posture of the network.

---

## Disclaimer

This assessment was performed on an authorized test environment strictly for educational and internship purposes.
