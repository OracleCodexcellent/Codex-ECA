# Codex Playbook for Oracle Solutions Engineers and Cloud Enterprise Architects

This guide is for Oracle Solutions Engineers, Sales Consultants, Cloud Enterprise Architects, and senior technical pre-sales teams.

It is written for your daily work:

- Customer discovery calls
- OCI, Autonomous Database, Fusion Cloud, Exadata, MySQL HeatWave, APEX, Analytics, AI, and integration demos
- Proofs of Concept and Proofs of Value
- RFI and RFP responses
- Reference architectures
- TCO and business-case models
- Migration assessments from AWS, Azure, GCP, Snowflake, SQL Server, PostgreSQL, Redshift, BigQuery, or legacy Oracle estates
- Executive summaries and follow-up emails
- Reviewing work from junior SEs
- Building reusable prompt libraries and demo assets

Codex is not replacing your job. It is not the person in the customer conversation. It does not own the deal strategy, the political judgment, the pricing commitment, or the executive relationship.

Codex helps with the work around the work:

- Drafting
- Structuring
- Comparing
- Generating starter artifacts
- Creating sample data
- Building demo plumbing
- Formatting
- Summarizing
- Reviewing
- Turning rough notes into usable deliverables

Sometimes it saves 5%. Sometimes it saves 80%. The difference depends on the task.

## The Big Picture: What Changes in Your Day

Before Codex, a typical SE or Enterprise Architect day has a lot of small annoying tasks that eat time:

- "I need to mock up a quick demo by tomorrow."
- "I need to answer 12 RFI questions by Friday."
- "I need to convert this customer's AWS architecture into OCI terms."
- "I need to summarize a 90-minute discovery call before the account team forgets the details."
- "I need to update last quarter's TCO model with new assumptions."
- "I need to create synthetic data for a demo without exposing customer data."
- "I need to review a junior SE's architecture deck before it goes to the customer."

With Codex, many of these go from hours to minutes.

You stay in the same role. You still need technical judgment. You still need to know the customer. You still need to validate anything that affects pricing, sizing, security, or a contractual commitment.

The change is that you spend more time on the human parts:

- Relationship
- Discovery
- Judgment
- Storytelling
- Executive alignment
- Live demo delivery
- Competitive positioning

And less time on repetitive work:

- First drafts
- Boilerplate
- Sample schemas
- Synthetic data
- Formatting
- Table creation
- Slide outlines
- Follow-up emails
- Migration notes

## Two Big Payoff Areas

### 1. Faster PoCs and Demos

Codex can quickly create starter code, Terraform drafts, SQL scripts, sample data generators, demo UIs, runbooks, and README files.

That matters because most SE demos are not blocked by one brilliant idea. They are blocked by plumbing:

- You need realistic data.
- You need tables.
- You need sample queries.
- You need a small UI.
- You need a repeatable setup.
- You need a story that connects the demo to the customer's business problem.

Codex is very good at generating that first version.

### 2. Drafting at Scale

Codex is useful anywhere you are staring at a blank page:

- RFI responses
- RFP answers
- Executive summaries
- Architecture readouts
- Discovery recaps
- Workshop agendas
- Demo scripts
- Migration plans
- Risk registers
- TCO assumption models

You should not blindly send the first draft. But a first draft is much easier to edit than an empty page.

## The Default SE Prompt Pattern

Use this structure whenever the task matters:

```text
Act as an Oracle Solutions Engineer and Cloud Enterprise Architect.

Goal: <what I need>
Customer context: <industry, business problem, current platform, known constraints>
Audience: <CIO, CTO, enterprise architects, developers, procurement, security, operations>
Oracle scope: <OCI, Autonomous Database, APEX, Exadata, MySQL HeatWave, Analytics, Fusion, etc.>
Inputs: <notes, docs, repo, spreadsheet, diagram, RFI questions>
Output: <email, deck outline, PPTX, DOCX, XLSX, SQL, Terraform, demo script>
Rules:
- Be confident but factual.
- Separate facts from assumptions.
- Mark anything that needs validation as [VERIFY].
- Do not fabricate pricing, benchmarks, roadmap, or customer-specific claims.
- Do not expose secrets, customer confidential data, or PII.
- Do not create, modify, or delete real cloud resources unless I explicitly ask.
- Do not commit or push changes.
```

