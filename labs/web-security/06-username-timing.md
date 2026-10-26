# Username enumeration via response timing

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-07  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-208; CWE-307

## Objective and scope

Investigate username enumeration via response timing in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Long incorrect passwords amplified response-time differences between candidate usernames. The notes record a slower valid-account candidate, subsequent password testing and successful login. Client-controlled X-Forwarded-For values also bypassed the lab’s IP-based restriction.

## Root cause and impact

Account validity leaked through timing, and the application trusted an unverified proxy header. Exact server-side implementation was not inspected.

## Representative request pattern

This excerpt is a sanitized reconstruction from the notes, not a retained raw HTTP capture.

```http
POST /login HTTP/2
Host: <lab-instance>
Cookie: session=<redacted>
Content-Type: application/x-www-form-urlencoded
X-Forwarded-For: <unique-value>

csrf=<redacted>&username=<candidate-username>&password=AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
```

## Recommended remediation

Use consistent authentication work, trusted-proxy handling and account-aware throttling.

## Proposed retest

Compare repeated timing distributions and verify that changing forwarding headers cannot reset attempt limits.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `02-authentication-session(4).md`. [Official lab](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-response-timing).
