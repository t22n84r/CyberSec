# Python traffic-inspection prototype

[Back to portfolio](../README.md)

**Status:** Project documented in personal notes; original source code, test logs and screenshots were not supplied for this portfolio.

## Purpose and recorded work

My project notes describe an AI-assisted Python GUI proxy built with socket, threading and tkinter. The intended use was to highlight plaintext HTTP traffic, show connection problems and export text logs during controlled browser tests. The notes also record troubleshooting Chromium proxy routing using launch-time configuration.

## My contribution

The documented work focused on defining the inspection behavior, shaping the user interface, testing browser connectivity and troubleshooting the browser’s proxy configuration, with AI assistance for implementation and debugging.

## Technical boundaries

The notes do not establish TLS interception or decrypted HTTPS contents. Handling HTTPS CONNECT tunnels is distinct from terminating TLS. Likewise, forcing a browser to use a proxy does not prove that every protocol or every application request was captured. This portfolio therefore omits the original narrative’s “100% traffic capture” claim and does not describe the prototype as an independently audited security product.

## What would make this a reproducible code project

Recover the original source, remove secrets and real captured traffic, document supported protocols, add bounded connection handling and representative tests, and publish installation and usage instructions. Until then, this entry is a project narrative, not a runnable repository component.

Source: the Tooling page under Cybersec resume building notes in Notion. Repeated copies of the same narrative were treated as one project.