Short version:

```text
Act as an Oracle Solutions Engineer. Turn the context below into a customer-ready artifact. Be factual, separate assumptions from facts, mark unknowns as [VERIFY], and do not invent pricing or roadmap.
```

## Scenario 1: Building a Quick PoC for a Customer

### The Situation

A customer asks you to show how retail data could land in Autonomous Data Warehouse, get transformed, and surface in Oracle Analytics Cloud. You have 48 hours before the next call.

Without Codex, you might spend the first day hunting for sample schemas, hand-writing SQL, creating fake data, and formatting a README. Day two becomes rushed demo prep.

With Codex, you ask it to create the starter assets.

### Prompt

```text
I'm building a PoC for a retail customer.

I need:
- A 5-table star schema: sales fact plus product, customer, store, and date dimensions
- A Python script that generates 100,000 realistic-looking rows of sales data
- SQL DDL that creates these tables in Oracle Autonomous Data Warehouse
- Sample SQL queries showing top products by region and month
- A README explaining how to load the data into ADW and how to run the queries

The customer is a US grocery chain. Make the data plausible for that industry:
- Product names should look like grocery products
- Store regions should look realistic
- Sales patterns should vary by product category, region, and season

Use synthetic data only. Do not include real customer data. Do not create cloud resources. Do not commit or push.
```

### What Codex Can Create

- `schema.sql`
- `generate_data.py`
- CSV files
- `sample_queries.sql`
- `README.md`
- Optional `demo_script.md`

### Follow-Up Prompts

```text
Now add a daily sales aggregation table and SQL to populate it from the sales fact table.
```

```text
Create a short Oracle Analytics Cloud dashboard specification for this dataset. Include chart names, filters, metrics, dimensions, and the business question each chart answers.
```

```text
Generate the same dataset as CSV files that can be uploaded through the OCI console or loaded into Autonomous Data Warehouse.
```

```text
Create a 10-minute demo script that starts with the business problem, shows the data model, runs three queries, and explains what the customer should notice.
```

## Scenario 2: Writing RFI and RFP Responses

### The Situation

A 60-question RFI lands in your inbox. Many answers already exist somewhere in old proposals, product pages, internal notes, or security documents. The problem is finding them, rewriting them consistently, and marking the ones that need SME review.

### Prompt for One RFI Question

```text
I need to answer this RFI question:

"Describe how the platform encrypts data at rest, including key management options and customer-controlled key support."

Use the attached or referenced materials as source content:
- Past RFP responses
- OCI security overview
- Oracle product documentation
- Internal approved language, if available

Write a 200-300 word response in our usual voice:
- Confident but factual
- No marketing fluff
- No unsupported claims
- No invented roadmap

End with one sentence pointing the customer to relevant Oracle documentation.
Mark anything that needs SME or legal validation as [VERIFY].
```

### Prompt for an Entire RFI

```text
For each question in the RFI file, draft a first-pass answer using the provided source documents.

Output as a Markdown table with columns:
1. Question number
2. Question
3. Draft answer
4. Source used
5. Confidence: High, Medium, or Low
6. SME review needed: Yes or No
7. Notes

Rules:
- Mark any answer that requires new content as [NEEDS SME REVIEW].
- Do not invent pricing, roadmap, certifications, SLAs, benchmarks, or legal commitments.
- Keep the tone factual and customer-ready.
```

### What Codex Is Good At Here

- Finding reusable language
- Making inconsistent answers sound like one author wrote them
- Creating answer tables
- Flagging missing source material
- Creating SME review lists

### What You Still Own

- Final accuracy
- Legal commitments
- Pricing
- Security statements
- Contractual language
- Competitive positioning

## Scenario 3: Converting AWS, Azure, or GCP Architectures to OCI

### The Situation

A customer shows you an AWS architecture with EC2, S3, RDS PostgreSQL, Lambda, API Gateway, Cognito, and CloudWatch. They ask: "What would this look like on OCI?"

### Prompt

