# kbro company baseline configuration

## Local location

- Project root: `D:\AI application code\kbro`
- Company-output directory: `D:\AI application code\kbro\outputs\company`
- Canonical filename: `kbro_Company_Capability_Experience_Updated_YYYY-MM-DD_v<version>.docx`
- Current canonical versions:
  - `kbro_Company_Capability_Experience_Updated_2026-07-29_v0.1.docx`
  - `kbro_Company_Capability_Experience_Updated_2026-07-30_v0.2.docx`
- Legacy alias pattern: `Company_Capability_Experience_Draft_v<version>.docx`

Do not treat a byte-identical legacy alias as a separate version. Do not delete a legacy file unless the user explicitly approves deletion.

## Google Drive boundary and location

- Approved kbro root:
  `https://drive.google.com/drive/folders/1-e47r0JOuCXgFVzeKHBrxU6OvqFCMBXS`
- Approved root ID: `1-e47r0JOuCXgFVzeKHBrxU6OvqFCMBXS`
- Company-materials folder ID: `1Pu2zFC44jWlbZQ1Lf5DleQhNIoihS0iO`
- Company-output folder name: `outcomes`
- Company-output folder:
  `https://drive.google.com/drive/folders/1gYra9axeTlHuOeM5Bx1pfo4o6n039IYN`
- Company-output folder ID: `1gYra9axeTlHuOeM5Bx1pfo4o6n039IYN`

The verified ancestry is:

```text
kbro approved root
└── company materials
    └── outcomes
```

Never create or use another same-named folder outside this tree.

## Latest-baseline rule

1. Match canonical filenames and parse `<version>` as a semantic version.
2. Choose the highest semantic version. Use `YYYY-MM-DD` only to order files with the same version.
3. Require that the chosen canonical filename exists in both Local and Cloud.
4. Require content equality. Use filename and size as an initial check; download and hash when equality is uncertain.
5. If Local and Cloud differ, stop and request a sync decision. Never choose only by modified time.
6. Treat identical legacy aliases as non-canonical duplicates and ignore them for ordering.
7. Never hard-code the current version in an assessment skill or report.

## New-version rule

- Increment the minor version for an ordinary approved evidence update: `v0.2` -> `v0.3`.
- Use a major-version change only when the user explicitly approves a formal-baseline transition or material restructuring.
- Use the actual document update date in the filename.
- Never overwrite, replace, or silently revise an existing version.
- Put the version-update summary near the top of the document.

## Synchronization gate

A version is synchronized only when:

- Local and Cloud contain the same canonical filename;
- byte sizes match;
- content hashes match when both byte streams are available;
- both sides retain earlier canonical versions;
- Cloud readback confirms the observed file ID and parent folder.

If these checks do not pass, report the exact mismatch and do not call the baseline synchronized.
