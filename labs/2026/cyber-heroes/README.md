# Cyber Heroes

**From an open web service to exposed login credentials.**

[Portfolio](../../../README.md) · [Findings](findings.md) · [Evidence](evidence/README.md) · [Working notes](notes.md) · [Original export](source/scopelog-export.md)

| Field | Record |
| --- | --- |
| Report prepared | 2026-10-03 UTC |
| Testing date | Not recorded |
| Platform / room URL | Not recorded in the export |
| Project status | Complete, as recorded in ScopeLog |
| Focus | Service discovery, web enumeration, JavaScript inspection, authentication |
| Findings | 1 · Critical as recorded · Open |
| Evidence | 1 screenshot referenced; image not supplied |

## Overview

The login page exposed the username and password it checked inside browser-accessible JavaScript. My notes describe finding that check and entering the visible credentials. The generated report says this produced access to the admin panel; the supplied records do not include a screenshot of the authenticated result.

The core issue was a login mechanism that put its credentials and comparison logic in code delivered to the browser.

## Scope and evidence

The source identifies `http://10.146.163.97/login.html` and records SSH and HTTP services. It contains no formal scope, authorization record, scan command, or complete scan output. The address is retained as historical context from the lab report.

This case study is based on the supplied ScopeLog export. Its AI-generated narrative has been checked against the finding and working notes, but the referenced screenshot was not included. No new testing was performed for this writeup.

## Investigation

### 1. Identify the available services

My notes recorded these two open ports:

| Port | Service | Recorded banner |
| --- | --- | --- |
| 22/tcp | SSH | OpenSSH 8.2p1 Ubuntu 4ubuntu0.4; protocol 2.0 |
| 80/tcp | HTTP | Apache httpd 2.4.48; Ubuntu |

Port 80 gave me a web application to investigate. The records do not identify the scanner or establish coverage of all ports, and a service banner alone does not establish a vulnerability.

Source: research note `N-9fa0f9fa-8384-432b-be3b-1595a7ebce85`.

### 2. Inspect the login page

After seeing HTTP open, I opened the target in a browser and went to the login page. I used the browser inspector to look at the page's JavaScript.

The code contained a simple conditional check against a username and password. Both values were readable in the script. The export does not include the actual script, its filename, or the credential values.

### 3. Use the exposed credentials

My working note describes entering the username and password found in the script. The report's generated narrative records successful authentication and admin-panel access. That outcome is retained as reported, with the distinction that the screenshot and a post-login capture are unavailable here.

Source: research note `N-a7f6290e-a86d-4269-b1f4-7f9c21aa8bc5` and finding `F-f66e58ff-511b-42f6-87f2-77640942ef67`.

## Finding at a glance

| Finding | Recorded severity | Status | Detail |
| --- | --- | --- | --- |
| Hardcoded credentials in client-side JavaScript | Critical | Open | [Finding and remediation](findings.md#hardcoded-credentials-in-client-side-javascript) |

The Critical label comes from the original report. No CVSS score, independently verified privilege level, or wider business impact was recorded.

## Outcome

ScopeLog marks the project complete. The finding remains open, and no fix or retest is documented. A note is titled "Found Flag," but its body only describes discovering and using the credentials; no flag value or separate flag-submission result was supplied.

## Technical takeaways

These are takeaways derived from the recorded finding:

- Inspecting browser-delivered code can reveal authentication mistakes without complex tooling.
- A value sent to the browser cannot be treated as a hidden server secret.
- Obfuscating a script or moving credentials into another public file does not fix the underlying exposure.
- Better evidence would include the relevant code, the exact request path, and the authenticated result with sensitive values redacted.

The [detailed finding](findings.md) separates the proposed authentication fix from what was actually tested.