```text
Convert this AWS architecture to an OCI equivalent:

- 3 x EC2 m5.xlarge running Node.js APIs
- S3 bucket for user uploads, about 5 TB
- RDS PostgreSQL db.r5.large, Multi-AZ
- Lambda functions for image processing
- API Gateway in front of EC2 and Lambda
- Cognito for user authentication
- CloudWatch for logs and metrics

Produce:
1. A side-by-side service mapping table: AWS service, OCI service, notes
2. A target OCI architecture narrative
3. Key differences the customer should understand
4. Security and operational considerations
5. Open questions before recommending a final design

Do not create cloud resources. Do not estimate pricing unless I provide validated inputs.
```

### Follow-Up Prompt: Generate Terraform Drafts

```text
Now write a Terraform starter template for the OCI side using the Oracle OCI provider.

Rules:
- Use sensible placeholders.
- Add comments explaining each resource block in plain English.
- Stub networking details with TODO comments instead of guessing.
- Do not include real OCIDs, secrets, tenancy details, or customer names.
- Do not run terraform apply.
```

### Service Mapping Examples

Use Codex to produce the full table, but common mappings may include:

| Customer Has | OCI Conversation Starter |
|---|---|
| Amazon EC2 | OCI Compute |
| Amazon S3 | OCI Object Storage |
| Amazon RDS PostgreSQL | Oracle Base Database Service, Autonomous Database, MySQL HeatWave, or PostgreSQL-compatible options depending on the workload |
| AWS Lambda | OCI Functions |
| Amazon API Gateway | OCI API Gateway |
| Amazon Cognito | OCI IAM identity domains or integration with the customer's identity provider |
| Amazon CloudWatch | OCI Logging, Monitoring, Alarms, and Application Performance Monitoring |

## Scenario 4: Following Up After a Customer Call

### The Situation

You just finished a 90-minute discovery call. You have rough notes. You need a customer email, an internal account-team summary, and your own action list before the details fade.

### Prompt

```text
Below are my raw notes from a discovery call with ACME Corp.

<paste raw notes>

Produce three things:

1. A polite customer-facing follow-up email.
   Include:
   - Brief summary of what we discussed
   - What we heard as their goals and pain points
   - Agreed next steps
   - Who owes what by when
   - Proposed timing for the next meeting

2. A one-paragraph internal summary for the sales rep.
   Focus on:
   - Customer pain points
   - Top Oracle opportunity
   - Competitive risks mentioned
   - Decision timeline
   - Any executive stakeholder signals

3. A bulleted action list for me this week.
   Include:
   - Action
   - Owner
   - Suggested deadline
   - Dependency

Do not make up details. If anything is ambiguous, mark it [VERIFY].
```

### Why This Saves Time

You are not asking Codex to decide the strategy. You are asking it to convert messy notes into organized communication. You edit the nuance, but Codex removes the blank-page problem.

## Scenario 5: Demo Prep with MySQL HeatWave Sample Data

### The Situation

You are demoing MySQL HeatWave to an analytics buyer. You need realistic-looking data they can query live.

### Prompt

```text
Generate a MySQL schema and synthetic data for a fictional ride-sharing company.

Tables:
- users
- drivers
- rides
- payments
- ratings

Data requirements:
- 1 million synthetic ride rows
- Realistic distributions
- Most rides are short
- Most drivers are part-time
- Ratings skew positive
- Payment methods vary by region
- No real customer data or real personal data

Output:
1. SQL DDL
2. Data generation script, preferably producing CSVs for faster loading
3. Loading instructions
4. Five demo queries that highlight analytics on large joins
5. A short comment above each query explaining the business question it answers
6. A 15-minute demo script

Do not create cloud resources. Do not commit or push.
```

### Follow-Up Prompts

```text
Add a second demo path for operational analytics: driver utilization, city-level demand, cancellation patterns, and revenue by hour.
```

```text
Create speaker notes explaining why this demo is relevant to an analytics buyer and what questions to ask during the demo.
```

## Scenario 6: Helping a Customer Migrate Code to Oracle

### The Situation

A customer is migrating from PostgreSQL to Oracle Database. They have PL/pgSQL functions and are worried about syntax differences, behavior differences, and hidden gotchas.

### Prompt

