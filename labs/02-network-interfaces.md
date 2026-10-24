# Lab 02: Network Interface Investigation

## Objective

Inspect the network interfaces configured in my Ubuntu environment and identify their IP addresses, states, and basic networking properties.

## Environment

- Environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Command used: `ip addr`

## Procedure

I ran the following command:

```bash
ip addr
```

This command displays network interfaces and their assigned addresses.

## Findings

### 1. Loopback interface (`lo`)

- IPv4 address: `127.0.0.1/8`
- Interface flags: `LOOPBACK,UP,LOWER_UP`
- Additional IPv4 address observed: `10.255.255.254/32`
- IPv6 loopback address: `::1/128`

**Interpretation:** The loopback interface supports communication within the local system. The additional IPv4 address appears in this WSL2 environment and is part of its networking configuration.

### 2. Network interface (`eth0`)

- IPv4 address: `172.21.159.8/20`
- Broadcast address: `172.21.159.255`
- MTU: `1500`
- Interface state: `UP`
- Link state flag: `LOWER_UP`
- IPv6 link-local address: Present

**Interpretation:** The `eth0` interface is enabled and its link is up according to the displayed flags. Its IPv4 address belongs to private address space. These observations alone do not confirm internet connectivity.

The `/20` prefix corresponds to the subnet mask `255.255.240.0`.

## Security Considerations

1. **Private addressing:** Private IPv4 addresses are commonly used in local networks and virtualized environments.
2. **Interface visibility:** Inspecting network interfaces helps administrators understand the system's network configuration.
3. **Information exposure:** Network details can reveal information about an environment. Review raw output and screenshots before publishing them publicly.

These findings do not, by themselves, demonstrate a security vulnerability.

## Conclusion

This investigation identified the loopback interface and the `eth0` network interface in my WSL2 environment. I recorded their addresses, interface states, and selected networking properties.

This exercise improved my understanding of Linux networking and prepared me to investigate how traffic is routed.

## Next Step

Inspect the routing table to understand how the system determines where network traffic should go.
