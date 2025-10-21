# Learning DNS: From Local Client to Public Servers


![DNS resolution diagram: from local client through local DNS to root, TLD, and authoritative server](./dns-diagram.png)

__*All IP addresses and DNS servers shown are fictive; this is for educational purposes only!*__

This diagram shows the DNS resolution process, starting from a local client querying a local DNS server, and following the chain through root servers, top level domain (.) servers, and authoritative servers until the A record for `www.dn.se` is returned.

1. <span style="color:skyblue">User (local)</span> queries the local DNS server (`lo.se.dns`).
2. <span style="color:skyblue">Local DNS server</span> (`lo.se.dns`) checks its cache, local zones, and conditional forwarders.
3. If not found, the local server queries the <span style="color:lime">root server (.)</span>.
4. <span style="color:lime">Root server (one of 13 globally)</span> refers the query to the <span style="color:yellow">Top level domain server for .SE<span>.
5. <span style="color:lime">Top level domain server</span> refers the query to the <span style="color:orange">authoritative server for dn.se.</span>
6. <span style="color:orange">Authoritative server for dn.se</span> returns the A record for `www.dn.se`.
7. <span style="color:skyblue">Local DNS server</span> caches the result and returns it to the <span style="color:skyblue">local user.</span>
