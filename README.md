# TLS Traffic Analysis with Wireshark

This lab demonstrates how to capture and decrypt HTTPS (TLS) traffic using Wireshark, inspect DNS queries to reveal domains, and verify IP ownership using WHOIS. All traffic is captured ethically on the analyst's own machine.

## Skills Demonstrated

* Capturing and decrypting TLSv1.2 traffic using Wireshark
* Using SSL pre-master secrets to reveal HTTPS content
* Tracking DNS lookups to identify target domains
* Using `whois` to confirm IP address ownership

## Tools Used

* Wireshark
* Firefox
* Linux Terminal (Kali)
* DNS and WHOIS

## Table of Contents

* [Overview](#-tls-traffic-analysis-with-wireshark)
* [Skills Demonstrated](#-skills-demonstrated)
* [Tools Used](#-tools-used)
* [TLS Decryption Setup](#-tls-decryption-setup)
* [DNS + WHOIS Analysis](#-dns-analysis)
* [Traffic Analysis Summary](#-traffic-analysis-summary)
* [License](#-license)

## Decryption Setup

1. Set the environment variable:

   ```bash
   export SSLKEYLOGFILE=~/sslkeys.log
   firefox &
   ```

2. Set the key log file in Wireshark:

   * Edit → Preferences → Protocols → TLS → (Pre)-Master-Secret log filename → `~/sslkeys.log`

3. Visit HTTPS sites (e.g., `https://httpbin.org/get`) and apply the `http` filter in Wireshark to view decrypted traffic.

---

### DNS Analysis

Filter:

```
dns && frame contains "google"
```

Reveals domains like `play.google.com`, with resolved IPs (e.g., `192.178.50.46`).

---

### WHOIS Lookup

Run:

```bash
whois 192.178.50.46
```

Result: IP is owned by Google LLC.

---

## Traffic Analysis Summary

The analysis included:

* Capturing live TLSv1.2 traffic over port 443
* Decrypting HTTPS using SSL key log methods
* Observing DNS queries to reveal domain-to-IP resolution
* Confirming IP ownership with WHOIS to validate service providers

This demonstrates the ability to capture, decrypt, and investigate encrypted traffic using metadata and TLS session key logging.

---

## License

MIT
