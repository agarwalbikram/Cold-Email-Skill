# Bikram Cold Email Skill

Install **Bikram Cold Email Skill** (`bikram-cold-email-skill`) to give an LLM agent a client email workflow: onboarding, reusable company/brand/offer memory, single emails, variations, sequences, and approval-gated MailWizz campaign setup and tracking.

**Skill name:** `bikram-cold-email-skill` · **Entrypoint:** [`skills/bikram-cold-email-skill/SKILL.md`](skills/bikram-cold-email-skill/SKILL.md)

**v3.10.0 tags and footer:** every newly composed email, variation and sequence step includes `[FNAME]`, relevant recipient fields such as `[COMPANYNAME]`, a personal sender/company/website signature, and **Unsubscribe** linked to `[UNSUBSCRIBE_URL]`. Proposed draft tags are allowed before list selection; exact field mapping, sender values and working unsubscribe rendering remain mandatory before sending. Custom company tags are not universal MailWizz fields.

**v3.9.1 conversation repair:** first-use greeting asks for the company/website in chat instead of a one-option setup form. General introductions lead with the buyer's purchase goal, not supporting software features; negative quality feedback preserves that offer and CTA. Stock subject examples removed. Research must cover accessible core service/use-case pages before final recommendations. Recorded conversation replays do not establish deployed-host activation or runtime tool behavior.

**v3.9.0 original copy and subject hooks:** a style reference guides voice and useful detail, not sentences to copy. Exact-body preservation requires an explicit instruction; requested template variables remain supported independently. Subjects must offer a relevant reason to read that the body delivers, not just describe the service. These are copy-quality requirements, not promises of higher open rates.

**v3.8.0 URL-first research:** supply a product/company URL and the bot researches relevant public pages before recommending target companies and decision-makers. It uses navigation/sitemaps, reports actual read/failed/skipped coverage and cites sources; inaccessible pages or unavailable browsing remain explicit limits. A sitemap listing is not proof of reading every page. Recommendations do not silently overwrite saved audiences or authorize sending. Supplied-template fidelity remains supported. This package provides instructions, not its own crawler; the host must expose web tools.

This repository supplies instructions and blank data templates—not a running bot, email server, scheduler, MCP server, or credentials. Drafting does not require MailWizz. Sending requires a separately configured MailWizz MCP connection and host-enforced permissions and approval.

## Install

