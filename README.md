# Ethical Hacking · Real Examples

Hands-on security labs, findings, and the reasoning behind them.

I use this repository to document the labs I work through on TryHackMe and other ethical hacking platforms. Each entry shows what I investigated, what I found, the evidence I recorded, and what I learned. I capture my work in ScopeLog, then turn those records into writeups I can revisit and share.

## Lab index

| Lab | Report date | Focus | Recorded outcome | Writeup |
| --- | --- | --- | --- | --- |
| Cyber Heroes | 2026-10-03 | Web enumeration · JavaScript inspection · Authentication | Exposed credentials used to log in; project marked complete | [Read case study](labs/2026/cyber-heroes/README.md) |

Dates in this index are report dates unless an entry explicitly records a testing date. Project completion and vulnerability remediation are tracked separately.

## Start here

**[Cyber Heroes](labs/2026/cyber-heroes/README.md)** — An open HTTP service led to a login page whose JavaScript exposed the credentials it checked. This entry follows the investigation from service discovery to the recorded login result.

## How entries are organized

Each assessment lives in `labs/<year>/<lab-slug>/`. The year comes from the recorded assessment or report date. Entries without a recorded date use `labs/undated/`.

| File | What you will find |
| --- | --- |
| `README.md` | The case study: overview, investigation, outcome, and lessons |
| `findings.md` | Technical findings, impact, reproduction, remediation, and retest status |
| `notes.md` | Working notes, decisions, and open questions |
| `evidence/README.md` | Evidence descriptions, availability, and source references |
| `evidence/` | Screenshots and supporting files when supplied |
| `source/scopelog-export.md` | The original report, with any necessary public-sharing redactions documented |

## Adding the next lab

Send the complete ScopeLog export and any evidence attachments to the assistant with a request to add it to this repository. The [import workflow](docs/scopelog-workflow.md) and [writeup template](templates/lab-writeup.md) keep new entries consistent. [Repository instructions](AGENTS.md) describe how to preserve the source, update the index, and avoid inventing missing details.

This is an assistant-driven workflow when a report is provided in chat. There is no background connection to ScopeLog.

## About the records

This portfolio is for training labs and authorized security work. Entries distinguish recorded observations from interpretation and proposed improvements. Source exports may contain AI-assisted summaries; raw notes and supplied evidence take priority when those summaries overstate what was recorded. Missing evidence and unverified claims are identified within each entry.