```text
Convert the PL/pgSQL functions in the provided folder to Oracle PL/SQL.

For each function:
- Produce the Oracle equivalent in a corresponding file under an oracle/ folder
- Add a comment block at the top listing non-trivial differences
- Flag anything that does not have a clean Oracle equivalent with -- TODO: REVIEW
- Preserve business behavior where possible

When done, create migration-notes.md summarizing:
1. Common conversion patterns
2. Risky areas
3. Manual review items
4. Testing recommendations
5. Questions to ask the customer

Do not overwrite original files. Do not commit or push.
```

### Same Pattern Works For

- PostgreSQL to Oracle Database
- SQL Server T-SQL to Oracle PL/SQL
- Snowflake SQL to Autonomous Data Warehouse
- Redshift SQL to Autonomous Data Warehouse
- BigQuery SQL to Autonomous Data Warehouse
- Legacy shell scripts to OCI-native automation

### Important Warning

Codex can create a strong first-pass conversion, but database migrations require serious validation:

- Data type behavior
- Date and timestamp handling
- Transaction behavior
- Error handling
- Performance plans
- Index strategy
- Stored procedure side effects
- Security and grants

Treat the output as a migration accelerator, not a certified conversion.

## Scenario 7: TCO and Pricing Models

### The Situation

The sales rep asks for a TCO comparison: current AWS spend versus a proposed OCI footprint. They need a starting point by tomorrow morning.

### Prompt

```text
Build a TCO comparison workbook structure from these inputs.

Current AWS monthly spend:
- 12 EC2 m5.2xlarge: <validated monthly cost>
- RDS PostgreSQL db.r5.4xlarge: <validated monthly cost>
- 50 TB S3 storage: <validated monthly cost>
- 200 TB egress to internet: <validated monthly cost>
- Reserved instance coverage: 60%

Proposed OCI footprint:
- 12 OCI Compute VM.Standard.E4.Flex, 16 OCPU each
- Autonomous Database for Transaction Processing, 8 OCPU with autoscaling
- 50 TB OCI Object Storage
- Similar egress pattern

Output:
1. Side-by-side monthly cost table
2. 3-year cumulative cost model
3. Sensitivity analysis
4. Assumptions table
5. Inputs that require validation
6. Executive summary

Do not invent prices. Use placeholders where pricing is not provided. Mark pricing, discounts, commitment levels, licensing, and egress assumptions as [VERIFY].
```

### Better Prompt When Using the Spreadsheets Skill

```text
Use the Spreadsheets skill to create a TCO comparison workbook as an XLSX file.

Tabs:
1. Executive Summary
2. Input Assumptions
3. Current-State AWS Costs
4. Proposed OCI Costs
5. 3-Year View
6. Sensitivity Analysis
7. Risks and Validation Items

Use formulas and clear formatting. Do not invent pricing. Use placeholders for prices that must come from official tools or account-specific pricing. Save locally. Do not commit or push.
```

## Scenario 8: Building a Quick APEX or Web App Demo

### The Situation

You want to show how quickly Oracle APEX or a lightweight web app can create an operational front end over Oracle data.

### APEX Demo Prompt

```text
Design an Oracle APEX demo on Autonomous Database.

Business scenario: Customer support ticket triage
Existing table: CUSTOMER_TICKETS
Columns:
- id
- customer_id
- subject
- status
- priority
- created_at
- assigned_to

Create:
1. APEX application name and purpose
2. User personas
3. Page list
4. Interactive report design
5. Ticket detail form
6. Workflow for marking a ticket resolved
7. Dashboard cards and charts
8. Role-based access model
9. Demo click path
10. Setup checklist
11. Production considerations

Write for an SE who understands cloud and databases but may not be an APEX developer.
```

### Lightweight Node.js Demo Prompt

```text
Build a small Node.js Express demo app for an Oracle Autonomous Database table named CUSTOMER_TICKETS.

The app should:
- Connect using an Oracle wallet path and credentials provided through environment variables
- Have three routes:
  1. List open tickets
  2. View one ticket
  3. Mark a ticket resolved
- Use minimal server-rendered HTML, no React
- Be readable on a screen share
- Include setup instructions
- Include a README

Do not include real credentials. Do not commit or push.
```

## Scenario 9: Reviewing Junior SE Work

### The Situation

You are asked to review a demo script, RFP draft, architecture diagram, or TCO model from a less-experienced SE.

### Prompt

