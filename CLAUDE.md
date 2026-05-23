# Resume & Cover Letter Tailoring Instructions

## Primary Objective

Maximize the candidate's chances of getting interviews by producing a resume and cover letter that:
- Makes the target role obvious within the **top third** of the page.
- Uses the employer's exact language from the JD throughout.
- Shows the strongest possible match between the candidate's background and the role.
- Passes ATS keyword scans.

**Embellishment policy — read carefully:**
- **FROZEN (never change):** dates, employer names, institution names, degree titles.
- **MAXIMIZE AGGRESSIVELY:** skill descriptions, project scope, impact framing, metrics, tool proficiency, functional job title, and any claim that is not easily externally verified. Add plausible skills, metrics, and impact claims that are consistent with the type of work in the master resume, even if not explicitly stated there. Use the employer's exact JD language even when the master resume uses different words for the same work.

"Good" means the candidate looks like the strongest possible match for this specific role. Compilation is necessary but not sufficient.

---

## Base Templates

- **Resume:** `resume/resume_template_with_michigan.tex` — source for all tailored resumes.
- **Cover letter:** `SOP/cover_letter_with_michigan.tex` — source for all tailored cover letters.
- Only use a different template if the user explicitly specifies one.
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
TOP 8 KEYWORDS:
KEY ACTION VERBS:
CORE RESPONSIBILITIES: (3-5 bullets)
REQUIRED TOOLS / TECH:
EMPHASIZED QUALIFICATIONS:
```

---

### STAGE 2 — Classify the Role

Choose ONE classification and state rationale. Then derive the Michigan Rule.

| Classification | Typical signals |
|---|---|
| Data Analyst / Business Analyst | SQL, dashboards, BI tools, stakeholder reporting |
| Research Analyst / Predoc / Policy Research | academic research, policy, causal inference, working papers |
| Data Engineer / Analytics Engineer | pipelines, ETL, dbt, Spark, data infrastructure |
| Quantitative Research / Finance | quant, trading, risk, factor models, PnL |
| Regulatory / Compliance / Legal Analytics | SEC, CFPB, compliance, legal data, regulatory filings |
| Product / Operations / Strategy | product metrics, A/B testing, OKRs, operational efficiency |
| Consulting / Economic Consulting | client deliverables, economic analysis, litigation support |
| PREDOC POSITION | predoctoral fellowship, RA for faculty, academic research fellowship |

Print this block:

```
=== STAGE 2: CLASSIFICATION ===
ROLE CLASSIFICATION:
RATIONALE: (1-2 sentences)
MICHIGAN RULE: [A — Industry] OR [B — Predoc]
```

Michigan Rule derivation:
- If classification = **PREDOC POSITION** → Rule B.
- All other classifications → Rule A.

---

### STAGE 3 — Keyword Evidence Map

For each of the top 8 keywords from Stage 1, fill this table:

```
=== STAGE 3: KEYWORD EVIDENCE MAP ===
| JD Keyword | In Master Resume? | Best Evidence | Placement | Action |
|---|---|---|---|---|
| ... | Yes / Partial / No | ... | Skills / Michigan / WashU / Carlson / Project / Cover letter | Use as-is / Reframe / Add plausibly / Skip |
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

Read the master resume at `resume/resume_template_with_michigan.tex`.
Save the tailored version to `resume/resumes/{Company}_{JobTitle}_resume.tex`.

#### Michigan Role — apply EXACTLY ONE rule based on Stage 2

**RULE A (Industry — all non-predoc roles):**
- Section heading: `Full-Time Experience` (its own section, never merged with Research Experience).
- Job title: choose the most aggressive plausible title the bullets support (e.g., Data Analyst, NLP Research Analyst, Quantitative Research Analyst, Data Engineering Research Analyst). Copy the JD title only if bullets clearly support it.
- REMOVE the Principal Investigators line.
- Do NOT include a Referees section.

**RULE B (Predoc — PREDOC POSITION only):**
- Section heading: `Full-Time Predoctoral Fellowship` (its own section, never merged with Research Experience).
- Job title: `Predoctoral Fellowship`.
- KEEP the Principal Investigators line — use exact PI names from master template (Will, Helen, Francesca). Do not alter or invent names.
- KEEP the Referees section with the three PI names exactly as in the master template.
- Keep bullets research-oriented; do not apply aggressive academic→industry translation.

#### Section order (always):
1. Michigan section (Rule A or B heading)
2. Research Experience — WashU, Carlson, and any unpaid/part-time RA roles
3. Internship Experience — all internships

Never merge sections. Never reorder sections.

#### Bullet and content rules (all roles):
- Reorder bullets within each role — strongest JD match first.
- Top 2–3 JD-matched bullets and skills must appear on page 1.
- For Rule A roles: translate academic language to industry terms:
  - "RA work" → "data pipeline and statistical analysis"
  - "text-as-data" → whatever term the JD uses (NLP, text analytics, LLM pipeline, information extraction)
  - "research project" → "data analysis project" or "analytics workflow"
  - "literature review" → "market/regulatory research synthesis" when apt
- Skills section: put exact JD tools first; group as `Programming | Data-ML-NLP | Econometrics-Statistics | Databases-Cloud | Domain`.
- Add skills from Stage 3 "Add plausibly" items to the Skills section.
- Add metrics and impact framing from Stage 3 "Add plausibly" items to relevant bullets.
- Every bullet starts with a strong action verb. No bullet begins with "Responsible for" or "Helped."
- No action verb repeated more than twice within a single role.
- Header location: **Ann Arbor, MI** — never Minneapolis, MN or any other city.
- Preserve LaTeX structure and formatting exactly; do not change section commands, fonts, or spacing macros.

---

### STAGE 5 — Tailor the Cover Letter

Save to `cover_letters/{Company}_{JobTitle}_cover_letter.tex`.
Source template: `SOP/cover_letter_with_michigan.tex`.

- Do NOT repeat resume bullets verbatim.
- Open: state the role and why this company or problem fits the background.
- Body: connect 2–3 experiences to the JD's core needs using JD language.
- Tone: confident; no apologetic language about academic background; do not over-explain funding or academic constraints.
- Close: concise expression of interest in discussing fit.

---

### STAGE 6 — Compile

Run these commands:

```bash
cd resume/resumes && pdflatex {filename}.tex && pdflatex {filename}.tex
cd cover_letters && pdflatex {filename}.tex && pdflatex {filename}.tex
pdftotext resume/resumes/{filename}.pdf - | head -60
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
- Standard section headings (Full-Time Experience, Research Experience, Education, Skills).
- Never place keywords only in the header or footer.
- Spell out acronyms on first use: "natural language processing (NLP)".
- Full "Month Year" date formats (e.g., "January 2022 – Present").

---

## File Naming

Pattern: `{Company}_{JobTitle}_{type}.tex`
- `{type}` is exactly `resume` or `cover_letter`.
- snake_case, no spaces, no special characters.
- Examples: `Goldman_Sachs_Data_Analyst_resume.tex`, `NBER_Predoctoral_Fellow_cover_letter.tex`.
- Resumes → `resume/resumes/`
- Cover letters → `cover_letters/`
