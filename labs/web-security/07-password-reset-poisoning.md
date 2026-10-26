# Password reset poisoning via middleware

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-07  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-640

## Objective and scope

Investigate password reset poisoning via middleware in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

An X-Forwarded-Host value changed the reset-link destination. The lab exploit-server log exposed a reset token, which was used on the legitimate lab host to reset the target account and log in.

## Root cause and impact

Reset URLs trusted request-derived host metadata.

## Recommended remediation

Generate reset URLs from a trusted configured origin; validate proxy headers and make reset tokens short-lived and single-use.

## Proposed retest

Poison host-related headers and verify that reset links always use the configured origin; verify token expiry and reuse rejection.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `02-authentication-session(4).md`. [Official lab](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-poisoning-via-middleware).
