# Lab 05: Network Connectivity Testing

## Objective

Test connectivity to `example.com` using HTTPS and ICMP ping, then compare the results to understand what each test verifies.

## Environment

- Operating environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Target domain: `example.com`
- Tools: `curl`, `ping`
- HTTPS port: TCP 443

## Test 1: HTTPS Connectivity

### Command

```bash
curl -I --max-time 10 https://example.com
```

### Observed Results

- HTTP response: `HTTP/2 200`
- Content type: `text/html; charset=utf-8`
- Server header: `cloudflare`
- Cache status header: `HIT`

### Analysis

The server returned an HTTP success status in response to the HTTPS request. This confirms that the request reached an HTTPS endpoint and received a response at the time of testing.

The response headers also indicated that Cloudflare handled the response and reported a cache hit.

## Test 2: ICMP Connectivity

### Command

```bash
ping -c 4 example.com
```

### Observed Results

- Resolved IPv4 address: `172.66.147.243`
- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%
- Minimum round-trip time: 15.434 ms
- Average round-trip time: 17.851 ms
- Maximum round-trip time: 21.206 ms

### Analysis

All four ICMP echo requests received replies from the resolved address. This confirms that the destination responded to ping during the test.

The average round-trip time was approximately 17.9 ms. Network latency can vary due to routing, congestion, and other conditions.

## Comparison

| Check | Result | What it demonstrates |
|---|---|---|
| HTTPS request | HTTP/2 200 | A successful web response |
| ICMP ping | 4/4 replies | The destination responded to echo requests |
| DNS resolution | Address returned | The domain resolved to an IPv4 address |

These checks measure different aspects of connectivity. A successful result from one does not guarantee that every other network service is available.

## Security Considerations

1. **Layered troubleshooting:** Use DNS, ICMP, and application-level checks to investigate different types of connectivity issues.
2. **Response headers:** HTTP headers can reveal information about the technologies handling a response.
3. **Limitations:** Successful connectivity tests do not prove that a host or service is free of vulnerabilities.
4. **Repeatability:** Record the command, results, and test conditions so future tests can be compared.

No security vulnerability was identified by these connectivity tests alone.

## Conclusion

I tested `example.com` using an HTTPS HEAD request and ICMP ping. The HTTPS request returned `HTTP/2 200`, and all four ping requests received replies with no packet loss.

This lab strengthened my understanding of DNS resolution, ICMP, HTTPS, and layered network troubleshooting.

## Next Steps

Review the results from all five labs, identify their security lessons and limitations, and prepare a final project summary.

