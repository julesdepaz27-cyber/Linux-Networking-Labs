# Lab 06: Security Analysis and Final Findings

## Objective

Review the findings from five Linux and networking investigations, identify their security relevance, and document the limitations of the tests performed.

## Environment

- Operating environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Platform: Windows 11 with Ubuntu running through WSL2
- Topics investigated: Linux fundamentals, network interfaces, routing, DNS, and connectivity

## Summary of Findings

### 1. Linux Fundamentals

**Evidence:** Used `pwd`, `ls -la`, `whoami`, and `uname -a`.

**Finding:** Identified the working directory, current user, project directories, and Linux kernel environment.

**Security relevance:** User identity, file permissions, and system identification are useful starting points for understanding a system's security context.

### 2. Network Interfaces

**Evidence:** Ran `ip addr`.

**Finding:** Identified the loopback interface and `eth0`, including their configured IP addresses and interface flags.

**Security relevance:** Understanding network interfaces helps with troubleshooting and reviewing which network connections a system uses.

### 3. Routing and Gateway Connectivity

**Evidence:** Ran `ip route` and `ping -c 4 172.21.144.1`.

**Finding:** Identified the default gateway and connected subnet. All four gateway ping requests received replies, with 0% packet loss.

**Security relevance:** Routing information helps administrators understand traffic paths and investigate network connectivity.

### 4. DNS Investigation

**Evidence:** Ran `dig example.com` and `dig google.com`.

**Finding:** Both queries returned `NOERROR` and IPv4 address records through the same observed DNS server.

**Security relevance:** DNS testing helps troubleshoot name resolution and understand how domain names map to network addresses.

### 5. Network Connectivity

**Evidence:** Ran `curl -I --max-time 10 https://example.com` and `ping -c 4 example.com`.

**Finding:** The HTTPS request returned `HTTP/2 200`. All four ICMP ping requests received replies with 0% packet loss.

**Security relevance:** Different connectivity tests help determine whether a problem involves name resolution, network reachability, or an application-level response.

## Overall Security Assessment

The tests completed in this project demonstrated basic Linux administration and network troubleshooting skills in a WSL2 environment.

The observed results showed that:

- The Linux environment had configured network interfaces.
- A default route and gateway were present.
- DNS queries returned address records.
- The gateway responded to ICMP requests.
- An HTTPS request and ICMP tests to a public domain succeeded.

**Assessment limitation:** These tests did not constitute a full security audit. They did not establish whether the system was vulnerable, whether all services were securely configured, or whether unauthorized access was possible.

## Skills Practiced

- Linux command-line navigation and system identification
- Reading network interface configuration
- Interpreting routing tables
- Testing gateway connectivity
- Performing DNS lookups
- Testing HTTPS responses and ICMP connectivity
- Recording technical evidence in Markdown
- Writing security observations without overstating conclusions

## Conclusion

This project provided hands-on practice with Linux and networking fundamentals in an Ubuntu WSL2 environment. I documented five investigations, recorded observed results, and connected each exercise to practical security concepts.

The project established a foundation for future work involving Linux hardening, cloud networking, access controls, and cloud security monitoring.

## Future Improvements

- Investigate file permissions and identify overly permissive files in a controlled environment.
- Learn to inspect listening services and open ports on the local system.
- Practice reviewing security logs.
- Apply networking concepts to a cloud lab environment.