Run from the **private project where your bot works**, not from a public client-data repository. The [Skills CLI](https://github.com/vercel-labs/skills) requires Node.js 22.20+ and Git.

```bash
# Discover the skill without installing
npx skills add agarwalbikram/Cold-Email-Skill --list

# Install Bikram Cold Email Skill; choose your agent when prompted
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill
```

For a bot doing non-interactive installation, select its actual host. For example:

```bash
# Claude Code, project-local
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill --agent claude-code --copy --yes

# Codex, project-local
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill --agent codex --copy --yes

# Check installed skills
npx skills list
```

Use only the command matching your host. Add `--global` if you intentionally want shared instructions across projects; client data must still remain private and separate. Review an existing skill with the same name before replacing it. Reload/restart your host if needed for discovery. Installation does not automatically copy this repository's root `Skill_Agents.md` into your bot project.

### Instructions to give an LLM bot

```text
Install Bikram Cold Email Skill (bikram-cold-email-skill) from https://github.com/agarwalbikram/Cold-Email-Skill.
Read its README and Skill_Agents.md first. Use the Skills CLI from my private bot project, selecting
only bikram-cold-email-skill and your actual agent host. Preserve any existing skill and client
data; report a name conflict rather than overwriting it. Configure this dedicated
bot's persistent host instructions to load Skill_Agents.md (or merge its bot
instructions), resolving references from the installed skill directory. Preserve
unrelated host instructions. Verify discovery, then open a fresh conversation
with only "Hi" and confirm the skill loads and asks for client/first company
without writing invented facts or sending. Record the host configuration and
observed result; reading this file once is not persistent setup. If host access
or fresh-session verification is unavailable, report greeting setup as unverified.
Do not install MailWizz, add credentials, or send email.
```

The bot needs shell/file access and an Agent Skills-compatible host. An ordinary chat window can read instructions but cannot install files or provide persistent memory by itself. No single command makes every LLM platform discover skills.

### Manual install or uploaded repository

If the host does not support the CLI, copy the **entire** [`skills/bikram-cold-email-skill/`](skills/bikram-cold-email-skill/) directory into its documented skill directory, keeping the final directory named `bikram-cold-email-skill`. Examples of project-local destinations:

| Host | Destination |
| --- | --- |
| Claude Code | `.claude/skills/bikram-cold-email-skill/` |
| Codex | `.agents/skills/bikram-cold-email-skill/` |
| Other host | Its documented skill directory, ending in `bikram-cold-email-skill/` |

Do not copy just `SKILL.md`; `references/` and `assets/` are required resources. If uploading a ZIP to a host's skill importer, package the complete `bikram-cold-email-skill/` directory in the archive format that host accepts—not `.git/`, `.projectmem/`, or client data. A generic repository attachment does not necessarily install or activate a skill.

Without a skill loader, configure the host to load the entrypoint and its linked references explicitly. `SKILL.md` is the [standard discovery filename](https://agentskills.io/specification); **`bikram-cold-email-skill` is the name you invoke**.

## Tell your agent when to use it

Configure your dedicated bot host to load [Skill_Agents.md](Skill_Agents.md) explicitly as persistent bot instructions. This file is for the email bot, not for repository-maintenance coding agents. The custom filename is not automatically discovered. Preserve existing host instructions and merge the following routing rule rather than replacing unrelated instructions:

```text
For this dedicated client email bot, invoke the installed bikram-cold-email-skill skill by name
for greetings, onboarding, email drafts, variations, sequences, company/brand
corrections, MailWizz setup, and campaign tracking. Follow its bundled
references/agent-policy.md and references/workspace.md. Keep live client state in
this private project's client-data/, never inside installed skill files. Never
send, schedule, activate, or test-send without exact operation/version approval.
```

The repository's [Skill_Agents.md](Skill_Agents.md) routes by this same skill name and requires the complete client bot policy. The full runtime policy is also bundled inside the skill so it survives installation without relying on repository-root files. If copying Skill_Agents.md into a separate bot project, resolve its policy/workspace links from the installed `bikram-cold-email-skill` directory, not from the bot project's root.

Verify the host loads these instructions again in a fresh conversation with only **“Hi”**, without manually naming the skill. Use an empty synthetic private workspace for the check: expect a small client/first-company question batch, no invented saved facts, and no sending. Skill-file discovery and a one-time instruction read do not prove greeting activation. Do not claim this setup complete unless the actual host's persistent configuration and fresh-session behavior were observed.

## First use and JSON files

Start with **“Use bikram-cold-email-skill. Hi”**, or provide a complete brief:

> Use bikram-cold-email-skill. Write three email variations for our consulting offer to B2B agency owners. Use the attached approved product PDF. Draft only; do not send.

After the operator confirms the client identity and first company/brand in a private project, the bot uses available persistent file tools to create a missing `client-data/` directory and initialize both private JSON files from these blank templates for a new client. It saves only confirmed facts and verifies them with a fresh read before claiming success. A missing new-client profile is not a reason to refuse when file tools can create the storage; permission failures or unavailable tools must be reported with the exact path/error, without claiming a save. For an established client, a missing record is a recovery case: preserve remaining data and history and never reset from blank templates. A client profile holds one client catalog with multiple companies and brands; adding a company appends to that same profile and preserves existing companies, defaults, sources, and history. Persistent file tools are required for memory across conversations:

| Bundled template | Private working file | Purpose |
| --- | --- | --- |
| [`assets/client-profile.json`](skills/bikram-cold-email-skill/assets/client-profile.json) | `client-data/client-profile.json` | Client preferences and company/brand/niche/offer catalog |
| [`assets/campaigns.json`](skills/bikram-cold-email-skill/assets/campaigns.json) | `client-data/campaigns.json` | Versioned drafts, approval references, remote IDs, history, aggregate statistics |

These JSON documents contain empty catalogs and record templates, not real clients or JSON Schema validation rules. Never edit the installed templates to store client facts: reinstalling/updating a skill can replace its files. The bot creates `client-data/sources/` only when authorized documents are supplied. Follow [workspace setup](skills/bikram-cold-email-skill/references/workspace.md) for initialization, existing-data migration, and safe persistence.

In every consuming private project, ignore `client-data/` before use. This repository already includes that ignore rule. Git ignore does not protect tracked files or enforce access control. Keep each client's workspace and credentials separate; never publish client data, recipient lists, API keys, or campaign approval records.

Other example requests:

- “Use bikram-cold-email-skill. Update this brand's tone to concise and direct for future emails.”
- “Use bikram-cold-email-skill. Write a three-email sequence at days 0, 3, and 7. Draft only.”
- “Use bikram-cold-email-skill. Help configure the selected draft in MailWizz; show the final packet before approval.”
- “Use bikram-cold-email-skill. Show available aggregate stats for the campaign we saved.”

Missing persistent file tools must be reported; the bot must not pretend it saved memory. Missing MailWizz tools block remote operations, not a useful local draft. Approval and client isolation need enforcement by the host/tool gateway, not just prompts or JSON flags.

## Repository layout

```text
Skill_Agents.md                   # Explicitly loaded email-bot instructions
README.md                         # Installation and usage
skills/
  bikram-cold-email-skill/
    SKILL.md                      # Standard skill metadata and entrypoint
    assets/
      client-profile.json         # Blank profile template
      campaigns.json              # Blank campaign-register template
    references/                   # Bot policy, workspace, writing and MailWizz guides
    evals/
      evals.json                  # Behavioral evaluation prompts and expectations
```

`evals/evals.json` is a manual dataset with 68 cases, not an automated runner or proof of passed tests. Case 68 covers tags and footer across drafts, variants, steps and output formats; older case results retain their historical version, not evidence for current defaults. See the [evaluation guide](skills/bikram-cold-email-skill/evals/README.md) for recorded runs and limits. Recommendations stay provisional until accepted; draft feedback stays campaign-scoped unless made enduring. `.projectmem/` is maintainer memory, not a runtime dependency. Writing references originated from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/main/skills/cold-email).

## Updating

```bash
npx skills update bikram-cold-email-skill
```

Review upstream changes before accepting them. Keep private working files outside the installation so updates cannot replace client memory. Back up private data through an authorized client-scoped process; never upload it with this skill.
