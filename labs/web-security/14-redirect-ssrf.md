# SSRF with filter bypass via open redirection vulnerability

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-27  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-918; CWE-601

## Objective and scope

Investigate ssrf with filter bypass via open redirection vulnerability in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

A stock-fetch endpoint accepted a same-origin URL leading to an open redirect. Following the redirect reached an internal lab administration interface. The notes record internal-host discovery and completion of the target deletion.

## Root cause and impact

Destination validation did not remain effective across redirects.

## Recommended remediation

Validate every redirect hop and final resolved destination; restrict outbound access and remove the open redirect.

## Proposed retest

Test direct and redirected internal destinations, including redirect chains; legitimate stock requests should still succeed.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `04-SSRF(1).md`. [Official lab](https://portswigger.net/web-security/ssrf/lab-ssrf-filter-bypass-via-open-redirection).
