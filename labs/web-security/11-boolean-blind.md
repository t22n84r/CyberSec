# Blind SQL injection with conditional responses

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-23  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-89

## Objective and scope

Investigate blind sql injection with conditional responses in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

The TrackingId cookie exposed a boolean oracle through the presence or absence of a welcome message. The notes record length discovery and character extraction with a Python binary-search routine, followed by administrator login. An attempted sqlmap workflow did not finish.

## Root cause and impact

Conditional query behavior leaked sensitive data without directly returning query results. The retained evidence does not establish a specific DBMS or the cause of the sqlmap failure.

## Recommended remediation

Parameterize the tracking query and minimize database permissions.

## Proposed retest

Compare paired true/false probes after remediation; injected conditions must not influence application behavior.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `03-sql-injection(1).md`. [Official lab](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses).
