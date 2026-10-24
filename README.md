# Linux & Networking Security Lab

A hands-on cybersecurity learning project exploring Linux fundamentals, network configuration, routing, DNS, and connectivity troubleshooting in Ubuntu on Windows Subsystem for Linux 2 (WSL2).

## Project Overview

The goal of this project is to build practical Linux and networking skills relevant to cybersecurity and cloud security. Each lab documents the commands used, observed results, technical interpretation, and security considerations.

## Labs

| Lab | Topic | Skills Practiced |
|---|---|---|
| 01 | Linux Fundamentals | Terminal navigation, user identification, system information |
| 02 | Network Interface Investigation | IP addresses, interface states, network configuration |
| 03 | Routing Table and Gateway Connectivity | Routing tables, default gateway, ICMP testing |
| 04 | DNS Investigation | DNS queries, IPv4 records, resolver analysis |
| 05 | Network Connectivity Testing | HTTPS response headers, ping, connectivity troubleshooting |
| 06 | Security Analysis and Final Findings | Evidence review, security considerations, limitations |

## Tools and Technologies

- Ubuntu on WSL2
- Linux command line
- Bash
- `ip`
- `ping`
- `dig`
- `curl`
- Markdown documentation
- Git and GitHub (for project version control and publication)

## Key Findings

- Identified Linux network interfaces and their configured addresses.
- Inspected the routing table and identified the default gateway.
- Successfully tested gateway connectivity with no packet loss during the recorded test.
- Resolved two domain names using DNS queries.
- Received a successful HTTPS response from `example.com`.
- Compared DNS, ICMP, and HTTPS checks and documented their limitations.

## Security Perspective

This project focuses on foundational investigation and troubleshooting. Successful connectivity tests do not establish that a system is secure, and the labs do not claim to identify vulnerabilities without supporting evidence.

All tests were conducted from my own Ubuntu WSL2 environment against the documented destinations.

## Repository Structure

```text
linux-networking-labs/
├── README.md
├── labs/
│   ├── 01-linux-fundamentals.md
│   ├── 02-network-interfaces.md
│   ├── 03-routing-and-gateway.md
│   ├── 04-dns-investigation.md
│   ├── 05-network-connectivity.md
│   └── 06-security-analysis.md
├── findings/
└── screenshots/
```

## Future Improvements

- Practice Linux file-permission reviews.
- Inspect local listening services and ports.
- Investigate system logs and security events.
- Apply Linux networking concepts to a cloud environment.

## Author

Aspiring Cloud Security Engineer

This project represents my hands-on learning journey in Linux, networking, and cybersecurity.

