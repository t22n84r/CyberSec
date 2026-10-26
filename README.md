# Cybersecurity & Infrastructure Security Portfolio

**Taanvir Nazmee** · Linux · Networking · Automation · Cloud infrastructure security

I work in AWS data center operations and build practical security skills through an independently operated homelab and authorized cybersecurity exercises. This portfolio connects vulnerability analysis with the controls needed to operate infrastructure: restricted access, reliable monitoring, protected secrets and recoverable changes.

## Start here

| Work | What it demonstrates | Evidence |
|---|---|---|
| [Web application security](labs/web-security/README.md) | Authorization testing, authentication logic, SQL injection and SSRF | 15 labs recorded completed; 2 unconfirmed investigations |
| [Secure file transfer analysis](labs/network-security/secure-file-transfer.md) | FTP/FTPS/SFTP comparison, packet analysis and TLS session-key handling | Assignment screenshots and Notion lab notes |
| [Service enumeration and exposed root shell](labs/network-security/metasploitable-enumeration.md) | Nmap discovery, targeted enumeration and privilege verification | Scan and shell screenshots |
| [Windows endpoint-security observations](labs/endpoint-security/windows-lab.md) | Detection evidence, execution evidence and careful interpretation | Defender alerts and a later shell-session screenshot |
| [Infrastructure security homelab](projects/infrastructure-security.md) | Access boundaries, automation identities, private HTTPS and network segmentation | Published implementation records; migration work remains active |
| [Local AI platform security](projects/local-ai-platform.md) | GPU platform operations, restricted backends, controlled maintenance and observability | Deployed platform and public technical write-up |
| [Monitoring and recovery](projects/monitoring-and-recovery.md) | Root-cause diagnosis and LXC-compatible service hardening | Documented service recovery and health validation |
| [Python traffic-inspection prototype](projects/python-proxy.md) | AI-assisted Python tooling and browser-proxy troubleshooting | Project narrative; original code not supplied |

## Featured engineering decisions

- Separate Terraform API identity, Ansible SSH identity and interactive administration.
- Enforce sensitive access at the hypervisor/network boundary and limit container port publication.
- Validate internal HTTPS using an internal CA, with private keys kept out of public documentation.
- Restore monitoring services while retaining the outer LXC/AppArmor boundary.
- Keep GPU-stack package rollback distinct from full off-host backup and disaster recovery.
- Record incomplete tests honestly: an absent callback or a successful shell does not prove every hypothesis in an attack chain.

## Skills demonstrated

| Area | Applied work |
|---|---|
| Application security | Burp Proxy/Repeater/Intruder, request comparison, access-control testing, authentication testing, SQLi and SSRF analysis |
| Network security | Nmap, Wireshark, FTP/FTPS/SFTP, firewall scoping and segmented labs |
| Linux and infrastructure | Proxmox, Linux VMs/LXC, Docker, SSH controls, service accounts and systemd troubleshooting |
| Automation and operations | Terraform, Ansible, Ansible Vault, validation checks, maintenance and recovery documentation |
| Observability | Prometheus, Grafana, Alertmanager, host/container/GPU exporters and alert delivery testing |

## How to read the evidence

[Evidence register](evidence/README.md) · [Publication and privacy policy](docs/publication-policy.md) · [Current scope and next steps](docs/status-and-next-steps.md)

The public examples use placeholders. Original screenshots, office files, captures and runtime secrets remain outside this repository. Transcriptions are labeled and are not fabricated command output. The work includes independent projects and training, not paid penetration-testing engagements or claims of complete production security.

## Related work

- [Homelab implementation documentation](https://github.com/t22n84r/homelab_docs)
- [LinkedIn](https://www.linkedin.com/in/taanvir-nazmee-5b13a7106/)

Reviewed for publication: October 26, 2026. Labs belong to their respective platforms; the case-study text describes my learning and recorded results.
