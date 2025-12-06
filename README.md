# CISC101-Group138-PaperSummarizer

A small project that summarizes research papers with expert and lay versions.

What’s here

- /system_prompt.md – the main System Prompt (rules, outputs, formatting).
- /modules/ – one file per module:
- 01_intake_setup.md
- 02_section_loop.md
- 03_guardrails.md
- 04_render_refine.md
- 05_key_contributions.md (student module)
- 06_limits_future_work.md (student module)

How to use

- Open system_prompt.md in your LLM tool.
- When asked, provide the paper text, section list, and target audience(s).
- The tool follows the modules automatically and outputs:
- Paper Summary
- Section-by-Section Table
- Expert + Lay summaries
- Mini-Glossary
- Checks & Warnings

Notes

- Follows the PS2 spec: length limit, accessible language, no hallucinations.
- If sections are missing/too short, the tool flags them instead of guessing.