```text
Review this draft as if you were the customer's procurement team and enterprise architecture review board.

Look for:
1. Claims that are overstated
2. Missing assumptions
3. Missing security details
4. Missing pricing or sizing caveats
5. Architecture gaps
6. Weak demo story
7. Competitive risks
8. Anything the customer is likely to challenge

Do not rewrite the whole document.
Give me a prioritized punch list of issues by deal risk:
- High
- Medium
- Low

For each issue, explain why it matters and what the author should fix.
```

### Why This Helps

Codex does the tedious first-pass review. You still provide the strategic feedback:

- "We should lead with business value."
- "This architecture does not address the customer's security concern."
- "This demo does not connect to the executive sponsor's stated pain."

## Scenario 10: Staying Current on Oracle's Product Portfolio

### The Situation

Oracle services evolve constantly. Database features, OCI capabilities, APEX updates, Fusion Cloud enhancements, AI services, and multicloud offerings change faster than any one person can fully track.

### Prompt with Release Notes

```text
I pasted release notes or product update content below.

Summarize:
1. What is actually new
2. What appears to be renamed, repackaged, or incremental
3. Why it matters to an Oracle Solutions Engineer
4. What it means when selling against AWS, Azure, GCP, Snowflake, Databricks, or other competitors
5. Which customer conversations this could affect this week
6. Which claims need verification before I use them externally

Use a practical field-facing tone.

Release notes:
<paste content>
```

### Prompt with Official Documentation

```text
Verify the current Oracle product names and capabilities from official Oracle documentation before drafting customer-facing content.

Focus on:
- What the service does
- What changed recently, if available
- How to explain the value in plain English
- What not to overclaim

Cite the official Oracle sources used.
```

## Scenario 11: Fusion Cloud Discovery and Demo Planning

### The Situation

You are involved in a conversation around Oracle Fusion Cloud ERP, HCM, SCM, or CX. The customer may care about process modernization, reporting, integration, AI, security, or migration from legacy systems.

### Prompt

```text
Create a discovery and demo plan for an Oracle Fusion Cloud conversation.

Fusion area: <ERP, HCM, SCM, CX, or cross-functional>
Customer industry: <industry>
Business process: <for example: procure-to-pay, hire-to-retire, order-to-cash, demand planning>
Audience: Business leaders, enterprise architects, integration leaders, and security stakeholders

Create:
1. Business discovery questions
2. Current-state process questions
3. Integration questions
4. Data and reporting questions
5. Security and access questions
6. Demo storyline
7. Suggested demo flow
8. OCI and integration touchpoints
9. Risks and assumptions
10. Follow-up artifacts to create

Do not invent product capabilities. Mark anything requiring validation as [VERIFY].
```

### Why This Helps

Fusion conversations often cross business and technical teams. Codex can help you prepare questions that connect process, data, integration, identity, reporting, and operations.

## Scenario 12: Exadata and Database Platform Modernization

### The Situation

The customer wants to understand whether Exadata, Exadata Database Service, Autonomous Database, or another Oracle Database option fits their workload.

### Prompt

```text
Prepare a database platform modernization discussion guide.

Customer context:
<paste notes>

Compare these options where relevant:
- Oracle Exadata
- Exadata Database Service
- Autonomous Database
- Base Database Service
- Oracle Database 23ai
- MySQL HeatWave, if the workload is MySQL or analytics-focused

Output:
1. Workload discovery questions
2. Performance and availability questions
3. Data protection and DR questions
4. Operational model comparison
5. Fit-for-purpose recommendation framework
6. Risks and validation items
7. Customer-facing explanation in plain English

Do not make a final recommendation without enough workload facts.
```

## Scenario 13: Analytics and Executive Insight Demo

### The Situation

The buyer wants dashboards and insight, not a database discussion. You need to connect data architecture to business outcomes.

### Prompt

```text
Design an Oracle Analytics demo for this customer scenario:
<scenario>

Create:
1. Business questions the dashboard should answer
2. Synthetic dataset design
3. Metrics and dimensions
4. Dashboard pages
5. Suggested charts
6. Filters
7. Drill-down paths
8. Executive talking points
9. Data governance considerations
10. Follow-up questions

Keep the story business-first, not tool-first.
```

### Good Follow-Up

