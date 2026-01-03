Passive Recon-Shodan Analysis (44.228.249.3)

Findings :

The server is hosted on Amazon EC2 (us-west-2).
The IP belongs to Amazon (shared cloud infrastructure).
Only HTTP (port 80) is visible from Shodan’s historical scan.
No HTTPS service detected.
Hosting environment is cloud-managed (not on-premise).

The application runs on a public cloud VM. Cloud-hosted environments often reuse IPs and may host multiple demo systems, so attacks must remain strictly in-scope.

The absence of HTTPS suggests insecure transmission of sensitive data, which supports later testing tasks (Wireshark credential capture and session analysis).

Shodan results were obtained without interacting with the target, meaning this intelligence was collected safely and ethically.

Shodan confirms a cloud-hosted web application running on port 80 only, with no encryption detected. This information helps narrow our Nmap scanning strategy and guides later exploitation planning.