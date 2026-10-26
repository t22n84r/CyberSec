# Referer-based access control

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-03  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-284

## Objective and scope

Investigate referer-based access control in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

An ordinary user’s role-change request failed without the expected Referer but succeeded with a forged admin-page Referer.

## Root cause and impact

Client-supplied navigation metadata was treated as proof of authorization.

## Recommended remediation

Use server-side role checks. Treat Referer checks only as supplementary context.

## Proposed retest

Vary, omit and forge Referer while verifying that permissions remain tied to identity.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `01-broken-access-control(3).md`. [Official lab](https://portswigger.net/web-security/access-control/lab-referer-based-access-control).
