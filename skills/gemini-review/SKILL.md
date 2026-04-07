---
name: gemini-review
description: Uses Gemini to review code, pull requests, documents, or architecture plans. Use this skill when the user requests a review of their work utilizing Gemini's capabilities.
---

# Gemini Review

Review the current code, design documents, or specific files using Gemini.

**Input:** `$ARGUMENTS` — file paths or description of what needs to be reviewed.

## When to use this skill

- User says "do a gemini review", "review this using gemini", or "have gemini check this"
- When needing a holistic review of a codebase or specific architecture changes
- When validating complex logic or security implementations

## Steps

1. **Identify the scope:** Determine exactly which files or changes the user wants reviewed. If not specified, ask for clarification or use the currently modified files.
2. **Gather context:** Read the necessary files, recent changes (git diff), and relevant documentation.
3. **Formulate the review prompt:** Prepare a clear prompt for Gemini that includes:
   - The objective (e.g., find bugs, check for best practices, optimize performance, security audit)
   - The relevant code or context
   - Specific areas of concern from the user
4. **Execute the review:**
   - Call the `ask_gemini` MCP tool with `model="gemini-3.1-pro-preview"` and the formulated review prompt and context. Include all relevant code, diffs, and specific review criteria in the prompt.
5. **Present findings:** Summarize Gemini's review findings clearly for the user. Highlight critical issues, suggest improvements, and provide code snippets for recommended changes. Be concise and actionable.
