DNS Reconnaissance

command used : nslookup vulnweb.com
This is the "Name Service Lookup." It is a basic tool used to find the IP address associated with a domain name or vice versa.
output : Server:  10.2.0.1
Address:  10.2.0.1#53

Non-authoritative answer:
Name:   vulnweb.com
Address: 44.228.249.3

Resolution Summary
Domain resolves to: 44.228.249.3
Response type: Non-authoritative (from DNS cache)
The domain correctly resolves to a public IP address hosted on cloud infrastructure.
Non-authoritative responses are normal and simply indicate the answer was retrieved from a cached DNS resolver.

command used : dig vulnweb.com ANY
dig (Domain Information Groper) is a more flexible and detailed tool than nslookup.
The ANY switch: This tells the DNS server to return all available resource records it has in its cache for that domain.
output : ; <<>> DiG 9.20.15-2-Debian <<>> vulnweb.com ANY
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: SERVFAIL, id: 53487
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;vulnweb.com.                   IN      ANY

;; Query time: 740 msec
;; SERVER: 10.2.0.1#53(10.2.0.1) (TCP)
;; WHEN: Thu Jan 01 23:38:25 EST 2026
;; MSG SIZE  rcvd: 40

ANY Query (dig)
DNS server returned SERVFAIL and did not provide records.
The DNS server likely blocks ANY queries intentionally to limit information disclosure.
This is considered a defensive configuration and does not represent a vulnerability.