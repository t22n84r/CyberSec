# Blind SSRF with Shellshock exploitation

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-30  
**Status:** Unconfirmed — not solved  
**Mapping:** CWE-918; CWE-78

## Objective and scope

Investigate blind ssrf with shellshock exploitation in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

The intended blind-SSRF-to-Shellshock chain was studied and partly attempted. No callback or command output was captured, and the lab was not solved.

## Root cause and impact

The lab describes SSRF delivery to a vulnerable internal service. No independent RCE finding is claimed. The official exercise restricts callbacks to its public Collaborator service.

## Recommended remediation

Patch vulnerable Bash, remove unsafe shell execution paths, constrain server-side fetches and restrict egress.

## Proposed retest

Future validation requires correlated out-of-band evidence and platform completion; proposed fixes have not been applied or retested.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `04-SSRF(1).md`. [Official lab](https://portswigger.net/web-security/ssrf/blind/lab-shellshock-exploitation).
