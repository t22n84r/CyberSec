# SQL injection UNION attack, retrieving data from other tables

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-21  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-89

## Objective and scope

Investigate sql injection union attack, retrieving data from other tables in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Quote and one-column UNION probes produced errors. A two-column UNION succeeded; text probes established compatible output positions. The lab supplied the table and column names. Retrieving those fields led to administrator login.

## Root cause and impact

User input influenced SQL structure and returned data outside the intended product query.

## Representative request pattern

This excerpt is a sanitized reconstruction from the notes, not a retained raw HTTP capture.

```http
GET /filter?category=Gifts HTTP/1.1
Host: <lab-instance>
```

## Recommended remediation

Use parameterized queries and restrict the application database account.

## Proposed retest

Repeat quote and UNION probes; confirm inputs are treated as data and normal category filtering still works.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `03-sql-injection(1).md`. [Official lab](https://portswigger.net/web-security/sql-injection/union-attacks/lab-retrieve-data-from-other-tables).
