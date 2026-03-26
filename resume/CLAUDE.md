# Resume Tailoring Instructions

## Meta Resume
The canonical base resume is `meta_resume.tex`. Always use this file as the source when tailoring for a job.

## When a Job Description is Uploaded

When the user provides a job description (pasted text, file, or URL content), do the following **automatically without asking**:

1. **Parse the job description** — extract:
   - Company name
   - Job title
   - Key skills, tools, and technologies mentioned
   - Action verbs and domain-specific language used
   - Any emphasized qualifications or responsibilities

2. **Tailor the resume** — modify a copy of `meta_resume.tex` by:
   - Weaving keywords and phrases from the JD into existing bullet points naturally (do not fabricate experience)
   - Prioritizing and reordering bullets within each role to front-load the most relevant ones
   - Adjusting technical terminology to match the JD's language (e.g., "NLP pipeline" vs. "text processing system")
   - Tweaking the Skills section if needed to surface tools explicitly mentioned in the JD

3. **Save the file** — use the naming convention:
   ```
   {Company}_{JobTitle}.tex
   ```
   - Use snake_case, no spaces, no special characters
   - Example: `Goldman_Sachs_Data_Analyst.tex`, `Microsoft_Quant_Researcher.tex`

4. **Report back** — briefly summarize:
   - Which keywords were added and where
   - Any bullets that were reordered or rewritten
   - Anything in the JD that could not be matched to existing experience

## Constraints
- Never invent experience or skills not present in `meta_resume.tex`
- Keep all dates, institutions, and titles accurate
- Preserve the LaTeX structure and formatting exactly

keep the new resume for this position to 。/resumes foloder