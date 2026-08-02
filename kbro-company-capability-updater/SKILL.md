---
name: kbro-company-capability-updater
description: Review one or more new kbro company-information, capability, project, case-study, weekly-report, monthly-report, financial, staffing, certification, or operational files; compare them with the synchronized latest kbro capability baseline; propose exact additions, updates, conflicts, and exclusions; wait for explicit user approval; then create, verify, version, and save a new Word baseline to both the approved local and Google Drive locations without overwriting prior versions. Use when the user supplies local paths, Google Drive file URLs or IDs, or Drive folder URLs and asks to update kbro's company profile, capabilities, experience, tender-readiness evidence, financial scale, or reusable comparison baseline.
---

# kbro Company Capability Updater

Update the reusable kbro company baseline from one or more new evidence files. Preserve every source and prior baseline.

## Required configuration

Read [references/kbro-company-config.md](references/kbro-company-config.md) before acting. Treat its local path, Drive boundary, latest-baseline rule, naming rule, and synchronization checks as mandatory.

## Workflow

### 1. Ground every input

1. Classify each input as a local file, Google Drive file URL or ID, or Google Drive folder URL.
2. Verify local files are readable. For Drive files, read metadata before fetching or exporting.
3. For a Drive folder, list direct children and identify supported evidence files. Ask the user only when the intended files cannot be determined safely.
4. Support PDF, PPT, PPTX, DOC, DOCX, ODP, XLS, XLSX, CSV, and clearly readable image evidence.
5. Preserve all source files. Do not rename, move, edit, upload, or overwrite them unless the user separately requests source archiving.
6. Classify each source as internal kbro evidence, public company information, third-party evidence, competitor intelligence, tender material, or unclear.
7. Exclude competitor-only claims from kbro-owned capabilities. Route a competitor comparison request to `kbro-competitor-assessment`.

### 2. Resolve the synchronized latest baseline

1. List baseline candidates in both configured Local and Cloud locations.
2. Parse semantic versions from canonical filenames. Use the update date only as a tie-breaker.
3. Treat a byte-identical legacy filename as an alias, not another version.
4. Confirm the highest canonical version exists in both locations with the same filename and content. Download and hash when metadata alone cannot prove equality.
5. Stop and report the mismatch if one side is newer, a same-name file differs, or candidates cannot be ordered confidently. Do not guess, overwrite, or continue from only one side without explicit user direction.
6. Never use a hard-coded baseline version. Record the resolved filename, version, update date, Local path, and Cloud file ID.

### 3. Read and assess the evidence

Use the relevant installed artifact skills and read the complete material:

- PDF: PDF skill, including every relevant page.
- PPT, PPTX, or ODP: Presentations skill, including every slide.
- DOC or DOCX: Documents skill, including all paragraphs, tables, notes, and sources.
- XLS, XLSX, or CSV: Spreadsheets skill, including relevant sheets, formulas, notes, and date ranges.
- Images: inspect the original-resolution image and use OCR only when needed.

Browse when current public facts require verification. Prefer government, regulator, official company, audited, and primary sources. Record the source URL and review date.

Keep these evidence states separate:

- verified completed or operating evidence;
- signed, ordered, or executing work;
- concrete proposal or designed solution;
- evaluation, POC, negotiation, pipeline, or plan;
- unsupported, conflicting, stale, or partner-dependent claim.

Do not promote a proposal, POC, weekly pipeline item, partner capability, or competitor claim into a completed kbro capability.

### 4. Produce the pre-approval change proposal

Before editing any baseline or uploading any output, present one complete proposal containing:

- resolved current baseline filename and version;
- each proposed addition;
- each proposed modification, including old and new wording or meaning;
- the target section for each change;
- source file, page, slide, sheet, or public URL;
- evidence state and confidence;
- tender or competitor-comparison relevance;
- items that should not be added and why;
- conflicts, stale facts, and internal confirmations still required;
- proposed next filename and version.

Classify every reviewed item as `Add`, `Update`, `No change`, `Exclude`, or `Needs confirmation`.

Stop and wait for explicit user approval. Do not create, edit, upload, rename, or replace the baseline before approval. If the user approves only selected items, implement only those items.

### 5. Create the approved new baseline

1. Start from the synchronized latest baseline, never from an older draft or a source file.
2. Apply only the approved changes and preserve the existing layout, evidence model, terminology, calculations, and unsupported-capability boundaries.
3. Add a visible version-update block near the top containing:
   - new version and update date;
   - additions in this version;
   - modified facts or conclusions;
   - removed or superseded statements, if any;
   - important limitations or required confirmations.
4. Update the visible version label and document metadata.
5. Include source links and source dates near the added material or in a clearly labeled source section.
6. Use the canonical filename and next semantic version from the configuration.
7. Never overwrite or rename an earlier Local or Cloud baseline.

### 6. Verify the Word document

Use the Documents skill's strict edit and render workflow:

1. Preserve the original document structure and apply minimal local edits.
2. Render the new DOCX to page images and inspect every page.
3. Check headings, numbering, tables, hyperlinks, Chinese glyphs, clipping, overflow, overlap, awkward page breaks, and the version-update block.
4. Re-render after fixes until all pages pass.
5. If the renderer is unavailable, perform structural, ZIP, text-order, table, hyperlink, and file-open checks and disclose that full visual QA was not completed.

### 7. Save and synchronize

1. Save the verified DOCX to the configured Local company-output directory.
2. Upload the exact same DOCX as a new file to the configured Cloud company-output folder.
3. Refuse same-name overwrite. Increment the version when a filename already exists.
4. Verify the Cloud upload by metadata or folder readback.
5. Re-list Local and Cloud candidates and confirm the same latest filename and byte size. Compare hashes when both byte streams are available.
6. Confirm all prior versions remain present.
7. If either save or verification fails, report the partial state and do not claim synchronization.

## Completion report

Return:

- new baseline version and concise update summary;
- Local file link;
- Cloud file link;
- number of pages visually inspected, or the exact QA fallback used;
- synchronization result;
- evidence limitations that still affect tender or competitor comparisons.

State that future tender and competitor assessments must resolve this synchronized latest baseline rather than a fixed historical version.
