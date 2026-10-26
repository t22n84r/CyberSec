# Cybersecurity Lab Portfolio

**Taanvir Nazmee** · Web application security · Network analysis · Endpoint-security exercises

This repository presents my authorized cybersecurity training, practical lab exercises and security-tooling project notes. Each case study explains the test, the observed result, its security implications and the limits of the available evidence.

## Explore the work

| Work | What it demonstrates | Evidence |
|---|---|---|
| [Web application security](labs/web-security/README.md) | Authorization testing, authentication logic, SQL injection and SSRF | 15 labs recorded completed; 2 unconfirmed investigations |
| [Secure file transfer analysis](labs/network-security/secure-file-transfer.md) | FTP/FTPS/SFTP comparison, packet analysis and TLS session-key handling | Assignment screenshots and Notion lab notes |
| [Service enumeration and exposed root shell](labs/network-security/metasploitable-enumeration.md) | Nmap discovery, targeted enumeration and privilege verification | Scan and shell screenshots |
| [Windows endpoint-security observations](labs/endpoint-security/windows-lab.md) | Detection evidence, execution evidence and careful interpretation | Defender alerts and a later shell-session screenshot |
| [Python traffic-inspection prototype](projects/python-proxy.md) | AI-assisted Python tooling and browser-proxy troubleshooting | Project narrative; original code not supplied |

## Skills demonstrated

| Area | Applied work |
|---|---|
| Application security | Burp Proxy/Repeater/Intruder, request comparison, access-control testing, authentication testing, SQLi and SSRF analysis |
| Network analysis | Nmap, Wireshark, FTP/FTPS/SFTP and service enumeration in an isolated lab |
| Endpoint investigation | Interpreting Windows Defender alerts, remediation status and shell-session evidence |
| Security tooling | Python proxy design, socket/threading/tkinter concepts and browser-proxy troubleshooting |
| Reporting | Methodology, evidence limits, root causes, remediation and proposed retest criteria |

## How to read the evidence

[Evidence register](evidence/README.md) · [Publication and privacy policy](docs/publication-policy.md) · [Lab status and next steps](docs/status-and-next-steps.md)

Public examples use placeholders. Original screenshots, office files, captures and runtime secrets remain outside this repository. Transcriptions are labeled and are not fabricated command output. These are training exercises and independent security-tooling work, not paid penetration-testing engagements.

Two blind-SSRF exercises remain explicitly unconfirmed. The endpoint report distinguishes detection, remediation failure and a later shell session without claiming that every step in the attack chain was proven.

[LinkedIn](https://www.linkedin.com/in/taanvir-nazmee-5b13a7106/)

Reviewed for publication: October 26, 2026. Labs belong to their respective platforms; the case-study text describes my learning and recorded results.
