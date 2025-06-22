# TLS Traffic Analysis with Wireshark

This lab demonstrates how to capture and decrypt HTTPS (TLS) traffic using Wireshark, inspect DNS queries to reveal domains, and verify IP ownership using WHOIS. All traffic is captured ethically on the analyst's own machine.

## Skills Demonstrated
- Capturing and decrypting TLSv1.2 traffic using Wireshark
- Using SSL pre-master secrets to reveal HTTPS content
- Tracking DNS lookups to identify target domains
- Using `whois` to confirm IP address ownership

## Tools Used
- Wireshark
- Firefox
- Linux Terminal (Kali)
- DNS and WHOIS

## Screenshots
See the `images/` folder for walkthrough screenshots:
- `wireshark_capture.png` – TLS capture from YouTube
- `decrypted_http.png` – Viewing decrypted HTTP from `httpbin.org`
- `dns_query.png` – DNS query revealing `play.google.com`
- `whois_google_ip.png` – WHOIS confirmation of Google-owned IP

## Decryption Setup
1. Set the environment variable:
   ```bash
   export SSLKEYLOGFILE=~/sslkeys.log
   firefox &
