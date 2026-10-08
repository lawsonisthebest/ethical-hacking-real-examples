# ScopeLog → GitHub

[Back to portfolio](../README.md)

## What to send

Paste or attach the full ScopeLog report after a lab. Include screenshots or other evidence separately: an exported filename and checksum do not contain the actual attachment. A room URL, platform name, testing date, and any additional personal notes are useful when the export does not include them.

You can use this request:

> Add this ScopeLog report to `lawsonisthebest/ethical-hacking-real-examples`. Follow the repository's AGENTS.md, preserve the source report, organize the writeup and evidence, and update the main index. Use only the information I provide and mark missing details clearly.

## What gets created

| Destination | Content |
| --- | --- |
| `labs/<year>/<lab-slug>/README.md` | Overview, investigation, reasoning, outcome, and takeaways |
| `labs/<year>/<lab-slug>/findings.md` | Findings with source IDs, supporting evidence, remediation, and retest status |
| `labs/<year>/<lab-slug>/notes.md` | Working notes and unresolved questions |
| `labs/<year>/<lab-slug>/evidence/README.md` | An inventory of supplied and missing evidence |
| `labs/<year>/<lab-slug>/source/scopelog-export.md` | Preserved source export, redacted only when needed for public sharing |
| Root `README.md` | A new or updated row in the lab index |

The same lab and assessment should update its existing entry. A distinct attempt can have a separate entry with a recorded date suffix. Git history preserves earlier published versions.

## Editorial standard

The writeup should explain both the technical result and how the investigation reached it. Keep observations grounded in the source. Treat AI-generated summaries as drafts, and identify missing commands, screenshots, scope, or validation instead of filling gaps with guesses.

Use the original severity as a recorded assessment label, not an independently established risk rating. Record a fix or successful retest only when supporting information is supplied.

For public entries, remove actual private credentials, tokens, personal information, and flag values when present. Document any redactions without reproducing the removed values. Keep the evidence useful and never claim a modified attachment matches its original checksum.

## Adding evidence later

Supply the missing file and identify its lab. Add it under the existing `evidence/` folder, link it from the evidence register, and calculate its checksum if the actual bytes are available. State whether that checksum matches the original export. Update the entry's evidence limitation only after reviewing the supplied file.

## How the workflow runs

Imports happen when you provide a report in chat and ask the assistant to update this repository using GitHub access. Repository instructions keep the format reusable across sessions. This setup does not monitor ScopeLog or sync exports without a chat request.
