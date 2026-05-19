# Setting Up Codex for SE Work: First 30 Minutes

This guide helps Oracle Solutions Engineers, Sales Consultants, and Cloud Enterprise Architects set up a practical Codex workspace for day-to-day pre-sales work.

Codex CLI behavior and flags can vary by version, so verify your installed version and your organization's approved usage policy before relying on a specific command.

## 1. Install or Open Codex

OpenAI's Codex documentation describes CLI installation with:

```bash
npm install -g @openai/codex
```

Then start Codex:

```bash
codex
```

If your organization provides a managed Codex environment, use that instead of a personal setup.

## 2. Create a Working Directory

Create one root folder for SE work:

```bash
mkdir -p ~/se-workspace
cd ~/se-workspace
```

Use this workspace for customer folders, PoC code, RFI drafts, generated demo data, reusable prompts, and templates.

Suggested structure:

```text
se-workspace/
  customers/
  demos/
  prompts/
  templates/
  scratch/
```

## 3. Create a Starter `AGENTS.md`

In `~/se-workspace/AGENTS.md`, add standing instructions that describe your role, voice, and guardrails.

Example:

```markdown
# Oracle Solutions Engineering workspace

## Who I am
Principal Solutions Engineer at Oracle, covering OCI, Autonomous Database,
Fusion Cloud, Exadata, MySQL HeatWave, APEX, Analytics, AI, and adjacent products.
Pre-sales / sales consulting role.

## Voice / style
- Confident but factual; no marketing superlatives.
- Use Oracle product names carefully.
- When comparing to competitors, be balanced and flag where they have real strengths.
- Default to US English.
- Default to USD for pricing, but do not invent pricing.

## What I do most
- PoCs and demos
- SQL, Python, Node.js, and Terraform drafts for OCI demos
- RFI/RFP drafts
- Architecture conversions from AWS, Azure, or GCP to OCI
- Customer follow-up emails and executive summaries
- TCO model scaffolding
- Migration assessments
- Junior SE review

## Things to never do
- Do not fabricate Oracle pricing.
- Do not reference internal Oracle roadmap unless I explicitly provide approved language.
- Do not include customer PII in sample data.
- Generate synthetic data for demos.
- Mark uncertain claims as [VERIFY].
- Do not commit or push unless I explicitly ask.

## Useful preferences
- Prefer Mermaid diagrams for architecture drafts I can paste into slides.
- Prefer tables for service comparisons.
- Prefer executive summaries that separate facts, assumptions, and recommendations.
- Prefer demo artifacts that include setup, validation, reset, and troubleshooting steps.
```

`AGENTS.md` gives Codex standing instructions for a workspace. It is like briefing a new teammate before assigning tasks.

## 4. Use a Safe Launch Pattern

For local SE work, a safe default is to allow Codex to read and write inside the workspace while asking before actions that need approval.

Example pattern if your CLI supports these flags:

```bash
codex --sandbox workspace-write --ask-for-approval on-request
```

Optional shell alias:

```bash
alias se-codex='codex --sandbox workspace-write --ask-for-approval on-request'
```

## 5. Try One Real Task Today

Do not try to learn every feature first. Pick one real task:

- Draft a follow-up email
- Create a demo dataset
- Build an RFI answer table
- Convert an AWS architecture to OCI
- Create a migration assessment outline
- Review a junior SE's deck

Use Codex on that task, then save the prompt if it worked.

## Useful Official Codex References

- Codex quickstart: https://developers.openai.com/codex/quickstart
- Codex CLI: https://developers.openai.com/codex/cli
- Codex CLI command line options: https://developers.openai.com/codex/cli/reference
- Custom instructions with `AGENTS.md`: https://developers.openai.com/codex/guides/agents-md
- Codex skills: https://developers.openai.com/codex/skills
- Model Context Protocol in Codex: https://developers.openai.com/codex/mcp
- Codex best practices: https://developers.openai.com/codex/learn/best-practices
- Generate slide decks with Codex: https://developers.openai.com/codex/use-cases/generate-slide-decks
