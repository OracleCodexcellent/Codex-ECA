# Setting Up Codex for SE Work: Non-Coder Guide

This guide is for Oracle Solutions Engineers, Sales Consultants, and Cloud Enterprise Architects who want Codex to handle repository work without typing Git commands.

You do not need to install Git, GitHub CLI, Node.js, npm, or any developer tool for the workflow in this guide. The only thing you need is access to Codex in an environment that is already connected to the repository and allowed to work with GitHub.

## What You Need

- Codex access through your approved company setup.
- A repository connected to Codex.
- Permission to create branches, commits, pushes, and pull requests for that repository.
- Approval from your team before using customer, confidential, regulated, or personal data.

If Codex can see the repository files and can ask for approval before committing or pushing, you are ready.

## Plain-English Terms

- Repository: the shared folder where the team keeps documentation or code.
- Branch: a draft copy of the repository for your changes.
- Commit: a saved package of changes with a short description.
- Push: upload your saved changes to GitHub.
- Pull request, or PR: a review request before your changes are merged.
- Versioned changes: files the repository is already tracking. This usually excludes local settings, downloads, and editor folders.

You do not have to run commands for any of these. Ask Codex to do the work and explain what it is doing.

## First 10 Minutes

### 1. Open Codex in the Repository

Open Codex in the workspace or repository your team gave you.

Then paste this:

```text
Check this repository and explain the current state in plain English.

Tell me:
- What repository I am in
- What branch I am on
- Whether I have local changes
- Which files changed
- Whether anything looks like local editor settings or temporary files

Do not change files.
Do not commit or push.
```

### 2. Tell Codex How You Work

If the repository does not already have an `AGENTS.md` file, ask Codex to create one:

```text
Create an AGENTS.md file for my Oracle Solutions Engineering workspace.

Write it for Codex so it understands how to help me.

Include:
- I am an Oracle Solutions Engineer / Cloud Enterprise Architect.
- Keep writing clear, factual, and customer-ready.
- Do not invent pricing, benchmarks, roadmap, licensing, certifications, or legal commitments.
- Mark uncertain claims as [VERIFY].
- Do not include customer PII, credentials, secrets, or confidential data in examples.
- Use synthetic data for demos.
- Prefer tables for comparisons.
- Prefer Mermaid diagrams for architecture drafts.
- For customer-facing work, separate facts, assumptions, recommendations, and open questions.
- Do not commit, push, or create a pull request unless I explicitly ask.

Make the file practical and concise.
```

### 3. Make One Small Local Change

Use a real task, but keep it small:

```text
Update this documentation so it is easier for a non-coder Oracle SE to understand.

Use plain language.
Keep the content practical.
Do not use terminal commands.
Do not commit or push.
```

### 4. Review Before Publishing

Ask Codex to summarize the changes before anything goes to GitHub:

```text
Review my local changes in plain English.

Tell me:
- Which files changed
- What changed in each file
- Whether any new files are untracked
- Whether any local editor or temporary files should be excluded
- Whether the change is safe to commit

Do not change files.
Do not commit or push.
```

## Publishing Changes with Codex

Use these prompts instead of typing Git commands.

### Commit and Push Only Existing Versioned Files

Use this when you changed files that were already part of the repository and you want to avoid adding local files by accident.

```text
Commit and push only versioned changes.

Before committing:
- Show me the files that will be included.
- Exclude untracked files.
- Exclude local editor settings, IDE folders, downloads, and temporary files.
- Use a clear documentation commit message.

After committing:
- Push this branch to GitHub.
- Create a pull request against main.
- Write a detailed PR description with:
  - Summary
  - What changed
  - Why it changed
  - Review notes
  - Testing or validation performed

Do not include any untracked files unless I explicitly name them.
```

### Commit and Push a New Named File

Use this when Codex created a new file that you do want included.

