Sub-Domains Reconnaissance

Subdomain Enumeration, a critical step in the reconnaissance (information gathering) phase of a security audit or penetration test.

command used : sublist3r -d vulnweb.com
sublist3r: Invokes the Sublist3r tool, a Python-based script popular among ethical hackers.
-d: Stands for Domain. It tells the tool which target domain you want to investigate.
vulnweb.com: The target domain. In this case, it’s a site designed for legal security testing.
output : 
www.vulnweb.com
test.php.vulnweb.com
rest.vulnweb.com
test.vulnweb.com
testasp.vulnweb.com
testaspnet.vulnweb.com
testhtml5.vulnweb.com
testphp.vulnweb.com

detailed output :     
[-] Enumerating subdomains now for vulnweb.com
[-] Searching now in Baidu..
[-] Searching now in Yahoo..
[-] Searching now in Google..
[-] Searching now in Bing..
[-] Searching now in Ask..
[-] Searching now in Netcraft..
[-] Searching now in DNSdumpster..
[-] Searching now in Virustotal..
[-] Searching now in ThreatCrowd..
[-] Searching now in SSL Certificates..
[-] Searching now in PassiveDNS..
[!] Error: Google probably now is blocking our requests
[~] Finished now the Google Enumeration ...
Process DNSdumpster-8:
Traceback (most recent call last):
  File "/usr/lib/python3.13/multiprocessing/process.py", line 313, in _bootstrap
    self.run()
    ~~~~~~~~^^
  File "/usr/lib/python3/dist-packages/sublist3r.py", line 269, in run
    domain_list = self.enumerate()
  File "/usr/lib/python3/dist-packages/sublist3r.py", line 649, in enumerate
    token = self.get_csrftoken(resp)
  File "/usr/lib/python3/dist-packages/sublist3r.py", line 644, in get_csrftoken
    token = csrf_regex.findall(resp)[0]
            ~~~~~~~~~~~~~~~~~~~~~~~~^^^
IndexError: list index out of range
[!] Error: Virustotal probably now is blocking our requests
[-] Total Unique Subdomains Found: 8
www.vulnweb.com
test.php.vulnweb.com
rest.vulnweb.com
test.vulnweb.com
testasp.vulnweb.com
testaspnet.vulnweb.com
testhtml5.vulnweb.com
testphp.vulnweb.com


| Subdomain                                 | Likely Purpose                   | Attack Relevance                    |
| ----------------------------------------- | -------------------------------- | ----------------------------------- |
| [www.vulnweb.com](http://www.vulnweb.com) | Main site                        | Baseline                            |
| test.vulnweb.com                          | Generic test site                | Possible older features             |
| testphp.vulnweb.com                       | PHP app (your internship target) | High priority                       |
| testasp.vulnweb.com                       | Classic ASP app                  | Legacy tech → often vulnerable      |
| testaspnet.vulnweb.com                    | ASP.NET test                     | Authentication/logic flaws common   |
| testhtml5.vulnweb.com                     | HTML5 demo app                   | Likely XSS test bed                 |
| rest.vulnweb.com                          | API endpoint                     | IDOR, auth bypass, API exploitation |
| test.php.vulnweb.com                      | Typo / alternate routing         | Confirms internal experiments       |


The domain hosts multiple test environments, each exposing different technologies (PHP, ASP, .NET, REST APIs, etc.). This increases the potential attack surface because development and demo systems often lack hardened security controls.

However, the internship scope is restricted to testphp.vulnweb.com, so the other subdomains were only documented and not targeted for active testing.

Issues Noted During Enumeration : 
Google, VirusTotal, and DNSdumpster blocked automated requests.
This is expected behavior and does not indicate problems with the target.