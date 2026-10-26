# Bettercap MITM Attack & Analysis
A technical lab report documenting a controlled Man-in-the-Middle (MITM) attack using the Bettercap framework, performed entirely within an isolated VirtualBox host-only network.

**Author:** MUSABE Leon Armand

## Lab Environment

| Host Role | Operating System | IP Address | Interface |
|---|---|---|---|
| Attacker | Kali Linux | 192.168.56.101 | Host-only Adapter |
| Victim | Windows 10 Desktop | 192.168.56.102 | Host-only Adapter |
| Gateway (Host) | VirtualBox Host-Only | 192.168.56.1 | vboxnet0 |

## What's Covered

- **Network Reconnaissance** — host discovery using Bettercap's `net.probe` module
- **ARP Cache Poisoning** — dual-duplex ARP spoofing with IPv4 forwarding enabled
- **Packet Sniffing** — traffic capture to `.pcap` with Wireshark inspection and tcpdump fallback
- **DNS Spoofing** — redirecting domain resolution to a local Python HTTP server
- **HTTP Proxy & JavaScript Injection** — real-time HTML modification via a custom `inject.js` script
- **Automation** — full attack sequence consolidated into a reusable Bettercap caplet (`.cap`)

## Security Analysis

The report also breaks down the root causes behind each attack vector and maps them to defensive controls:

| Vulnerability | Countermeasure |
|---|---|
| Unauthenticated ARP resolution | Dynamic ARP Inspection (DAI) |
| Plaintext HTTP traffic | HTTP Strict Transport Security (HSTS) |
| Unsecured local DNS resolution | DNSSEC |

## Scope

This exercise was conducted entirely within an isolated VirtualBox host-only subnet (192.168.56.0/24), for educational purposes only.

## Report

The full report is available in [`Armand.pdf`](./Armand.pdf).
