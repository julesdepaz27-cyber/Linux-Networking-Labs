# Lab 04: DNS Investigation

## Objective

Use the `dig` command to investigate DNS resolution for two domain names, compare their IPv4 address records, and document the results.

## Environment

- Operating environment: Ubuntu on Windows Subsystem for Linux 2 (WSL2)
- Tool: `dig`
- DNS server observed: `10.255.255.254`
- Protocol: UDP
- DNS port: 53
- Record type queried: A (IPv4 address)

## Test 1: Resolve example.com

### Command

```bash
dig example.com
```

### Observed Results

- DNS status: `NOERROR`
- Answer records: 2
- IPv4 address 1: `104.20.23.154`
- IPv4 address 2: `172.66.147.243`
- Query time: 16 ms
- DNS server: `10.255.255.254`

### Interpretation

The DNS server returned two IPv4 address records for `example.com`. The `NOERROR` status indicates that the query completed without a DNS error.

## Test 2: Resolve google.com

### Command

```bash
dig google.com
```

### Observed Results

- DNS status: `NOERROR`
- Answer records: 1
- IPv4 address: `142.251.40.110`
- Query time: 20 ms
- DNS server: `10.255.255.254`

### Interpretation

The DNS server returned one IPv4 address record for `google.com`. The query also completed without a DNS error.

## Comparison

| Observation | example.com | google.com |
|---|---|---|
| DNS status | NOERROR | NOERROR |
| IPv4 records returned | 2 | 1 |
| Query time | 16 ms | 20 ms |
| DNS server | 10.255.255.254 | 10.255.255.254 |

The two queries returned different numbers of address records and different response times. These measurements represent individual queries and do not establish typical performance.

## Security Considerations

1. **DNS troubleshooting:** DNS lookups help identify whether a domain resolves to address records.
2. **Infrastructure awareness:** DNS responses can reveal information about how a service's network endpoints are configured.
3. **Response limitations:** Successful DNS resolution does not prove that a web server is reachable or that its services are secure.
4. **Privacy:** DNS queries can reveal which domain names a system looks up. DNS privacy depends on the resolver and network configuration.

These observations do not, by themselves, demonstrate a security vulnerability.

## Conclusion

I used `dig` to investigate DNS resolution for two domains. Both queries returned `NOERROR` through the same observed DNS server, but the number of IPv4 records and query times differed.

This lab improved my understanding of DNS records, resolvers, and basic network troubleshooting.

## Next Steps

Test network connectivity to a public destination and compare the results of ICMP and HTTPS checks.

