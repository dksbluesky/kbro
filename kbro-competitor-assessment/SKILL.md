---
name: kbro-competitor-assessment
description: Compare a competitor project presentation or document against the synchronized latest kbro company-capability baseline; apply a consistent scenario-based 0-100 execution-feasibility score; assess Pros, Cons, evidence gaps, remediation needs, partner roles, target industries and named companies; create and visually verify a Word report; and, after explicit approval, archive the source and report in the approved kbro Google Drive tree. Use when the user provides a local path, Google Drive file URL or ID, or Drive folder URL containing a PDF, PPT, PPTX, DOC, DOCX, or ODP and asks for a kbro competitor comparison, project feasibility assessment, scored Word report, or the same assessment-and-upload workflow used for CHT.
---

# kbro Competitor Assessment

Execute the complete workflow from one local path or Google Drive reference. Ask a question only when a required identity, source, or permission cannot be grounded safely.

## Required configuration

Read [references/kbro-config.md](references/kbro-config.md) before acting. Treat its project root, capability-baseline rule, output convention, and Google Drive boundary as mandatory.

Read [references/scoring-framework.md](references/scoring-framework.md) before scoring or drafting the report. Apply its score anchors, weights, evidence rules, scenario separation, confidence label, and required report presentation consistently.

## Workflow

### 1. Ground the input

1. Classify the input as a local file path, Google Drive file URL or ID, or Google Drive folder URL.
2. For a local path, verify it resolves to a readable file.
3. For a Drive file, read metadata first to confirm its MIME type, then fetch or export it with the Google Drive plugin as appropriate.
4. For a Drive folder, list its direct contents. Automatically select the source only when exactly one supported competitor document is present; otherwise ask the user to identify the intended file.
5. Preserve the source file; do not rename, move, edit, or overwrite it.
6. Infer the competitor name and project title from the filename and content.
7. Ask the user only if the competitor identity remains ambiguous after reading the source.
8. List company-baseline candidates in both configured Local and Cloud locations.
9. Resolve the highest canonical semantic version using the rule in `kbro-config.md`; use the filename date only as a tie-breaker.
10. Confirm the same latest filename and content exist in both Local and Cloud. Download and hash when metadata cannot prove equality.
11. Treat a byte-identical legacy filename as an alias, not another version.
12. Stop and report the mismatch if Local and Cloud differ, one side is newer, a same-name file differs, or candidates cannot be ordered confidently. Do not start the comparison from only one side without explicit user direction.
13. Record the resolved baseline filename, version, update date, Local path, and Cloud file ID. Never use a hard-coded historical baseline.

### 2. Read all evidence

Use the relevant installed artifact skills:

- PDF input: use the PDF skill and inspect every page.
- PowerPoint or ODP input: use the Presentations skill and inspect every slide.
- Word input: use the Documents skill and inspect the complete document.

Separate these evidence classes throughout the analysis:

- competitor claims or demonstrations;
- actual project requirements inferred from the source;
- verified kbro evidence from the capability baseline;
- assumptions, missing evidence, or partner-dependent capability.

Never equate “not documented” with “kbro cannot do it.” Phrase it as an evidence gap until verified.

Never use competitor material to update the kbro company baseline. If the source contains credible new kbro-owned evidence, report it separately and recommend running `kbro-company-capability-updater` with that evidence.

### 3. Research only what the sources cannot establish

Browse when current or external facts are needed, especially for named target customers, partner capabilities, standards, or market claims. Prefer official company, government, university, NGO, and vendor sources. Add direct hyperlinks to the report.

Do not invent customer demand, procurement intent, budgets, contracts, certifications, project status, or kbro delivery evidence.

### 4. Make the feasibility decision

Assess at least:

1. network and optical infrastructure;
2. field engineering and system integration;
3. data center, HPC, cloud, or cross-site computing;
4. AI, model operations, and measurable accuracy;
5. AIoT devices, sensors, calibration, and environmental durability;
6. data platform, governance, APIs, backup, and lifecycle;
7. cybersecurity, privacy, resilience, and compliance;
8. operations, NOC, SLA, spares, and recovery;
9. domain expertise and ecosystem partners;
10. commercial capacity, qualifications, insurance, contractual responsibility, and referenceability.

Give separate conclusions when the source contains materially different solution layers. Use calibrated outcomes such as:

