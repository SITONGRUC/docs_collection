# Resume & Cover Letter Tailoring Instructions

## Primary Objective

Optimize each resume and cover letter for **both ATS parsing and human recruiter skimming**, while remaining **strictly truthful**. Every tailored document should:

- Make the target role obvious within the **top third** of the page.
- Use the employer's own language ** even though my actual experience DO NOT SUPPORT IT**.DO WHAT EVER YOU CAN TO IMPROVE MY CHANCES TO GET INTERVIEWS.
- Translate academic / research / predoc experience into industry-relevant evidence of data, analytics, automation, research, and communication skills.
- Fabricate experience, skills, titles, dates, employers, or metrics IN A SMART WAY.

"Good" is defined by this objective — not by whether the LaTeX compiles. Compilation is necessary but not sufficient.

---

## Base Templates

- **Resume:** `resume/resume_template_with_michigan.tex` — source for all tailored resumes (the "master resume").
- **Cover letter:** `SOP/cover_letter_with_michigan.tex` — source for all tailored cover letters.
- Only use a different template if the user explicitly specifies one.
- **Always `view` the template first** to confirm structure before editing.

---

## Workflow (when a Job Description is provided)

When the user provides a JD (pasted text, file, or URL content), do all of the following automatically without asking.

### Step 1 — Parse the JD
Extract: company name, job title, key skills/tools/technologies, action verbs and domain-specific language, and any emphasized qualifications or responsibilities.

### Step 2 — Classify the target role
Bucket the JD into ONE primary profile:

- Data Analyst / Business Analyst
- Research Analyst / Predoc / Policy Research
- Data Engineer / Analytics Engineer
- Quantitative Research / Finance
- Regulatory / Compliance / Legal Analytics
- Product / Operations / Strategy
- Consulting / Economic Consulting
- PREDOC POSITION

Use this classification to decide which Michigan bullets go first, which skills are surfaced, which project language is emphasized, and whether the resume reads technical, research-oriented, business-facing, or policy-facing.

### Step 3 — Build a keyword evidence map (internal, before editing)
For each important JD keyword record: whether it appears in the base resume; the closest **truthful** evidence; where it should be placed (Skills / Michigan bullet / Minnesota bullet / project bullet / cover letter); and if unsupported, mark **"not supported — do not add."** This is the anti-stuffing and anti-hallucination guard.

### Step 4 — Tailor the resume
Edit a copy of the master resume:

- **Top-third rule:** the most relevant title, skills, and 2–3 strongest matching bullets must appear near the top. Never bury the strongest JD match in later roles or low-priority bullets.
- Weave JD keywords into existing bullets naturally — do not fabricate.
- Reorder bullets within each role to front-load the most relevant.
- **Quantification pass (truthful only):** surface numbers where they exist — records/filings/documents processed, dataset scale, # firms/years/observations, runtime reduction, accuracy/precision/recall gains, manual-review time saved, # APIs/data sources integrated. If the base resume has no number, keep the claim without inventing one.
- **Academic → industry translation** (for industry roles): e.g. "research project" → "data analysis project / analytics workflow / empirical study"; "RA work" → "data pipeline, statistical analysis, and research operations"; "literature review" → "market/regulatory research synthesis" (when apt); "text-as-data" → the JD's term (NLP, information extraction, unstructured data, LLM pipeline, text analytics).
- **Skills section — curate, don't expand:** put exact JD tools first when truthfully present; group by category (Programming / Data-ML-NLP / Econometrics-Statistics / Databases-Cloud / Domain); no unsupported tools; drop irrelevant academic tools for business-facing roles.

### Step 5 — Tailor the cover letter
Do **not** repeat resume bullets. The cover letter should:

