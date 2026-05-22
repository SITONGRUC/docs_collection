# Resume Tailoring Instructions

## Base Templates
- **Resume**: `resume/resume_template_with_michigan.tex` — use this as the source for all tailored resumes
- **Cover letter**: `SOP/cover_letter_with_michigan.tex` — use this as the source for all tailored cover letters
- Only use a different template if the user explicitly specifies one

## When a Job Description is Uploaded

When the user provides a job description (pasted text, file, or URL content), do the following **automatically without asking**:

1. **Parse the job description** — extract:
   - Company name
   - Job title
   - Key skills, tools, and technologies mentioned
   - Action verbs and domain-specific language used
   - Any emphasized qualifications or responsibilities

2. **Tailor the resume** — modify a copy of `resume/resume_template_with_michigan.tex` by:
   - Weaving keywords and phrases from the JD into existing bullet points naturally (do not fabricate experience)
   - Prioritizing and reordering bullets within each role to front-load the most relevant ones
   - Adjusting technical terminology to match the JD's language (e.g., "NLP pipeline" vs. "text processing system")
   - Tweaking the Skills section if needed to surface tools explicitly mentioned in the JD

3. **Save the file** — use the naming convention:
   ```
   {Company}_{JobTitle}_{file_type}.tex
   ```
   - Use snake_case, no spaces, no special characters
   - Example: `Goldman_Sachs_Data_Analyst_cover_letter.tex`, `Microsoft_Quant_Researcher_resume.tex`

4. **Report back** — briefly summarize:
   - Which keywords were added and where
   - Any bullets that were reordered or rewritten
   - Anything in the JD that could not be matched to existing experience

## Constraints
- Never invent experience or skills not present in `resume/resume_template_with_michigan.tex`
- Keep all dates, institutions, and titles accurate
- Preserve the LaTeX structure and formatting exactly
- **Location**: Always use **Ann Arbor, MI** (not Minneapolis, MN) as the header location in every tailored resume
- **Michigan role title**: Always present the Michigan role under "Professional Experience" (not "Predoctoral Experience") and remove the Principal Investigators line. Set the title to match the target job — use the closest fit from the JD (e.g., Data Engineer → "Data Engineer", Business Analyst → "Data Analyst", Program Manager / research role → "Research Analyst"). Default to "Data Analyst" only if no better match exists.

- Save tailored **resumes** to `resume/resumes/`
- Save tailored **cover letters** to `cover_letters/`