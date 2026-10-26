# Web security lab index

[Back to portfolio](../../README.md)

17 documented exercises: **15 completed according to the lab records; 2 unconfirmed**. They cover five access-control labs, four authentication labs, four SQL-injection labs and four SSRF labs. These are authorized training exercises, not client assessments.

| # | Exercise | Date recorded | Outcome |
|---|---|---|---|
| 01 | [User ID controlled by request parameter](01-idor.md) | 2026-08-02 | Completed (notes) |
| 02 | [URL-based access control can be circumvented](02-url-override.md) | 2026-09-02 | Completed (notes) |
| 03 | [Method-based access control can be circumvented](03-http-method.md) | 2026-09-01 | Completed (notes) |
| 04 | [Multi-step process with no access control on one step](04-workflow-step.md) | 2026-09-02 | Completed (notes) |
| 05 | [Referer-based access control](05-referer-authorization.md) | 2026-09-03 | Completed (notes) |
| 06 | [Username enumeration via response timing](06-username-timing.md) | 2026-09-07 | Completed (notes) |
| 07 | [Password reset poisoning via middleware](07-password-reset-poisoning.md) | 2026-09-07 | Completed (notes) |
| 08 | [Broken brute-force protection, multiple credentials per request](08-multiple-credentials.md) | 2026-09-07 | Completed (notes) |
| 09 | [2FA bypass using a brute-force attack](09-mfa-attempt-limits.md) | 2026-09-10 | Completed (notes) |
| 10 | [SQL injection UNION attack, retrieving data from other tables](10-union-data-retrieval.md) | 2026-09-21 | Completed (notes) |
| 11 | [Blind SQL injection with conditional responses](11-boolean-blind.md) | 2026-09-23 | Completed (notes) |
| 12 | [Blind SQL injection with time delays and information retrieval](12-time-based-blind.md) | 2026-09-26 | Completed (notes) |
| 13 | [SQL injection with filter bypass via XML encoding](13-xml-filter-bypass.md) | 2026-09-26 | Completed (notes) |
| 14 | [SSRF with filter bypass via open redirection vulnerability](14-redirect-ssrf.md) | 2026-09-27 | Completed (notes) |
| 15 | [SSRF with whitelist-based input filter](15-allowlist-ssrf.md) | 2026-09-28 | Completed (notes) |
| 16 | [Blind SSRF with out-of-band detection](16-blind-oast.md) | 2026-09-30 | Unconfirmed |
| 17 | [Blind SSRF with Shellshock exploitation](17-blind-shellshock.md) | 2026-09-30 | Unconfirmed |

Each write-up separates the observed result, interpretation, recommended remediation and proposed retest. Requests are representative and sanitized. No new network tests were performed for this publication.
