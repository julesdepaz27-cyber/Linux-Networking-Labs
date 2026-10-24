# Lab 03: Routing Table and Gateway Connectivity

## Objective

Examine the Linux routing table, identify the default gateway, and test connectivity to that gateway using ICMP ping requests.

## Environment

- Operating environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Network interface: `eth0`
- Commands used: `ip route`, `ping`

## Part 1: Routing Table Investigation

### Procedure

I ran the following command:

```bash
ip route
```

### Observed Results

```text
default via 172.21.144.1 dev eth0 proto kernel onlink
172.21.144.0/20 dev eth0 proto kernel scope link src 172.21.159.8
```

### Analysis

**Default route**

- Gateway: `172.21.144.1`
- Interface: `eth0`

The default route provides a path for traffic when no more specific routing entry matches the destination.

**Connected subnet**

- Subnet: `172.21.144.0/20`
- Interface: `eth0`
- Source address: `172.21.159.8`

The `/20` prefix corresponds to the subnet mask `255.255.240.0`. The interface address falls within this subnet.

## Part 2: Gateway Connectivity Test

### Procedure

I ran the following command:

```bash
ping -c 4 172.21.144.1
```

The `-c 4` option sends four ICMP echo requests before ending the test.

### Observed Results

- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%
- Minimum round-trip time: 0.287 ms
- Average round-trip time: 0.319 ms
- Maximum round-trip time: 0.381 ms

### Analysis

All four ICMP echo requests received replies from the configured gateway. This confirms that the gateway responded to the connectivity test from my WSL2 environment at the time of testing.

The low response times indicate a fast connection to this gateway during the test. However, this result does not independently confirm that external internet destinations are reachable.

## Security Considerations

1. **Routing visibility:** Reviewing routes helps administrators understand how network traffic is directed.
2. **Connectivity troubleshooting:** Ping can help determine whether a destination responds to ICMP requests.
3. **Limitations of ping:** A successful ping does not prove that every service or port is reachable or secure.
4. **Environment awareness:** WSL2 networking may behave differently from a standalone Linux server or cloud virtual machine.

These observations do not, by themselves, demonstrate a security vulnerability.

## Conclusion

I identified the default gateway and connected subnet in my Linux routing table. I then tested the gateway with four ICMP echo requests and observed a 0% packet-loss rate.

This lab strengthened my understanding of routing, gateways, and basic network troubleshooting in a virtualized Linux environment.

## Next Steps

- Investigate DNS resolution with `dig`.
- Compare successful and unsuccessful name lookups.
- Document how DNS supports network connectivity.