```text
Create a PowerPoint-ready dashboard storyboard. For each dashboard page, include the title, audience, key message, visuals, and what I should say while presenting it.
```

## Creating PowerPoint Decks with the Presentations Skill

Use the Presentations skill when you want Codex to create a real PowerPoint file, not just an outline.

### Good Uses

- Customer architecture readout
- Discovery summary deck
- OCI target-state architecture deck
- Autonomous Database and APEX demo deck
- Migration assessment deck
- RFP oral presentation deck
- Architecture review board deck
- Executive briefing
- TCO summary deck

### Prompt

```text
Use the Presentations skill to create a PowerPoint deck.

Deck purpose: Customer architecture readout
Audience: CIO, CTO, enterprise architects, security leader, application owners
Customer scenario: <describe customer>
Desired length: 10 slides
Tone: Executive, practical, architecture-led, not salesy

Slides:
1. Title and customer objective
2. Executive summary
3. Current-state challenges
4. Target-state OCI architecture
5. Service mapping
6. Data and integration flow
7. Security and governance model
8. Migration or demo roadmap
9. Risks, assumptions, and decisions
10. Next steps

Requirements:
- Make every slide title a conclusion, not a label.
- Include speaker notes.
- Include diagrams where useful.
- Use clean, executive-readable visuals.
- Render and verify the deck visually.
- Save as a PPTX file locally.
- Do not commit or push.
```

### Example of Better Slide Titles

Weak:

```text
APEX Overview
```

Better:

```text
APEX accelerates secure workflow delivery on Autonomous Database
```

Why:

Executives and enterprise architects remember the conclusion faster when the slide title states the point.

## Creating Word Documents with the Documents Skill

Use the Documents skill when the output should be a polished `.docx`.

### Good Uses

- Solution design document
- Architecture decision record
- Discovery readout
- Migration assessment
- Security architecture review
- Demo setup guide
- Production readiness report
- Workshop summary

### Prompt

```text
Use the Documents skill to create a Word document.

Document type: OCI solution design document
Audience: Enterprise architects, security team, application owners
Scenario: <describe customer scenario>

Include:
1. Executive summary
2. Business goals
3. Current-state architecture
4. Target-state OCI architecture
5. Service mapping
6. Data flow
7. Security model
8. Operations model
9. Migration approach
10. Risks and mitigations
11. Assumptions
12. Open questions
13. Next steps

Render and verify the document layout. Save locally as DOCX. Do not commit or push.
```

## Creating Spreadsheets with the Spreadsheets Skill

Use the Spreadsheets skill when the output should be a real `.xlsx` workbook.

### Good Uses

- TCO model
- Migration wave plan
- Application inventory
- RFI compliance matrix
- Requirements traceability matrix
- Risk register
- Action tracker
- Demo build checklist
- Sizing assumptions

### Prompt

```text
Use the Spreadsheets skill to create an Excel workbook for OCI migration planning.

Workbook tabs:
1. Application Inventory
2. Dependencies
3. Cloud Readiness Score
4. Target OCI Services
5. Migration Waves
6. Risks
7. Assumptions
8. Action Items

Include useful columns, sample rows, formulas where appropriate, filters, and clear formatting.
Use synthetic sample data only.
Save locally as XLSX.
Do not commit or push.
```

## Using Browser, Image, and Connector Capabilities

### Browser Use

Use browser validation when Codex creates a local demo, prototype, or generated HTML page.

Prompt:

```text
Start the local demo server, open it in the browser, verify the main flow, check desktop and mobile layouts, capture issues, and tell me the local URL. Do not commit or push.
```

Why:

Reading files does not prove the demo works. Browser validation checks the actual user experience.

### Image Generation

Use image generation for safe, synthetic visuals:

- Demo title slide background
- Generic industry visual
- Synthetic user avatar
- Conceptual workflow illustration
- Non-branded mock product image

Prompt:

```text
Use image generation to create a professional synthetic visual for a supplier onboarding modernization demo. Do not include real logos, real customer names, real employees, or confidential data.
```

### Enterprise Connectors

If configured, connectors can help Codex pull context from:

- Outlook Calendar
- Outlook Email
- Slack
- Confluence
- SharePoint or OneDrive
- Jira

Prompt:

