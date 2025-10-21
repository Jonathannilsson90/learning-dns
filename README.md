# Learning DNS: From Local Client to Public Servers


![DNS resolution diagram: from local client through local DNS to root, TLD, and authoritative server](./dns-diagram.png)

__*All IP addresses and DNS servers shown are fictive; this is for educational purposes only!*__

This diagram shows the DNS resolution process, starting from a local client querying a local DNS server, and following the chain through root servers, top level domain (.) servers, and authoritative servers until the A record for `www.dn.se` is returned.


1. ![User](https://img.shields.io/badge/User-skyblue) queries the local DNS server (`lo.se.dns`).
2. ![Local DNS](https://img.shields.io/badge/Local_DNS-skyblue) (`lo.se.dns`) checks its cache, local zones, and conditional forwarders.
3. If not found, the local server queries the ![Root](https://img.shields.io/badge/Root-lime) server (.).
4. ![Root](https://img.shields.io/badge/Root-lime) server (one of 13 globally) refers the query to the ![TLD](https://img.shields.io/badge/.SE-yellow) Top level domain server for .SE.
5. ![TLD](https://img.shields.io/badge/.SE-yellow) Top level domain server refers the query to the ![Authoritative](https://img.shields.io/badge/dn.se-orange) authoritative server for dn.se.
6. ![Authoritative](https://img.shields.io/badge/dn.se-orange) authoritative server returns the A record for `www.dn.se`.
7. ![Local DNS](https://img.shields.io/badge/Local_DNS-skyblue) caches the result and returns it to the ![User](https://img.shields.io/badge/User-skyblue) local user.
