# Cyber Heroes · Working notes

[Case study](README.md) · [Original notes](source/scopelog-export.md#research-notes)

These are lightly edited paraphrases of the two source notes. The original wording remains in the export.

## Open ports

**Source:** `N-9fa0f9fa-8384-432b-be3b-1595a7ebce85`

The open ports I recorded were 22 and 80. The service versions were OpenSSH 8.2p1 Ubuntu 4ubuntu0.4 and Apache httpd 2.4.48 on Ubuntu.

The note does not include the scan command, tool name, full output, or port range.

## Following the web service

**Source:** `N-a7f6290e-a86d-4269-b1f4-7f9c21aa8bc5`  
**Original title:** Found Flag

I saw that port 80 was open, opened the IP address in a browser, and went to the login page. I opened the inspector and found a JavaScript script. Its code used a simple conditional to check the username and password. I could read those values directly, so I entered them into the form.

The note title mentions a flag, but the body does not document a flag value or a successful flag submission. The generated narrative separately reports successful authentication.

## Follow-up documentation

These are suggested additions, not completed actions:

- Add the original authentication-script screenshot.
- Record the platform, room URL, testing date, and scope.
- Include the scan command and output if available.
- Add a redacted code excerpt and evidence of the resulting authenticated access.
- Record remediation or a retest only if one is actually performed.
