# 2FA bypass using a brute-force attack

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-10  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-307

## Objective and scope

Investigate 2fa bypass using a brute-force attack in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

The notes record a completed MFA brute-force exercise. A Burp macro restored login state before each verification attempt, allowing attempts to continue across the application’s logout behavior.

## Root cause and impact

Ending a session did not enforce a cumulative verification-attempt limit on the account.

## Representative request pattern

This excerpt is a sanitized reconstruction from the notes, not a retained raw HTTP capture.

```http
POST /login2 HTTP/2
Host: <lab-instance>
Cookie: session=<redacted>
Content-Type: application/x-www-form-urlencoded

csrf=<redacted>&mfa-code=<candidate-code>
```

## Recommended remediation

Bind MFA challenges to an account and login transaction; enforce account-level attempt limits and expiry.

## Proposed retest

Repeat failures across fresh sessions and confirm that cumulative limits persist and protected pages remain inaccessible.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `02-authentication-session(4).md`. [Official lab](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-bypass-using-a-brute-force-attack).
