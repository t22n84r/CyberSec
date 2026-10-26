# From service enumeration to an exposed root shell

[Back to portfolio](../../README.md)

**Environment:** Kali and an intentionally vulnerable Metasploitable training VM.  
**Recorded scan date:** June 6, 2026.  
**Status:** Screenshot-supported service enumeration and root-shell access.

## Method

I performed a full TCP port scan, then ran service/version detection and default scripts against the discovered ports. I investigated TCP/1524 with a Netcat-compatible client and used identity commands to establish the privilege of the returned shell.

Representative commands, with the original address removed:

```bash
sudo nmap -p- --min-rate 5000 -T4 <LAB_TARGET_IP>
sudo nmap -sV -sC -p <DISCOVERED_TCP_PORTS> <LAB_TARGET_IP>
nc -nv <LAB_TARGET_IP> 1524
```

These commands describe the historical, authorized lab workflow. Aggressive timing is environment-specific; a fast scan is not a guarantee that every service has been found.

## Evidence and result

The scan screenshot lists services including FTP, SSH, Telnet, HTTP, SMB, databases and TCP/1524 labeled ingreslock. A service label alone does not establish what a port actually runs. The connection and returned identity output provide the decisive evidence.

Sanitized transcription from the shell screenshot; host/address details omitted:

```text
[TCP connection to lab target on port 1524 succeeded]
id
uid=0(root) gid=0(root) groups=0(root)
whoami
root
pwd
/
```

This was direct access to an already exposed privileged shell. It does not demonstrate a separately executed privilege-escalation exploit, exploitation of every discovered service, or a complete vulnerability assessment.

## Impact and defensive response

An unauthenticated root shell gives a connecting party administrative control. In an operational environment, investigate and remove the unauthorized listener, preserve appropriate evidence, rebuild from trusted media when compromise is suspected, and review credentials and network boundaries. For this intentionally vulnerable VM, isolation is part of the lab design.

## Proposed retest

Verify that the listener is gone, the port is unreachable from disallowed sources, authorized administration still works and the service cannot return after reboot. These remediation tests were not performed as part of the supplied exercise.

## Sources

Assignment 2 and three standalone screenshots: full port discovery, detailed service enumeration and Netcat shell validation. [Evidence register](../../evidence/README.md).
