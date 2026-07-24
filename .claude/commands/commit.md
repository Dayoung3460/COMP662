Analyse all current git changes and create multiple focused commits by grouping related changes together.

This repository is coursework for COMP662 (Generative AI), not a software product — commits track tutorial notebook progress, dataset changes, and course documentation rather than app features.

## Steps

1. Run `git status` and `git diff` to identify all unstaged and staged changes
2. Analyse the changes and group them by logical concern (e.g. tutorial work, data changes, documentation updates, environment/config)
3. Before staging, check for generated artifacts that shouldn't be committed — model checkpoints (`*.pth`, `*.pt`), notebook checkpoint folders (`.ipynb_checkpoints/`). If present and untracked, ask the user whether to add them to `.gitignore` rather than committing them.
4. For each group, stage only the relevant files using `git add <files>`
5. Write a commit message following the template below, then commit
6. Repeat for each group until all changes are committed

## Commit Message Template

```
<type>: <subject>
```

Where `<type>` is one of:
- `tut` — tutorial notebook work (new exercises, solved cells, analysis, plots)
- `fix` — correcting a bug or error in notebook code (wrong data path, dtype mismatch, out-of-order cell fix, etc.)
- `data` — adding or updating dataset files under `tut/weekN/data/`
- `docs` — documentation changes (CLAUDE.md, TODO.md, course notes)
- `chore` — environment/dependency/config/maintenance tasks (`.venv`, `.idea`, `.claude` settings)

## Commit Message Rules

- Use clear, plain English
- Use imperative mood (e.g., "Add early stopping to tutorial 1 training loop")
- Start subject with uppercase
- No trailing period
- Keep subject within 72 characters
- Do NOT group unrelated changes into one commit just to reduce the number of commits
- Never commit model checkpoint files (`*.pth`, `*.pt`) or notebook checkpoint folders — flag them for `.gitignore` instead

## Example

If there are changes to tutorial 1 (early stopping added), a new dataset file, and a CLAUDE.md update, create three separate commits:
- `tut: add early stopping to tutorial 1 training loop`
- `data: add Weather_Data.csv for tutorial 1 regression task`
- `docs: update CLAUDE.md with tutorial 2 structure`