- currently not recommended as prime contractor;
- feasible only with named partner roles and evidence gates;
- recommended as a bounded POC;
- viable with current evidence.

Score every materially different execution scenario or role separately. Examples include prime contractor, alliance or subcontract role, formal regional AIoT project, and bounded single-site POC. Do not average unlike scenarios into one headline score.

Apply the mandatory method in `references/scoring-framework.md`:

1. Score the six weighted dimensions using evidence available at the review date.
2. Calculate the weighted raw score.
3. Map it to the standard reporting anchor: 0, 30, 60, 80, or 100.
4. State the anchor definition beside the score.
5. Explain the main reasons, required kbro role, partner dependencies, and evidence gates.
6. Add current-to-target score improvement conditions.
7. State confidence as high, medium, or low and explain material limitations.

Include:

- executive conclusion;
- scenario score dashboard;
- score definitions, weights, and calculation note;
- core judgment and score-improvement conditions;
- confidence level and evidence limitations;
- evidence scope and limitations;
- comparison matrix;
- Pros;
- Cons;
- specific actions needed to close each Cons item;
- recommended POC scope and measurable acceptance criteria;
- target industries and named companies, clearly labeled as potential accounts rather than confirmed buyers;
- recommended delivery role for kbro and required partners;
- internal evidence checklist;
- bid/no-bid or proceed/hold recommendation;
- sources and review date.

### 5. Create and verify the Word report

1. Build a professional Traditional Chinese `.docx`.
2. Save it under the configured local competitor-assessment directory.
3. Use a filename that includes kbro, competitor, a short project identifier, assessment type, and version.
4. Never overwrite an existing local report. Increment the version when the same assessment already exists.
5. Use the Documents skill’s strict render-and-verify workflow.
6. Render through LibreOffice to PDF and page PNGs, then inspect every page at full size.
7. Fix numbering continuity, clipped text, split tables, overflow, overlap, broken links, inconsistent headers or footers, and awkward blank pages. Re-render until all pages pass.
8. Reopen the final `.docx` structurally and verify the expected version, baseline name, score anchors, tables, hyperlinks, page-number field, and absence of empty table cells.
9. If the user asks for a draft, preview, or review copy, stop after local verification. Preserve the draft and wait for explicit upload approval.

### 6. Archive to Google Drive

Use the connected Google Drive plugin for all Drive operations.

1. Upload only when the user explicitly asks for cloud upload or has already given unambiguous upload approval.
2. Start from the approved root URL in `kbro-config.md`.
3. Traverse folders from that root; do not rely on a same-named folder found elsewhere in Drive. If the user supplies a direct destination URL, confirm its observed ID through this traversal before using it.
4. Create missing folders only inside the approved root tree.
5. For a local source, store the competitor source under:
   `competitor materials / <Competitor> / presentations`
6. For a Drive source already inside the approved root tree, reuse its existing file and do not upload a duplicate.
7. For a Drive source outside the approved root tree, preserve the original and archive a copy under `presentations` when the connector supports a safe copy or download-and-upload flow.
8. Store the verified report under:
   `competitor materials / <Competitor> / assessments`
9. If the exact source filename already exists, reuse it and do not create a duplicate.
10. Before uploading, list the destination folder and refuse same-name overwrite. If the report filename exists, increment the local version, rebuild or rename consistently, and re-verify before uploading.
11. Preserve the Word MIME type when uploading; do not convert the report to a native Google Doc.
12. Verify an uploaded report with Drive metadata and destination-folder readback. Require the observed filename, Word MIME type, parent folder ID, and file size to match the local file.
13. Return only observed folder and file links.

Never create a folder in My Drive root or outside the approved kbro root, even if a user casually names another destination. Stop and request explicit reconciliation if instructions conflict with this boundary.

## Completion report

Return:

- feasibility conclusion in one concise paragraph;
- exact kbro baseline filename and version used for the comparison;
- scenario scores with their standard definitions;
- local report path;
- number of pages visually inspected;
- scoring confidence;
- any evidence limitations that materially affect the conclusion;
- Google Drive source folder link;
- Google Drive assessment folder link;
- uploaded report link.

Omit cloud links when upload was not approved or has not occurred. Do not claim upload success until both metadata and destination-folder readback confirm the file.
