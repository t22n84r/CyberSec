# Windows endpoint-security lab: detection and execution evidence

[Back to portfolio](../../README.md)

**Scope:** Personal Windows/Kali training environment.  
**Evidence period:** Screenshots dated June–July 2026.  
**Status:** Defender detections and a later PowerShell shell session are visible; the complete causal chain and protection state are not established.

## Work represented

The screenshot sequence records Metasploit/Veil payload experimentation, document and executable packaging attempts, Windows Defender alerts, troubleshooting of local tool dependencies and a later reverse shell session. It also records archive/resource tooling used during the exercise.

## Observations

| Evidence | What it establishes | What it does not establish |
|---|---|---|
| Defender alert screenshots | The sample was detected; the UI reported incomplete remediation and failed quarantine | Successful cleanup or a clean endpoint |
| Payload/tool configuration screenshots | A training workflow was configured and artifacts were generated | Successful execution on the target |
| Handler output and Windows PowerShell prompt | A later shell session opened as a named Windows user | Administrator/SYSTEM privileges, persistence, or which earlier artifact produced it |
| Packaging and resource-tool output | Packaging steps and dependency troubleshooting were attempted | Reliable delivery or evasion of endpoint controls |

## Sanitized observation excerpts

```text
Windows Defender:
  Remediation incomplete
  Status: Quarantine failed

Later handler output:
  Command shell session opened
  Windows PowerShell running as user [LAB_USER] on [LAB_HOST]
```

These are selected transcriptions from separate screenshots, not a single continuous log. Private addresses, usernames, device identifiers and paths are omitted.

## Analysis

Detection, quarantine and prevention are different events. A detection alert with failed quarantine should lead to containment and investigation, not a claim that remediation succeeded. Likewise, a later shell session should not be labeled an antivirus bypass without correlated evidence showing the exact sample, execution path, protection settings and endpoint telemetry.

## Follow-up validation

For a repeat in a disposable isolated VM, record the sample identity, endpoint protection state, timestamped alert history, process tree, network connection and user context. Verify cleanup and restore a known-good snapshot before reuse. Those checks are proposed; the supplied screenshots do not establish that they were performed.

Executable payloads, disguised files, reusable delivery artifacts and generation scripts are not included in this documentation portfolio. The public contribution is the evidence interpretation and defensive lessons.
