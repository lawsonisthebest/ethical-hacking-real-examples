# Repository instructions

## Purpose

Maintain a readable portfolio of the owner's ethical hacking labs using ScopeLog exports and other supplied assessment records. When the owner requests an import, complete the entry and update the repository index in the same change.

## Standing workflow preference

The owner explicitly requested on 2026-10-08 that future ScopeLog reports, pasted assessment documents, and screenshots of similar ethical hacking lab reports be treated as requests to create or update an entry in `lawsonisthebest/ethical-hacking-real-examples`, without requiring the owner to repeat the workflow. Apply this when the material is clearly a lab assessment; honor any different instruction supplied with it.

Use the established Cyber Heroes structure and `templates/lab-writeup.md`, organize the findings, evidence, and thought process, preserve the supplied source, update the homepage index, and publish through the available authorized GitHub connection. If a report screenshot only contains part of a document, use only its readable content and mark missing or unreadable details. Save screenshot-derived text as `source/report-transcription.md`, label it as a partial transcription where applicable, and retain the supplied image when accessible; do not call it a complete original ScopeLog export. Update links to match the actual source filename.

This preference describes chat-triggered imports, not background monitoring of ScopeLog.

## Import procedure

1. Read the root README, this file, `docs/scopelog-workflow.md`, and any existing entry that matches the supplied lab.
2. Use `labs/<year>/<lab-slug>/`. Derive the year from a documented assessment date, then the report date; use `undated` if neither exists. Use lowercase, hyphen-separated slugs.
3. Match room name, platform when known, dates, and source record IDs before creating a new entry. Update the same assessment rather than duplicating it. Give a separate attempt a date suffix when its date is known.
4. Preserve the supplied export in `source/scopelog-export.md`. Inspect it before public publication for private information, actual secrets, and flags. If redaction is necessary, use clear placeholders and describe the redactions; do not describe a redacted copy as byte-for-byte original. Keep legitimate technical context.
5. Create or update `README.md`, `findings.md`, `notes.md`, and `evidence/README.md` using the template and the Cyber Heroes entry as references. Only include relevant sections; do not add empty filler files.
6. Preserve source finding, evidence, and note IDs so readers can trace each claim. Keep original severity and status, labeling them as recorded values. Do not invent a CVSS score or silently reinterpret an unresolved finding as fixed.
7. Add supplied evidence files with readable names and relative links. A referenced attachment is not an attached file. Mark absent files as not supplied; never fabricate an image, output, checksum verification, or evidence link.
8. Update the root lab index, sorted by report or assessment date newest first, with undated entries last. Use an accurate, concise outcome and a working relative link.
9. Check local links, source fidelity, sensitive content, and consistency before committing. Follow the owner's authorized GitHub workflow and preserve unrelated files. Never force-push over other changes.
10. Verify the resulting GitHub files and return the entry link with any material missing evidence.

## Writing rules

- Use direct, natural language. Use first person only when faithfully paraphrasing the owner's recorded actions or reasoning.
- Separate observed results, inference, suggested remediation, and tests that have not been performed.
- Source notes and supplied evidence take priority over AI-generated narrative. Explicitly qualify claims that only appear in the generated narrative.
- Do not invent platform URLs, difficulty, tools, commands, dates, flags, credentials, scope, authorization records, successful exploitation, or business impact.
- Do not infer that every port was scanned because only two open ports were listed.
- A completed lab does not mean its findings were remediated. Keep these statuses separate.
- Improve inaccurate technical advice in the curated writeup and explain significant corrections while preserving the source record.
- Keep GitHub Markdown readable: descriptive headings, short tables, fenced output where supplied, and relative file links.
- Do not include comments in code.
- Do not add a background service, paid integration, or scheduled job merely to import a report.
