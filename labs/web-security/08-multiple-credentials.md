# Broken brute-force protection, multiple credentials per request

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-07  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-307; CWE-20

## Objective and scope

Investigate broken brute-force protection, multiple credentials per request in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

The JSON password field accepted an array of guesses. The request returned a redirect and authenticated access was loaded in the browser, completing the lab.

## Root cause and impact

Input typing and attempt accounting allowed multiple credential checks within one request.

## Representative request pattern

This excerpt is a sanitized reconstruction from the notes, not a retained raw HTTP capture.

```http
POST /login HTTP/2
Host: <lab-instance>
Cookie: session=<redacted>
Content-Type: application/json

{
  "username": "carlos",
  "password": "<candidate-password>"
}
```

## Recommended remediation

Require a scalar password value and rate-limit authentication attempts per account.

## Proposed retest

Reject arrays and nested input, and verify that bundled requests cannot evade the attempt budget.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `02-authentication-session(4).md`. [Official lab](https://portswigger.net/web-security/authentication/password-based/lab-broken-brute-force-protection-multiple-credentials-per-request).
