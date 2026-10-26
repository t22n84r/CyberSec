# Blind SQL injection with time delays and information retrieval

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-26  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-89

## Objective and scope

Investigate blind sql injection with time delays and information retrieval in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

A PostgreSQL-style delay probe produced a recorded delay of about ten seconds. Conditional delays then served as a timing oracle for password extraction. The notes record an adapted Python routine and successful administrator login.

## Root cause and impact

Database-controlled delays exposed information even when response content did not change. Timing evidence requires controls for ordinary network variation.

## Representative request pattern

This excerpt is a sanitized reconstruction from the notes, not a retained raw HTTP capture.

```sql
'||(SELECT CASE WHEN ((SELECT ASCII(SUBSTRING(password,<position>,1)) FROM users WHERE username='administrator')><mid>) THEN pg_sleep(<delay>) ELSE pg_sleep(0) END)||'
```

## Recommended remediation

Parameterize queries, restrict database privileges and investigate unusual query latency.

## Proposed retest

Compare repeated baseline and conditional probes under stable conditions; injected conditions must no longer control delay.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `03-sql-injection(1).md`. [Official lab](https://portswigger.net/web-security/sql-injection/blind/lab-time-delays-info-retrieval).
