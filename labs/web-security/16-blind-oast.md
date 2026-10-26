# Blind SSRF with out-of-band detection

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-30  
**Status:** Unconfirmed — not solved  
**Mapping:** CWE-918

## Objective and scope

Investigate blind ssrf with out-of-band detection in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Referer-based out-of-band tests using substitute HTTP and DNS callback services produced no observed interaction. The required Collaborator workflow was unavailable in the tooling used. The lab was not solved.

## Root cause and impact

The lab describes blind SSRF, but a normal application response does not prove a server-side callback. The exact reason for the absent callbacks was not independently established.

## Recommended remediation

For this vulnerability class, constrain server-side fetch destinations and egress. These are recommendations, not implemented fixes.

## Proposed retest

Future completion requires a unique, correlated callback on an authorized OAST service and platform confirmation.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `04-SSRF(1).md`. [Official lab](https://portswigger.net/web-security/ssrf/blind/lab-out-of-band-detection).
