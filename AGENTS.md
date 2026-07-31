# Resume & Cover Letter Tailoring Instructions

## Context (read first)

The candidate begins a fully-funded Ph.D. in Accounting at UT Dallas (Naveen Jindal School of Management) in Aug 2026. The goal is **not** an academic professorship — the program's recent placement record is weak (as of April, only 3 of 8 graduates found academic jobs, and only 1 of those landed an R1 role). The candidate is targeting an **industry job after finishing the Ph.D.** and wants to start interning as early and as often as possible along the way.

UT Dallas does not allow first-year Ph.D. students to intern in the USA, so **Year 1 (2026–2027) internship search is focused on China and Hong Kong.** From Year 2 onward, US internships become allowed and the search should widen accordingly — check with the user before assuming location targeting has changed.

There is only **one track now: industry.** The previous predoc/academic-fellowship track (Rule B) is retired — do not classify any role as PREDOC POSITION and do not tailor materials in an academic/research-fellowship style. Every application goes through the industry framing described below.

**Status note:** on 2026-07-31 the prior master resume/cover-letter templates (Michigan-predoc era) were archived to `archive/resume/` and `archive/SOP/`. The repo now keeps only two working folders, `resume/` and `cover_letters/` — everything else (old academic materials, writing sample, job market paper, read list, transcript, code sample) lives in `archive/`. The new master resume lives at `resume/resume_for_work.tex` (rebuilt from `archive/resume/resume_for_work.tex`, updated with Dallas, TX header and the UT Dallas Ph.D. added to Education) and the new cover letter template lives at `cover_letters/cover_letter_template.tex` (placeholders only — no reusable body content carries over from the old Michigan-era letter). The pipeline is ready to run: JD in → tailored resume + cover letter out.

---

## Primary Objective

Maximize the candidate's chances of getting interviews by producing a resume and cover letter that:
- Makes the target role obvious within the **top third** of the page.
- Uses the employer's exact language from the JD throughout.
- Shows the strongest possible match between the candidate's background and the role.
- Passes ATS keyword scans.

**Embellishment policy — read carefully:**
- **FROZEN (never change):** dates, employer names, institution names, degree titles.
- **MAXIMIZE AGGRESSIVELY:** skill descriptions, project scope, impact framing, metrics, tool proficiency, and any claim that is not easily externally verified. Add plausible skills, metrics, and impact claims consistent with the type of work in the master resume, even if not explicitly stated there.
- Translate academic/research language into industry language and aggressively reframe the functional job title using JD terminology.

"Good" means the candidate looks like the strongest possible match for this specific role. Compilation is necessary but not sufficient.

---

## Base Templates

- **Resume:** `resume/resume_for_work.tex` — the single master template for all roles. (Prior master: `archive/resume/meta_resume.tex` / `archive/resume/resume_for_work.tex` — useful as source material while rebuilding.)
- **Cover letter:** `cover_letters/cover_letter_template.tex`. (Prior template: `archive/SOP/cover_letter_with_michigan.tex`.)
- Always `Read` the template first to confirm structure before editing.
- **NEVER modify the template files directly.** Always create a new file for each position using the file naming convention below, and write the tailored content there. The templates are read-only master sources.
- Save new resume files to `resume/resumes/`.
- Save new cover letter files to `cover_letters/`.

---

## MANDATORY WORKFLOW — ALWAYS FOLLOW STAGES IN ORDER

> **RULE: Do not write or edit any .tex file until Stages 1, 2, and 3 have been fully printed in your response. This is non-negotiable.**

---

### STAGE 1 — Parse the JD

Print this block immediately after receiving a JD, before anything else:

```
=== STAGE 1: JD PARSE ===
COMPANY:
JD TITLE:
LOCATION: (flag if outside China/Hong Kong for a Year-1 internship search)
TOP 8 KEYWORDS:
KEY ACTION VERBS:
CORE RESPONSIBILITIES: (3-5 bullets)
REQUIRED TOOLS / TECH:
EMPHASIZED QUALIFICATIONS:
```

