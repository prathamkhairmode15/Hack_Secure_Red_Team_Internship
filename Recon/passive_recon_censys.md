Passive Recon-Censys Analysis (44.228.249.3)

Host & DNS Mapping
Reverse DNS: ec2-44-228-249-3.us-west-2.compute.amazonaws.com
Forward DNS: testphp.vulnweb.com
Reverse lookup shows it is an AWS EC2 cloud machine
Forward lookup ties the IP directly to testphp.vulnweb.com

Cloud & Routing Details
Routing: via AMAZON-02, US (AS16509)
Traffic is routed via Amazon internal backbone.
This confirms cloud-shared infrastructure — not a corporate datacenter.

Services Exposed
Services: 80/HTTP

Web Server Software Identified
Software: nginx 1.19.0
The web server is nginx
Version 1.19.0 (not latest)
Older versions may have:
misconfiguration weaknesses
HTTP parsing quirks
reverse-proxy issues

Findings:
Reverse DNS points to AWS EC2 infrastructure
Forward DNS maps to testphp.vulnweb.com
Routing through Amazon backbone (AS16509)
Only HTTP (port 80) exposed
Web server identified as nginx 1.19.0
Server returns 400 Bad Request to malformed probes
Hosted physically in Oregon, USA

The application is hosted on an AWS EC2 instance with a minimal public attack surface.
Only HTTP is exposed, and no encryption is enabled, which indicates possible risks related to plaintext credential transmission.

The presence of nginx 1.19.0 suggests potential configuration-based vulnerabilities, though exploitation requires further testing.

Censys confirms earlier Shodan intelligence without requiring any interaction from our side, maintaining purely passive reconnaissance.

Censys validates that the target is a deliberately exposed web service hosted on AWS, running nginx over HTTP. This intelligence directly informs our active recon strategy in the next phase.