```text
Commit and push these specific files only:
- <file name 1>
- <file name 2>

Before committing:
- Confirm the exact files that will be included.
- Exclude everything else.
- Do not include editor settings, IDE folders, temporary files, credentials, or customer data.

After committing:
- Push this branch to GitHub.
- Create a pull request against main.
- Write a detailed PR description with summary, changed files, reviewer notes, and validation.
```

### Create a Branch for New Work

If you are starting a new documentation update, ask Codex:

```text
Create a new branch for this documentation update.

Use a short branch name that describes the work.
Then tell me the branch name in plain English.

Do not commit or push yet.
```

### Update an Existing PR

Use this after reviewers leave comments:

```text
Read the pull request comments for this PR: <paste PR link>

Summarize what reviewers asked for.
Make the requested documentation changes locally.
Show me a plain-English summary of the changes.

Do not commit or push until I approve.
```

When you are ready:

```text
Commit and push the PR feedback changes to the same branch.

Use a clear commit message.
Update the PR description if needed.
Tell me what changed and provide the PR link.
```

### Sync After a PR Is Merged

After the PR is merged, ask Codex:

```text
My pull request was merged.

Update my local workspace so it matches the latest main branch.
Then tell me in plain English whether I am ready to start the next task.
```

## Everyday Prompt Patterns

### Create Customer-Ready Documentation

```text
Create a customer-ready architecture summary from these notes.

Audience: CIO, CTO, enterprise architects, security leader, platform team
Tone: clear, factual, executive-readable

Structure:
- Executive summary
- Current state
- Target state
- Recommended architecture
- Key Oracle services
- Risks and assumptions
- Open questions
- Next steps

Mark anything uncertain as [VERIFY].
Do not invent pricing, benchmarks, or roadmap.
Do not commit or push.
```

### Turn Notes into a Follow-Up Email

```text
Draft a customer follow-up email from these notes.

Make it concise, professional, and specific.
Separate:
- Thank you / context
- Decisions made
- Action items
- Open questions
- Next meeting or next step

Do not invent commitments.
Mark uncertain items as [VERIFY].
Do not commit or push.
```

### Build a Demo or PoC Checklist

```text
Create a PoC checklist for this customer scenario.

Include:
- Goal
- Scope
- Success criteria
- Demo data needed
- Setup tasks
- Validation steps
- Risks
- Rollback or cleanup steps
- Owner and due date columns

Use synthetic data only.
Do not create cloud resources.
Do not commit or push.
```

### Review a Document Before Sharing

```text
Review this document for a customer-facing Oracle SE audience.

Check for:
- Unsupported claims
- Pricing, licensing, benchmark, roadmap, or legal-risk statements
- Confusing language
- Missing assumptions
- Missing next steps
- Anything that should be marked [VERIFY]

Suggest edits in plain English.
Do not commit or push.
```

## Safety Rules

- Ask Codex to make local changes first.
- Ask Codex to review the changed files before publishing.
- Ask Codex to exclude editor settings and temporary files.
- Use PRs for shared repositories.
- Do not publish credentials, tokens, secret keys, customer confidential data, or customer PII.
- Validate pricing, sizing, performance, licensing, roadmap, security, and legal claims with approved sources.
- If you do not understand what Codex is about to publish, ask it to explain in plain English before approving.

## Best One-Line Prompts

```text
Explain the repository state in plain English. Do not change anything.
```

```text
Make the documentation easier for non-coders. Do not use terminal commands. Do not commit or push.
```

```text
Review my local changes and tell me what would be committed. Do not commit or push.
```

```text
Commit and push only versioned changes, create a pull request, and write a detailed PR description.
```

```text
Read the PR comments, make the requested changes locally, and wait for my approval before publishing.
```

## Useful Official Codex References

- Codex quickstart: https://developers.openai.com/codex/quickstart
- Codex use cases: https://developers.openai.com/codex/use-cases
- Codex best practices: https://developers.openai.com/codex/learn/best-practices
- Custom instructions with `AGENTS.md`: https://developers.openai.com/codex/guides/agents-md
- Codex skills: https://developers.openai.com/codex/skills
