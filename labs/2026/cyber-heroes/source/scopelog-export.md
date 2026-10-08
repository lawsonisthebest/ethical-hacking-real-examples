# Cyber Heroes assessment report

**Cyber Heroes** · Security assessment

Prepared 2026-10-03 (UTC) · Project status: Complete

> Draft for review · Point-in-time snapshot
>
> AI-assisted narrative generated with OpenRouter. Verify the narrative against the source records before finalizing.

## Contents

1. Executive summary
2. Scope and methodology
3. Findings overview
4. Recommendations
5. Detailed findings
6. Evidence register
7. Research notes

## Executive summary

1 findings, 1 evidence records, and 2 research notes were captured for this assessment. 1 findings remain unresolved, including 1 rated High or Critical. Recorded severities inform remediation priority; they do not establish business risk or test coverage.

### Assessment narrative

A critical vulnerability \(F\-f66e58ff\-511b\-42f6\-87f2\-77640942ef67\) was identified where admin credentials were hardcoded in client\-side JavaScript on the login page \(E\-e91d8d1a\-dd78\-4a70\-87d3\-ab223d660dad\)\. This allowed unauthorized access to the admin panel by inspecting page source \(N\-a7f6290e\-a86d\-4269\-b1f4\-7f9c21aa8bc5\)\. Network scanning revealed open ports 22 \(SSH\) and 80 \(HTTP\) \(N\-9fa0f9fa\-8384\-432b\-be3b\-1595a7ebce85\)\. The vulnerability remains open\.

## Scope and methodology

### Recorded scope

No project scope was recorded.

### Basis and limitations

This report compiles the project records available at generation time. Testing methods, authorization, affected targets, and reproduction steps are established only where explicitly documented in those records. Evidence attachments and linked pages are referenced, not automatically opened or analyzed. Research notes are working material, not independently verified findings.

### Recorded approach — AI synthesis

The assessment began with network scanning identifying open ports 22 and 80 \(N\-9fa0f9fa\)\. The tester accessed the login page and used browser developer tools to inspect client\-side scripts \(E\-e91d8d1a\-dd78\-4a70\-87d3\-ab223d660dad\)\. Analysis of the JavaScript code revealed hardcoded credentials \(N\-a7f6290e\-a86d\-4269\-b1f4\-7f9c21aa8bc5\), which were extracted and used to successfully authenticate, confirming the critical vulnerability\.

## Findings overview

- **Critical:** 1 findings
- **High:** 0 findings
- **Medium:** 0 findings
- **Low:** 0 findings
- **Informational:** 0 findings

- **F-f66e58ff-511b-42f6-87f2-77640942ef67 · Username & Password** — Critical; Open; Vulnerability

## Recommendations

1. Prioritize investigation and remediation of the High and Critical findings: F-f66e58ff-511b-42f6-87f2-77640942ef67.
2. Review remaining unresolved findings in severity order, assign owners, and agree target dates.
3. Verify each fix with a documented retest and retain supporting evidence before closing the finding.

### Suggested next steps — AI synthesis

1\. Remove hardcoded credentials from client\-side code \(F\-f66e58ff\-511b\-42f6\-87f2\-77640942ef67\)\. 2\. Implement robust server\-side authentication with hashed password storage\. 3\. Ensure sensitive files are not accessible to the public\. 4\. Conduct regular code reviews to prevent leakage of secrets in client\-side scripts\.

## Detailed findings

### Username & Password

**Reference:** F-f66e58ff-511b-42f6-87f2-77640942ef67

**Severity:** Critical · **Status:** Open · **Category:** Vulnerability

Inside the login page, in the inspector panel, there is a JavaScript file that has the admin username and password\. It just runs a simple if statement to see if the username and password are correct in the input fields\. 

It is not encrypted, it is not secret, and it is written poorly in the code\.

## Evidence register

### Authentication Details Script

**Reference:** E-e91d8d1a-dd78-4a70-87d3-ab223d660dad

**Type:** Screenshot · **Category:** Security issue

This shows that any user can go into the inspector panel and find the username and password needed to log into the admin\. It should be encrypted, stored safely in a separate file, and managed more securely\.

**Source:** http://10\.146\.163\.97/login\.html

**Attachment:** Screenshot \(2\)\.png (1,568,648 bytes)

**SHA-256:** 51fc0e3ae3c6e32ef570a4640beae7964507ab8471c1b6bba6158e05257950be

## Research notes

### Open ports

**Reference:** N-9fa0f9fa-8384-432b-be3b-1595a7ebce85

The only open ports i found was 22 and 80 and here is the current versions: 22/tcp open  ssh     OpenSSH 8\.2p1 Ubuntu 4ubuntu0\.4 \(Ubuntu Linux; protocol 2\.0\)
80/tcp open  http    Apache httpd 2\.4\.48 \(\(Ubuntu\)\)

---

### Found Flag

**Reference:** N-a7f6290e-a86d-4269-b1f4-7f9c21aa8bc5

I first saw that port 80 was open, so I opened the browser and typed in the IP\. I went over to the login page, and then I pulled up the inspector\. Inside the inspector, I found a JavaScript script\. 

In that script, I read the code, and it was just a simple if statement to check if the username and password group was correct\. I just typed in that username and password because it was not hidden, coded, decoded, or encrypted at all, so I was able to read it\.