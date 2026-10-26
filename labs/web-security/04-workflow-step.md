# Multi-step process with no access control on one step

[Portfolio](../../README.md) · [Lab index](README.md)

**Platform:** PortSwigger Web Security Academy  
**Date recorded:** 2026-09-02  
**Status:** Completed — recorded in lab notes  
**Mapping:** CWE-284

## Objective and scope

Investigate multi-step process with no access control on one step in the authorized training instance. The source is my written lab record; this publication does not include a fresh execution or independently retained platform certificate.

## Method and observed outcome

Replaying the final role-change confirmation with an ordinary session and confirmed=true promoted that user.

## Root cause and impact

An earlier workflow check did not protect the final state-changing action.

## Recommended remediation

Validate identity, role and workflow state at every sensitive step.

## Proposed retest

Call the final step directly and out of sequence; confirm both denial and unchanged roles.

These checks describe how I would validate a fix. I did not implement or retest a production remediation in this exercise.

## Evidence and limitations

Completion statements above reflect the supplied lab notes. Live lab URLs, session cookies, passwords, API keys and reset tokens are omitted. Original extraction scripts and raw final responses were not supplied; this repository does not present newly written code as historical work.

Source: `01-broken-access-control(3).md`. [Official lab](https://portswigger.net/web-security/access-control/lab-multi-step-process-with-no-access-control-on-one-step).