```text
Use available enterprise connectors to gather architecture-relevant context for this customer meeting. Summarize only what is relevant to the solution discussion. Do not expose sensitive details unnecessarily. Cite the source type, such as email, calendar, Confluence, SharePoint, Slack, or Jira.
```

Use caution:

Only use customer or internal data when you are authorized to do so.

## Where Codex Hurts More Than It Helps

Codex is useful, but not for everything.

### Customer-Facing Live Conversation

If a customer asks a question live, do not pause the relationship to ask Codex for the perfect answer. Talk like a human. Use Codex later to write the follow-up, validate details, or create supporting material.

### Numbers You Will Be Held Accountable To

Pricing, sizing, benchmarks, savings claims, performance estimates, licensing impact, and commitment discounts must be validated.

Codex can create the model structure. You own the final numbers.

Use this line:

```text
Do not invent pricing or benchmarks. Use placeholders and mark all pricing, sizing, discount, and performance assumptions as [VERIFY].
```

### Confidential Data You Cannot Share

Do not paste:

- Customer production data
- Confidential contracts
- Personal information
- Regulated data
- Secret keys or tokens
- Unannounced Oracle roadmap
- Non-public competitive information

Use synthetic or anonymized data for demos.

### Deal Strategy That Requires Judgment

Codex can suggest options, but it cannot read the room. Questions like "Should we push back on this RFP requirement?" depend on the rep, customer politics, procurement dynamics, competition, and executive sponsorship.

### Topics Where You Cannot Spot a Wrong Answer

Codex can be confidently wrong. If you ask it about something where you cannot detect an error, treat the output as a hypothesis to verify.

## Setting Up Codex for SE Work: First 30 Minutes

This section uses Codex CLI examples. CLI behavior and flags can vary by version, so verify your installed version and your organization's approved usage policy.

OpenAI's help documentation describes Codex CLI installation with:

```bash
npm install -g @openai/codex
```

It also supports signing in with ChatGPT through the CLI in supported plans and environments.

### 1. Install or Open Codex

```bash
npm install -g @openai/codex
codex
```

If your organization provides a managed Codex environment, use that instead of a personal setup.

### 2. Create a Working Directory

```bash
mkdir -p ~/se-workspace
cd ~/se-workspace
```

### 3. Create a Starter `AGENTS.md`

In `~/se-workspace/AGENTS.md`, add something like this:

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

### Why `AGENTS.md` Helps

`AGENTS.md` gives Codex standing instructions for a workspace. It is like telling a new teammate how you work before assigning tasks.

### 4. Use a Safe Launch Pattern

For local SE work, a safe default is to allow Codex to read and write inside the workspace while asking before actions that need approval.

Example pattern if your CLI supports these flags:

```bash
codex --sandbox workspace-write --ask-for-approval on-request
```

Optional shell alias:

```bash
alias se-codex='codex --sandbox workspace-write --ask-for-approval on-request'
```

### 5. Try One Real Task Today

Do not try to learn every feature first. Pick one real task:

- Draft a follow-up email
- Create a demo dataset
- Build an RFI answer table
- Convert an AWS architecture to OCI
- Create a migration assessment outline
- Review a junior SE's deck

Use Codex on that task, then save the prompt if it worked.

## A Realistic Week with Codex

### Monday

9:00: Customer kickoff call.

10:00: Codex drafts the follow-up email, internal summary, and action list from rough notes.

11:00: Codex generates a starter PoC schema based on the customer's use case.

Afternoon: You refine the demo story, validate assumptions, and align with the account team.

### Tuesday

Morning: An RFI arrives. Codex drafts first-pass answers for the questions that have source material.

Afternoon: The sales rep asks for a TCO comparison. Codex creates the workbook structure; you fill in validated numbers.

### Wednesday

Demo prep for Thursday.

Codex creates:

- Synthetic data
- Sample SQL queries
- A lightweight web or APEX demo plan
- A demo script
- Troubleshooting notes

You spend the evening rehearsing the customer story, not building plumbing.

### Thursday

Live demo. Codex stays closed.

After the demo, Codex drafts:

- Customer recap email
- Internal "how it went" summary
- Risk and action register
- Follow-up demo improvements

### Friday

Peer review and cleanup.

Codex helps:

