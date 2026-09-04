<!-- Repository-wide engineering and Git conventions for coding agents. -->

# Global Codex Guidance

## Engineering Defaults

- Fail first. Do not add silent fallback paths, error-swallowing behavior, or misleading degraded modes. Surface failures clearly so the root cause is visible.
- Do not write backward-compatibility code for features that are still under active development unless explicitly requested.
- Keep file responsibilities single-purpose. Split directories and modules when responsibilities diverge.
- Add useful file header comments that explain the file's role and boundary.
- Do not assume the user already knows exactly what they want. If the goal is unclear, stop and discuss the goal before implementing.
- If the goal is clear but the requested path is not optimal, directly recommend the better approach and explain why.
- When problems appear, trace the root cause. Do not paper over issues with patches that only hide symptoms.
- Every technical decision must be able to answer: "why this way?"
- Communicate only decision-changing information. Cut details that do not affect the decision or next action.

## Git Commit Conventions

- Write commit messages in Chinese.
- Do not push commits to a remote repository unless the user explicitly requests it.
- Use `git merge --no-ff` by default when merging branches.
- Create commits with a HEREDOC-formatted message.
- Structure each commit message as a concise title of no more than 50 characters, followed by a blank line and one or more body paragraphs.
- Append a `Co-Authored-By` trailer matching the current model:
  - Claude: `Co-Authored-By: Claude <noreply@anthropic.com>`
  - Codex: `Co-Authored-By: Codex <noreply@openai.com>`
  - Other models: use the model's official name and the vendor's confirmed `noreply` email in the form `Co-Authored-By: <Model> <noreply@<vendor>>`. If the vendor email cannot be confirmed, omit the trailer instead of guessing.
