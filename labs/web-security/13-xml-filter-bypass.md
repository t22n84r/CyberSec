# SQL injection with filter bypass via XML encoding

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-26  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-89

## Objective and scope

Investigate sql injection with filter bypass via xml encoding in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Raw SQL probes in the XML stock-check request were blocked. XML numeric character references passed the filter and were decoded downstream. A single-column UNION result returned concatenated lab credentials, followed by administrator login.

## Root cause and impact

The request filter and application interpreted differently encoded input, while the SQL sink remained injectable.

## Recommended remediation

Fix the query with parameterization; use consistent parsing and normalization as defense in depth.

## Proposed retest

Test raw and encoded variants; verify that neither can alter the query and legitimate stock checks still work.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `03-sql-injection(1).md`. [Official lab](https://portswigger.net/web-security/sql-injection/lab-sql-injection-with-filter-bypass-via-xml-encoding).
