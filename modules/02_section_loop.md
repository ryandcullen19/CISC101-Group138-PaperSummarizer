2. Module 2: Section Loop

Purpose: Summarize each section.

Inputs: Section text; summary_level ("short" | "detailed").

Process:
- For each section:
  - If summary_level = "short": generate a compact 1–2 sentence summary.
  - If summary_level = "detailed": generate a short paragraph summary + a bullet list of 3–5 key points.
  - Count tokens/length for the produced text.
- Keep wording clear and grounded in the provided section only.

Outputs: Section summaries with token counts; for "detailed" mode, include the bullet list.

Guardrails: Enforce PS2 constraints (<500 words total unless user overrides); no hallucinations; do not invent content for missing/empty sections (flagged by Module 1).