- Review a junior SE's RFP answer
- Create a punch list for an architecture deck
- Convert one stored procedure or query for a customer technical contact
- Save reusable prompts into your prompt library

## Personal Prompt Library

Every time a prompt works, save it.

Suggested folders:

```text
se-workspace/
  prompts/
    discovery/
    demos/
    rfi-rfp/
    migration/
    tco/
    follow-up/
    review/
  customers/
  demos/
  templates/
```

Good prompts become reusable assets. A prompt that saves you two hours each week can save a team hundreds of hours if shared.

## Quick Copy-Paste Prompt Library

### Discovery Prep

```text
Act as an Oracle Cloud Enterprise Architect. Create a discovery guide for this customer situation. Include business questions, architecture questions, data questions, integration questions, security questions, operations questions, and success criteria. Explain why each question matters.
```

### Meeting Follow-Up

```text
Turn these raw notes into a customer follow-up email, internal account-team summary, and action list. Do not invent details. Mark ambiguous items as [VERIFY].
```

### OCI Service Mapping

```text
Map these customer requirements to OCI services. Return a table with requirement, recommended OCI service or pattern, rationale, dependencies, risks, and open questions. Separate facts from assumptions.
```

### AWS to OCI

```text
Convert this AWS architecture to OCI. Produce a side-by-side service mapping, target OCI architecture narrative, key differences, risks, and open questions. Do not estimate pricing unless I provide validated inputs.
```

### RFI Response

```text
Draft an RFI answer using only the provided source material. Use a confident but factual tone. Mark anything requiring SME review as [NEEDS SME REVIEW]. Do not invent commitments.
```

### Demo Plan

```text
Create a demo plan for this Oracle solution. Include business problem, personas, architecture, data model, sample data, setup steps, demo click path, talking points, reset steps, troubleshooting, and production caveats.
```

### PowerPoint Deck

```text
Use the Presentations skill to create a customer-ready PowerPoint deck. Include speaker notes, architecture visuals, conclusion-based slide titles, and render verification. Save locally as PPTX. Do not commit or push.
```

### TCO Workbook

```text
Use the Spreadsheets skill to create a TCO workbook. Include input assumptions, current-state costs, proposed OCI costs, 3-year view, sensitivity analysis, risks, and validation items. Do not invent pricing.
```

### Junior SE Review

```text
Review this as a senior Oracle SE. Give me a prioritized punch list of issues by deal risk. Focus on overstated claims, missing assumptions, weak architecture logic, security gaps, pricing caveats, and likely customer objections.
```

## Final Advice

Start small. Pick one task type and use Codex for it for a week.

Do not try to automate your whole job. Build trust with one workflow:

- Follow-up emails
- RFI drafts
- Demo data
- Architecture mappings
- TCO workbook scaffolding
- Junior SE reviews

Stay skeptical. Codex is fast and confident, but it can be wrong. Your value is judgment. Codex amplifies that judgment when you use it carefully.

Share what works. A good prompt is a reusable field asset.

Do not optimize away the part of SE work that matters most: showing customers what is possible and helping them make a good decision.

## Where to Go Next

Suggested companion guides to create or maintain in this workspace:

- `codex-tutorial.md`: Basic and medium Codex usage for SEs
- `codex-most-used-commands.md`: Daily-use Codex commands and prompts
- `codex-commands-guide.md`: Full command reference
- `codex-concepts-guide.md`: Concepts such as tokens, MCP, tools, skills, approvals, and connectors

Useful official references:

- OpenAI Codex CLI getting started: https://help.openai.com/en/articles/11096431
- OpenAI Codex CLI sign-in with ChatGPT: https://help.openai.com/en/articles/11381614-codex-cli-and-sign-in-withgpt
- Using Codex with your ChatGPT plan: https://help.openai.com/en/articles/11369540
- Oracle Cloud Infrastructure: https://www.oracle.com/cloud/
- Oracle Autonomous Database documentation: https://docs.oracle.com/en/cloud/paas/autonomous-database/
- Oracle APEX: https://www.oracle.com/apex/
- Oracle APEX Application Development: https://www.oracle.com/application-development/apex/
- OCI Generative AI overview: https://docs.oracle.com/en-us/iaas/Content/generative-ai/overview.htm
