# SSRF with whitelist-based input filter

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-28  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-918

## Objective and scope

Investigate ssrf with whitelist-based input filter in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

A crafted stock URL combining URL user information and a double-encoded fragment marker passed the allowlist and reached localhost. The notes record the target-user deletion and completed lab.

## Root cause and impact

The validator and outbound request path interpreted the URL differently. The precise parser and decoding sequence is an inference, not a source-code finding.

## Recommended remediation

Use a consistent URL parser and canonicalization path, validate resolved destinations, and enforce network egress restrictions.

## Proposed retest

Test encoded delimiters, user information, redirects and alternate address representations while verifying the actual outbound destination.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `04-SSRF(1).md`. [Official lab](https://portswigger.net/web-security/ssrf/lab-ssrf-with-whitelist-filter).