---

### STAGE 2 — Classify the Role

Choose ONE classification and state rationale.

| Classification | Typical signals |
|---|---|
| Data Analyst / Business Analyst | SQL, dashboards, BI tools, stakeholder reporting |
| Research Analyst / Policy Research | academic research, policy, causal inference, working papers |
| Data Engineer / Analytics Engineer | pipelines, ETL, dbt, Spark, data infrastructure |
| Quantitative Research / Finance | quant, trading, risk, factor models, PnL |
| Regulatory / Compliance / Legal Analytics | SEC, CFPB, compliance, legal data, regulatory filings |
| Product / Operations / Strategy | product metrics, A/B testing, OKRs, operational efficiency |
| Consulting / Economic Consulting | client deliverables, economic analysis, litigation support |

Print this block:

```
=== STAGE 2: CLASSIFICATION ===
ROLE CLASSIFICATION:
RATIONALE: (1-2 sentences)
```

---

### VISA / WORK AUTHORIZATION GATE (check BEFORE Stage 3)

After Stage 2 classification, scan the JD for language indicating the employer will **not** sponsor visas or will **not** consider candidates without existing work authorization. Common phrases:

- "unable to provide visa sponsorship"
- "no visa sponsorship available"
- "must be authorized to work in the United States"
- "no work permit sponsorship"
- "will not sponsor employment visas"
- "must have permanent work authorization"

**If the JD contains such language:**
- **STOP immediately.** Do NOT proceed to Stage 3.
- Tell the user: "This JD states they will not consider candidates without work authorization / will not sponsor visas. I'm not generating materials for this position."
- Do NOT generate any .tex files, do NOT run compilation.
- Exception: if the role is physically based in China or Hong Kong, US work-authorization boilerplate is often irrelevant — confirm with the user before treating it as a blocker.

---

### STAGE 3 — Keyword Evidence Map

For each of the top 8 keywords from Stage 1, fill this table against `resume/resume_for_work.tex`:

```
=== STAGE 3: KEYWORD EVIDENCE MAP ===
| JD Keyword | In Master Resume? | Best Evidence | Placement | Action |
|---|---|---|---|---|
| ... | Yes / Partial / No | ... | Skills / Full-Time Experience / Project / Research Assistant / Cover letter | Use as-is / Reframe / Add plausibly / Skip |
```

**Action definitions:**
- **Use as-is** — keyword already present in matching context.
- **Reframe** — the evidence exists but uses different words; translate to JD language.
- **Add plausibly** — keyword is not in master resume, but adding it is consistent with the work context; add it to the resume.
- **Skip** — no plausible connection; do not force it.

---

> **=== STOP: DO NOT WRITE ANY LaTeX UNTIL STAGES 1, 2, AND 3 ARE PRINTED ABOVE ===**

---

### STAGE 4 — Tailor the Resume

Read the master resume: `resume/resume_for_work.tex`.
Save the tailored version to `resume/resumes/{Company}_{JobTitle}_resume.tex`.

**Rules:**
- Section heading: `Full-Time Experience` (its own section, never merged with Research Assistant Experience).
- Job title: choose the most aggressive plausible title the bullets support (e.g., Data Analyst, NLP Research Analyst, Quantitative Research Analyst, Data Engineering Research Analyst). Copy the JD title only if bullets clearly support it.
- No Principal Investigators line, no References/Referees section.

#### Section order:
1. Education
2. Full-Time Experience
3. Project \& Internship Experience — analytics/research lab projects + all internships
4. Research Assistant Experience — strongest bullets only
5. Skills

Never merge sections. Never reorder sections.

