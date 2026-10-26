# Evidence register

[Back to portfolio](../README.md)

Original artifacts were reviewed privately. Public entries link to the resulting case studies and identify the limits of the evidence. This register accounts for all 22 uploaded files plus the named Notion section.

| Source set | Count | Public use | Important limit |
|---|---:|---|---|
| Broken-access-control Markdown | 1 | Five access-control case studies | Completion based on notes |
| Authentication/session Markdown | 1 | Four authentication case studies | Requests may be representative rather than raw captures |
| SQL-injection Markdown | 1 | Four SQLi case studies | Scripts/raw final responses not supplied; DBMS certainty narrowed |
| SSRF Markdown | 1 | Two completed and two unconfirmed case studies | No invented callback or RCE result |
| Assignment 1 Word document, including 14 embedded images | 1 | FTP/FTPS/SFTP and TLS-decryption analysis | Contains visible secrets; original excluded |
| Assignment 2 Word document, including three embedded images | 1 | Enumeration and exposed-shell case study | Duplicate embedded/standalone images are one evidence set |
| nc_access.png; nmap_ports_scan_details.png; nmap_all_ports_scan.png | 3 | Scan-to-shell result and sanitized identity output | No claims that every service was exploited |
| step_1, step_2, step_2.1, step_3 | 4 | Endpoint lab configuration and troubleshooting | Setup is not proof of target execution |
| step_4-1, step_4-2 | 2 | Defender detection and quarantine-status interpretation | Failed quarantine is not successful remediation |
| step_5 through step_9 | 5 | Packaging/tooling context | No proof of evasion or delivery success |
| step_10 | 1 | Later PowerShell shell-session observation | Exact originating artifact and protection state unconfirmed |
| step_11 | 1 | Additional packaging context | Not independent proof of compromise |
| Notion: Secure File Transfer Lab Notes | — | Transfer workflow and control-channel decryption | Data-channel decryption not established |
| Notion: Tooling | — | Python proxy project narrative | Repeated text deduplicated; code not supplied |
| Existing public homelab implementation records | — | Infrastructure, AI and monitoring case studies | Milestones distinguished from current open work |

Uploaded filenames include duplicate-download suffixes such as `(1)`. Those suffixes do not denote distinct experiments. Dates embedded in screenshots take precedence over assumptions from assignment filenames; exact dates are omitted where the material does not establish them.

Private Notion page identifiers and download URLs are not published. The root README and project pages link only the existing public homelab records and official training references.
