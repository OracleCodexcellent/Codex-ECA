# Setting Up Codex with GitHub in the Terminal

This guide is for Oracle Solutions Engineers and Cloud Enterprise Architects who want to use Codex from the terminal and let Codex handle GitHub work such as creating files, creating branches, committing, pushing, and opening pull requests.

The simple flow is:

1. Install Codex in the terminal.
2. Open Codex in your repository.
3. Ask Codex to connect or verify GitHub access.
4. If GitHub asks for a password and your account uses MFA, use a GitHub personal access token as the password.

## 1. Install Codex in the CLI

Install Codex:

```bash
npm i -g @openai/codex
```

Start Codex:

```bash
codex
```

The first time you run Codex, sign in with your ChatGPT account or your OpenAI API key, depending on how your company has approved access.

## 2. Open Codex in Your Repository

Go to the folder where your repository is located:

```bash
cd ~/path/to/your/repository
codex
```

Then ask Codex:

```text
Check this repository and tell me:
- what branch I am on
- whether GitHub is connected
- whether I can create a branch
- whether I can commit and push

Do not change files.
Do not commit or push.
```

If the repository is not connected yet, ask:

```text
Connect this local folder to my GitHub repository:
https://github.com/<org>/<repo>.git

Use HTTPS.
If GitHub asks for a username and password, pause and tell me exactly what to enter.
Do not store or print my token.
```

## 3. Create a GitHub Token

If GitHub MFA or SSO is enabled, your normal GitHub password will usually not work for Git commands.

Create a GitHub personal access token, also called a PAT:

1. Go to GitHub in your browser.
2. Click your profile picture.
3. Open `Settings`.
4. Open `Developer settings`.
5. Open `Personal access tokens`.
6. Create a fine-grained token if possible.
7. Select only the repository you need.
8. Give it the minimum permissions needed, such as read/write access to repository contents.
9. Set an expiration date.
10. Copy the token once when GitHub shows it.

Important: this is a GitHub token, not your OpenAI API key.

## 4. Use the Token as the GitHub Password

When Codex tries to push, pull, or clone using HTTPS, GitHub may ask for:

```text
Username:
Password:
```

Enter:

```text
Username: your GitHub username
Password: your GitHub personal access token
```

For MFA accounts, the token is used in place of your GitHub password for HTTPS Git operations.

Do not paste the token into a Markdown file, pull request, commit message, or customer document. Only paste it into the secure password prompt when GitHub asks for it.

## Example: What I Did in This Repository

These are examples of the plain-English requests used to build this repository.

Create the first tutorial locally:

```text
Can you create a tutorial file for me for commonly used commands in Codex by Oracle Solution Engineers or Enterprise architects. Don't commit or push, make the changes locally.
```

Refine it for architects:

```text
The file you created is very generic. I want it specific to Cloud Enterprise architects and Oracle Solution Engineers.
```

Create a branch, push, and open a pull request:

```text
Can you create a new branch and push the change to the branch and create a PR with detailed description.
```

Address pull request comments locally:

```text
There are a few PR comments. Can you address that locally in the PR and don't commit or push.
```

Commit and push the fixes:

```text
Commit and push to the branch and update PR description accordingly.
```

Pull latest main and create a new branch:

```text
Can you go to main branch and pull the latest changes and then create a new branch locally.
```

Commit only a specific file:

```text
Commit and push these specific files only: CODEX_SE_SETUP.md
```

## Safe Prompts to Use

Before publishing:

```text
Show me what files changed and what will be committed. Do not commit or push yet.
```

To avoid adding local junk files:

```text
Commit and push only the files I name. Exclude untracked files, IDE folders, local settings, temporary files, credentials, and tokens.
```

To create a pull request:

```text
Push this branch to GitHub and create a pull request against main with a detailed description.
```

To sync after merge:

```text
My pull request was merged. Switch to main, pull the latest changes, and tell me whether my local repo is clean.
```

## Official References

- Codex CLI: https://developers.openai.com/codex/cli
- GitHub personal access tokens: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens
- GitHub with two-factor authentication: https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/accessing-github-using-two-factor-authentication