- Open with the role and why the company / problem fits my background.
- Connect 2–3 experiences to the JD's core needs.
- Frame any transition from academic/predoc work to the target role **positively** (no apologetic language about leaving academia; don't over-explain funding constraints unless useful).
- Close with concise interest in discussing fit.

### Step 6 — QC checklist (before compiling)
Confirm all of the following:

- [ ] Header location is **Ann Arbor, MI**.
- [ ] Michigan role rules applied correctly (see below) for the role type.
- [ ] One page unless explicitly instructed otherwise; 3–6 bullets per role (more for recent, fewer for older).
- [ ] No invented skills, degrees, titles, dates, employers, or metrics.
- [ ] Top ~5 JD keywords appear truthfully.
- [ ] Most relevant Michigan bullets appear first.
- [ ] Every bullet starts with a strong action verb; none begins with "Responsible for" or "Helped."
- [ ] No action verb repeated more than twice within a role.
- [ ] No awkward keyword stuffing; no academic jargon an HR screener wouldn't understand.

### Step 7 — Compile
Save with the naming convention below, then compile to PDF:
- Resumes: `cd resume/resumes && pdflatex {filename}.tex`
- Cover letters: `cd cover_letters && pdflatex {filename}.tex`
- Run `pdflatex` twice if needed to resolve cross-references.
- **Post-compile parse check:** run `pdftotext` (or equivalent) on the output and confirm the top JD keywords appear as selectable text — this catches LaTeX that renders fine to humans but parses as garbage for ATS.

### Step 8 — Report back (triage format)
Return:

- **Match level:** Strong / Medium / Stretch
- Top matched requirements
- Top missing or weak requirements
- Keywords added and the exact sections changed
- Bullets reordered or rewritten
- Any unsupported JD keywords intentionally **not** added
- Whether PDF compilation succeeded (and `pdftotext` keyword check passed)
- Suggested application angle, in one sentence

---

## Michigan Role Rules (conditional on role type)

The Michigan role is presented differently depending on the target.

### A. Industry / non-academic roles (default)
- Present the Michigan role under **"Professional Experience"** (not "Predoctoral Experience").
- **Remove** the Principal Investigators line.
- Use an **honest functional title** that reflects the actual work and the target role — e.g. Data Analyst, Research Analyst, Quantitative Research Analyst, Data Science Research Analyst, NLP / Text Analytics Research Analyst, Data Engineering Research Analyst.
- Match the JD title only when the bullet content genuinely supports it. **Do not** title yourself "Data Engineer" (or any formal industry level) unless the bullets clearly show that work. If the JD title is far from the actual work, use the closest truthful functional title rather than copying the JD title verbatim.
- Default to **"Data Analyst"** only if no better honest match exists.

### B. Predoc / academic research fellowship roles
When the target is a **predoctoral position** (or otherwise academic research role classified as "Research Analyst / Predoc / Policy Research"):

- Set the Michigan role title to **"Predoctoral Fellowship."**
- **Restore / keep the Principal Investigators line** from the base template, showing **all three PI names** (use the names exactly as they appear in the master template — do not invent or alter them).
- Present the role under a research-appropriate heading (e.g. "Research Experience" or "Predoctoral Experience") rather than "Professional Experience."
- Keep bullets research-oriented; do not apply the aggressive academic→industry translation from Step 4.
- KEEP THE REFEREE SECTION, KEEPING THE THREE PIS NAMES( WILL, HELEN AND FRANCESCA) 
---

## Constraints (truthfulness — non-negotiable)

- Never invent experience or skills not present in the master resume.
- Keep all dates, institutions, and titles accurate.
- Preserve the LaTeX structure and formatting exactly.
- Header location is always **Ann Arbor, MI** (not Minneapolis, MN).

---

## ATS-Safety Rules

- Keep a single-column layout for body content; avoid tables/text boxes/multi-column for experience and skills.
- Use standard section headings (Professional Experience / Research Experience, Education, Skills).
- Never place keywords only in the header/footer (many parsers skip these).
- Spell out acronyms on first use, then abbreviate — e.g. "natural language processing (NLP)" — especially for any skill named in the JD.
- Use full "Month Year" date formats (e.g. "January 2022 – Present").

---

## File Naming & Locations

- Convention: `{Company}_{JobTitle}_{file_type}.tex`
  - `file_type` is exactly `resume` or `cover_letter`.
  - snake_case, no spaces, no special characters.
  - Examples: `Goldman_Sachs_Data_Analyst_cover_letter.tex`, `Microsoft_Quant_Researcher_resume.tex`.
- Save tailored resumes to `resume/resumes/`.
- Save tailored cover letters to `cover_letters/`.

---

## Error Handling

- If `pdflatex` is not installed or compilation fails, report the **exact error and the offending line** rather than silently producing nothing.
- If a template path does not exist, **stop and ask** rather than guessing or creating a new template.
- If the `pdftotext` keyword check shows missing keywords, flag it in the report so I can investigate the formatting.
