# User ID controlled by request parameter

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-08-02  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-639

## Objective and scope

Investigate user id controlled by request parameter in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Changing the account identifier returned another lab user’s account data and API key. The session remained that of the original, lower-privileged user.

## Root cause and impact

Authorization must bind each requested object to the authenticated identity.

## Recommended remediation

Enforce object-level authorization on every account lookup.

## Proposed retest

Repeat the original and modified identifier requests with two users; cross-user access must fail while each user retains access to their own account.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `01-broken-access-control(3).md`. [Official lab](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter).
