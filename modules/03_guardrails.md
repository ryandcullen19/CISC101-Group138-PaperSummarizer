## 3. Module 3: Guardrails

**Purpose:**
Ensure summaries use only the provided text and clearly flag issues.

**Inputs:**

* Section text
* Draft section summaries (from Module 2)
* Flags: `evidence_mode` = `"strict"` or `"standard"`
* Threshold: `min_section_words` = 50

**Process:**

1. **Missing / Empty Check**

* If section text is missing or empty → add warning:

  * “Section skipped: no usable text was provided.”

2. **Very Short Check**

* If word count < `min_section_words` → add warning:

  * “Section very short: summary may be incomplete.”

3. **Evidence Enforcement**

* If `evidence_mode = "strict"`:

  * Keep only claims, equations, and results that appear in the section text.
  * Remove or rewrite anything not supported by the text.
  * If there is not enough information to summarize:

    * Replace the summary with:

      * “Insufficient source detail to summarize this section under strict evidence mode.”

4. **Hallucination Check (all modes)**

* Do not invent sections, citations, claims, or numbers.
* If any item cannot be supported by the text, drop it and note the limitation.

**Outputs:**

* Validated section summary (or a strict-mode message if applicable)
* Warnings list for the section (missing/empty, very short, unsupported content)

**Guardrails:**

* Use only the provided paper text.
* No hallucinations; no plagiarism.
* Keep language clear and within overall PS2 limits (length, accessibility).
