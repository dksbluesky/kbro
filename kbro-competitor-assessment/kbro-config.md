# kbro assessment configuration

## Local project

- Project root: `D:\AI application code\kbro`
- Capability baseline directory: `D:\AI application code\kbro\outputs\company`
- Canonical baseline pattern: `kbro_Company_Capability_Experience_Updated_YYYY-MM-DD_v<version>.docx`
- Legacy alias pattern: `Company_Capability_Experience_Draft_v<version>.docx`
- Competitor report root: `D:\AI application code\kbro\outputs\competitor_assessments`
- Report directory: `<report root>\<Competitor>`
- Preferred filename: `kbro_<Competitor>_<ProjectSlug>_Feasibility_Assessment_v<version>.docx`

Keep generated reports separate from company capability models and tender assessments.

## Company baseline Cloud location

- Company-materials folder ID: `1Pu2zFC44jWlbZQ1Lf5DleQhNIoihS0iO`
- Company-output folder name: `outcomes`
- Company-output folder URL: `https://drive.google.com/drive/folders/1gYra9axeTlHuOeM5Bx1pfo4o6n039IYN`
- Company-output folder ID: `1gYra9axeTlHuOeM5Bx1pfo4o6n039IYN`
- Verified ancestry: approved root -> `company materials` -> `outcomes`

## Latest capability-baseline rule

1. List canonical candidates in both the Local baseline directory and Cloud company-output folder.
2. Parse semantic versions and select the highest version. Use the filename date only as a tie-breaker for the same version.
3. Require the selected canonical filename to exist on both sides.
4. Require content equality. Use filename and size as an initial check; download and hash when equality is uncertain.
5. Treat a byte-identical legacy alias as a non-canonical duplicate and ignore it for ordering.
6. If Local and Cloud differ, stop and request a sync decision. Never choose by modified time alone.
7. Record the exact baseline filename, version, Local path, and Cloud file ID in the assessment report and completion message.
8. Never hard-code a baseline version. Every new competitor or tender comparison must resolve the synchronized latest version at run time.

## Approved Google Drive boundary

- Approved root URL: `https://drive.google.com/drive/folders/1-e47r0JOuCXgFVzeKHBrxU6OvqFCMBXS`
- Approved root folder ID: `1-e47r0JOuCXgFVzeKHBrxU6OvqFCMBXS`
- All folders created by this skill must be the approved root or descendants of it.
- Never create a kbro folder in My Drive root or outside this tree.

## Drive layout

Use:

```text
approved root
└── competitor materials
    └── <Competitor>
        ├── presentations
        └── assessments
```

Archive source presentations or documents in `presentations`. Upload verified Word assessment reports to `assessments`.

## Version and duplicate policy

- Never overwrite a local or Drive report.
- Treat a new project for the same competitor as a distinct report by using `ProjectSlug`.
- For a revised assessment of the same project, increment the version.
- If an identical source filename is already present in `presentations`, reuse the existing Drive file unless the user explicitly asks to upload a revised source version.
