# Method-based access control can be circumvented

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-01  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-284

## Objective and scope

Investigate method-based access control can be circumvented in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

A protected role-change POST was rejected for the ordinary user. Converting it to GET with query parameters allowed that user’s role upgrade.

## Root cause and impact

Authorization differed between methods accepted by the same endpoint.

## Recommended remediation

Authorize every handler and reject unsupported methods; use appropriate CSRF protection for state changes.

## Proposed retest

Exercise each supported method and verify that no unprivileged request changes roles.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `01-broken-access-control(3).md`. [Official lab](https://portswigger.net/web-security/access-control/lab-method-based-access-control-can-be-circumvented).
