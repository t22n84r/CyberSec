# URL-based access control can be circumvented

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-02  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-284

## Objective and scope

Investigate url-based access control can be circumvented in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

A direct request for the admin route was blocked. Supplying the same route through X-Original-URL on an allowed path reached the admin interface and its delete operation.

## Root cause and impact

The front-end path check and back-end routing did not enforce the same authorization boundary.

## Recommended remediation

Strip untrusted routing override headers and authorize the resolved action in the application.

## Proposed retest

Test direct, overridden and normalized route variants with an unprivileged session.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `01-broken-access-control(3).md`. [Official lab](https://portswigger.net/web-security/access-control/lab-url-based-access-control-can-be-circumvented).