#### Bullet and content rules:
- Reorder bullets within each role — strongest JD match first.
- Top 2–3 JD-matched bullets and skills must appear on page 1.
- Translate academic language to industry terms:
  - "RA work" → "data pipeline and statistical analysis"
  - "text-as-data" → whatever term the JD uses (NLP, text analytics, LLM pipeline, information extraction)
  - "research project" → "data analysis project" or "analytics workflow"
  - "literature review" → "market/regulatory research synthesis" when apt
- Skills section: put exact JD tools first; group as `Programming | Data-ML-NLP | Econometrics-Statistics | Databases-Cloud | Domain`.
- Add skills from Stage 3 "Add plausibly" items to the Skills section.
- Add metrics and impact framing from Stage 3 "Add plausibly" items to relevant bullets.
- Every bullet starts with a strong action verb. No bullet begins with "Responsible for" or "Helped."
- No action verb repeated more than twice within a single role.
- Header location: confirm current city with the user if unsure (candidate is transitioning from Ann Arbor, MI to UT Dallas, TX as of Aug 2026) — never leave a stale city on the resume.
- Preserve LaTeX structure and formatting exactly; do not change section commands, fonts, or spacing macros.

---

### STAGE 5 — Tailor the Cover Letter

Save to `cover_letters/{Company}_{JobTitle}_cover_letter.tex`.
Source template: `cover_letters/cover_letter_template.tex`.

**Replace all hardcoded content from the template — nothing carries over as-is:**
- **Date:** update to today's date in "Month DD, YYYY" format.
- **Salutation:** replace with the correct hiring contact or committee for this role.
- **Full body:** rewrite entirely for this JD.
- **Header city:** confirm current city with the user if unsure — never leave a stale city on the letter.

**Content rules:**
- Do NOT repeat resume bullets verbatim.
- Open: state the role and why this company or problem fits the background.
- Body: connect 2–3 experiences to the JD's core needs using JD language.
- Tone: confident; no apologetic language about academic background; do not over-explain funding or academic constraints.
- Close: concise expression of interest in discussing fit.

---

### STAGE 6 — Compile

Run these commands:

```bash
mkdir -p resume/resumes cover_letters
cd resume/resumes && pdflatex {filename}.tex && pdflatex {filename}.tex
cd ../../cover_letters && pdflatex {filename}.tex && pdflatex {filename}.tex
pdftotext ../resume/resumes/{filename}.pdf - | head -60
```

- Run `pdflatex` twice to resolve cross-references.
- If compilation fails: report the exact error message and the offending line. Do not silently produce nothing.
- If a template path does not exist: STOP and ask — do not guess or create a new template.

---

### STAGE 7 — Report

Print this triage summary:

```
=== STAGE 7: TRIAGE REPORT ===
MATCH LEVEL: Strong / Medium / Stretch
TOP MATCHED REQUIREMENTS:
TOP GAPS:
KEYWORDS ADDED (keyword → section):
BULLETS REWRITTEN OR REORDERED:
EMBELLISHMENTS ADDED (what was added and where):
COMPILATION: Success / Failed ([exact error if failed])
ATS PARSE CHECK (top keywords found in pdftotext output?):
APPLICATION ANGLE: (one sentence)
```

---

## ATS Safety Rules

- Single-column layout for body content — no tables, text boxes, or multi-column blocks in experience or skills.
- Standard section headings: `Full-Time Experience`, `Project \& Internship Experience`, `Research Assistant Experience`, `Education`, `Skills`. All ATS-safe.
- Never place keywords only in the header or footer.
- Spell out acronyms on first use: "natural language processing (NLP)".
- Full "Month Year" date formats (e.g., "January 2022 – Present").

---

## File Naming

Pattern: `{Company}_{JobTitle}_{type}.tex`
- `{type}` is exactly `resume` or `cover_letter`.
- snake_case, no spaces, no special characters.
- Examples: `Goldman_Sachs_Data_Analyst_resume.tex`, `CICC_Quant_Research_Intern_cover_letter.tex`.
- Resumes → `resume/resumes/`
- Cover letters → `cover_letters/`
