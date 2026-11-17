# Cold Email Skill

Install **`cold-email`** to give an LLM agent a client email workflow: onboarding, reusable company/brand/offer memory, single emails, variations, sequences, and approval-gated MailWizz campaign setup and tracking.

**Skill name:** `cold-email` · **Entrypoint:** [`skills/cold-email/SKILL.md`](skills/cold-email/SKILL.md)

This repository supplies instructions and blank data templates—not a running bot, email server, scheduler, MCP server, or credentials. Drafting does not require MailWizz. Sending requires a separately configured MailWizz MCP connection and host-enforced permissions and approval.

## Install

Run from the **private project where your bot works**, not from a public client-data repository. The [Skills CLI](https://github.com/vercel-labs/skills) requires Node.js 22.20+ and Git.

```bash
# Discover the skill without installing
npx skills add agarwalbikram/Cold-Email-Skill --list

# Install cold-email; choose your agent when prompted
npx skills add agarwalbikram/Cold-Email-Skill --skill cold-email
```

For a bot doing non-interactive installation, select its actual host. For example:

```bash
# Claude Code, project-local
npx skills add agarwalbikram/Cold-Email-Skill --skill cold-email --agent claude-code --copy --yes

# Codex, project-local
npx skills add agarwalbikram/Cold-Email-Skill --skill cold-email --agent codex --copy --yes

# Check installed skills
npx skills list
```

Use only the command matching your host. Add `--global` if you intentionally want shared instructions across projects; client data must still remain private and separate. Review an existing skill with the same name before replacing it. Reload/restart your host if needed for discovery. Installation does not automatically copy this repository's root `AGENTS.md` into your bot project.

### Instructions to give an LLM bot

```text
Install the cold-email skill from https://github.com/agarwalbikram/Cold-Email-Skill.
Read its README first. Use the Skills CLI from my private bot project, selecting
only cold-email and your actual agent host. Preserve any existing skill and client
data; report a name conflict rather than overwriting it. Verify the installed
skill is discoverable, then invoke cold-email by name. Follow its workspace and
agent policy references. Do not install MailWizz, add credentials, or send email.
```

The bot needs shell/file access and an Agent Skills-compatible host. An ordinary chat window can read instructions but cannot install files or provide persistent memory by itself. No single command makes every LLM platform discover skills.

### Manual install or uploaded repository

If the host does not support the CLI, copy the **entire** [`skills/cold-email/`](skills/cold-email/) directory into its documented skill directory, keeping the final directory named `cold-email`. Examples of project-local destinations:

| Host | Destination |
| --- | --- |
| Claude Code | `.claude/skills/cold-email/` |
| Codex | `.agents/skills/cold-email/` |
| Other host | Its documented skill directory, ending in `cold-email/` |

Do not copy just `SKILL.md`; `references/` and `assets/` are required resources. If uploading a ZIP to a host's skill importer, package the complete `cold-email/` directory in the archive format that host accepts—not `.git/`, `.projectmem/`, or client data. A generic repository attachment does not necessarily install or activate a skill.

Without a skill loader, configure the host to load the entrypoint and its linked references explicitly. `SKILL.md` is the [standard discovery filename](https://agentskills.io/specification); **`cold-email` is the name you invoke**.

## Tell your agent when to use it

Add this to your **existing** private bot project's `AGENTS.md` or equivalent host instructions; merge it rather than replacing unrelated instructions:

```text
For this dedicated client email bot, invoke the installed cold-email skill by name
for greetings, onboarding, email drafts, variations, sequences, company/brand
corrections, MailWizz setup, and campaign tracking. Follow its bundled
references/agent-policy.md and references/workspace.md. Keep live client state in
this private project's client-data/, never inside installed skill files. Never
send, schedule, activate, or test-send without exact operation/version approval.
```

The repository's [AGENTS.md](AGENTS.md) routes by this same skill name. The full runtime policy is bundled inside the skill so it survives installation without relying on repository-root files.

## First use and JSON files

Start with **“Use cold-email. Hi”**, or provide a complete brief:

> Use cold-email. Write three email variations for our consulting offer to B2B agency owners. Use the attached approved product PDF. Draft only; do not send.

After identifying the client, the bot initializes private files from these blank templates **only for a new client**:

| Bundled template | Private working file | Purpose |
| --- | --- | --- |
| [`assets/client-profile.json`](skills/cold-email/assets/client-profile.json) | `client-data/client-profile.json` | Client preferences and company/brand/niche/offer catalog |
| [`assets/campaigns.json`](skills/cold-email/assets/campaigns.json) | `client-data/campaigns.json` | Versioned drafts, approval references, remote IDs, history, aggregate statistics |

These JSON documents contain empty catalogs and record templates, not real clients or JSON Schema validation rules. Never edit the installed templates to store client facts: reinstalling/updating a skill can replace its files. The bot creates `client-data/sources/` only when authorized documents are supplied. Follow [workspace setup](skills/cold-email/references/workspace.md) for initialization, existing-data migration, and safe persistence.

In every consuming private project, ignore `client-data/` before use. This repository already includes that ignore rule. Git ignore does not protect tracked files or enforce access control. Keep each client's workspace and credentials separate; never publish client data, recipient lists, API keys, or campaign approval records.

Other example requests:

- “Use cold-email. Update this brand's tone to concise and direct for future emails.”
- “Use cold-email. Write a three-email sequence at days 0, 3, and 7. Draft only.”
- “Use cold-email. Help configure the selected draft in MailWizz; show the final packet before approval.”
- “Use cold-email. Show available aggregate stats for the campaign we saved.”

Missing persistent file tools must be reported; the bot must not pretend it saved memory. Missing MailWizz tools block remote operations, not a useful local draft. Approval and client isolation need enforcement by the host/tool gateway, not just prompts or JSON flags.

## Repository layout

```text
AGENTS.md                         # Route the bot to cold-email by name
README.md                         # Installation and usage
skills/
  cold-email/
    SKILL.md                      # Standard skill metadata and entrypoint
    assets/
      client-profile.json         # Blank profile template
      campaigns.json              # Blank campaign-register template
    references/                   # Bot policy, workspace, writing and MailWizz guides
    evals/
      evals.json                  # Behavioral evaluation prompts and expectations
```

`evals/evals.json` is an evaluation dataset, not an automated test runner. `.projectmem/` is local maintainer memory, not a runtime dependency or part of the installed skill. The writing references originated from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/main/skills/cold-email); this repository adds dedicated-client memory, bot routing, and MailWizz workflows.

## Updating

```bash
npx skills update cold-email
```

Review upstream changes before accepting them. Keep private working files outside the installation so updates cannot replace client memory. Back up private data through an authorized client-scoped process; never upload it with this skill.
