# Secure file transfer: what the packet capture actually proves

[Back to portfolio](../../README.md)

**Environment:** Kali client, Ubuntu server, FileZilla, vsftpd, OpenSSH and Wireshark.  
**Status:** Transfer comparison completed; FTPS control-channel decryption confirmed. Full data-channel decryption is not established by the retained evidence.

## Question

Which parts of a file-transfer session remain readable on the network, and what changes when TLS or SSH is used?

## Work performed

I configured a dedicated transfer account and a passive FTP service, compared plaintext FTP with explicit FTPS, then used OpenSSH for SFTP. I captured the sessions in Wireshark, examined individual streams and checked uploaded files on the server. For FTPS, I enabled session-key logging in the client environment, verified that secrets were written, and loaded the key log in Wireshark for the matching capture.

## Results

| Mode | Recorded observation | Interpretation |
|---|---|---|
| FTP | USER, PASS, STOR and filenames were readable | Authentication and commands were exposed without transport encryption |
| Explicit FTPS | AUTH TLS, a TLS 1.3 handshake and encrypted application records | The control connection upgraded to TLS |
| FTPS passive data connection | A separate TLS-protected stream and no readable known file-content string in the shown search | The data connection must be investigated separately from the control connection |
| FTPS with matching session keys | Readable authentication and transfer commands after key-log loading | Control-channel decryption succeeded; this was access to session secrets, not a break of TLS |
| SFTP | SSH banners, handshake metadata and encrypted packets; a successful upload | SFTP used SSH rather than the FTP control/data-channel model |

## The troubleshooting lesson

The first apparent decryption failure came from looking for file contents in the wrong stream. FTP and FTPS have separate control and data connections. Recovering login and transfer commands demonstrates control-channel decryption, but does not by itself demonstrate recovery of the file body.

Unreadable bytes alone are weak evidence. Here, the protocol negotiation, encrypted-record decoding, successful transfer and matching-key decryption together support the conclusion.

## Security implications

Use a securely configured encrypted transfer protocol and validate the server identity. A self-signed certificate was used in this controlled lab; accepting a warning is not a general operational trust strategy. Protect TLS key logs like credentials: anyone with the relevant capture and secrets may be able to decrypt that session. Remove test logs when their authorized purpose is finished.

## Evidence

The assignment contains embedded FileZilla and Wireshark screenshots, an uploaded-file listing and a populated TLS key log. The Notion lab notes explicitly confirm control-channel decryption. Raw screenshots are withheld because they include credentials, session secrets, internal addresses and certificate identity details.

See [the evidence register](../../evidence/README.md). No packet capture or session secrets are distributed here.
