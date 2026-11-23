# Bikram Cold Email Skill

An Agent Skill (`bikram-cold-email-skill`) that turns an LLM bot into a dedicated email assistant for one client:

- Writes cold emails, variations and sequences that read like a person wrote them. Every draft goes through a built-in **humanizer pass** (adapted from [blader/humanizer](https://github.com/blader/humanizer), MIT) that strips AI-writing tells.
- Researches a supplied product/company URL and recommends who to email, with sources.
- Remembers the client's companies, brands, offers and style in private JSON files.
- Sets up MailWizz campaigns only after the operator approves the exact final version, then reports stats with suggestions.
- Supports own-product, affiliate and ClickBank offers.

It supplies instructions and blank data templates. It is not a running bot, mail server or MCP server. Drafting needs no MailWizz; sending needs a MailWizz MCP connection configured in your host.

## Layout

```text
Skill_Agents.md                     # Persistent instructions for the email bot
skills/bikram-cold-email-skill/
  SKILL.md                          # Entrypoint: flow, non-negotiables, output format
  references/
    workflow.md                     # Data, routing, scope, memory, URL research, setup, approval
    writing.md                      # Brief → body → subject → tags/footer → review → feedback
    humanizer.md                    # AI-tell removal pass for every draft
    campaign-modes.md               # Own-product / affiliate / ClickBank rules
    mailwizz.md                     # Scheduling checks, reporting, replies, suppression
  assets/                           # Blank client-profile.json and campaigns.json templates
  evals/                            # 36 manual scenarios + synthetic fixtures
```

## Install

Run from the private project your bot works in (Node.js 22.20+ and Git required):

```bash
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill
# non-interactive examples
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill --agent claude-code --copy --yes
npx skills add agarwalbikram/Cold-Email-Skill --skill bikram-cold-email-skill --agent codex --copy --yes
```

Manual install: copy the whole `skills/bikram-cold-email-skill/` folder into your host's skill directory (e.g. `.claude/skills/` or `.agents/skills/`), keeping the folder name. `SKILL.md` alone is not enough.

## Give the bot its instructions

Load [Skill_Agents.md](Skill_Agents.md) as the bot's persistent system instructions (merge it with any existing ones). Installing the skill does not do this for you.

Then check it: open a fresh conversation, send only **"Hi"**. The bot should ask for the company or website, invent nothing and send nothing.

## Client data

On first use the bot creates `client-data/` in your private project with `client-profile.json` and `campaigns.json` copied from the templates. Add `client-data/` to that project's `.gitignore`. One project per client; never commit or share it. Updating the skill never touches these files.

## Example requests

- "Hi"
- "https://example.com — who should we email?"
- "Write three variations for brand X to retail store owners. Draft only."
- "Write a 3-email sequence at days 0, 3, 7."
- "This sounds like AI, rewrite it."
- "Always use a casual tone for this brand."
- "Set the approved draft up in MailWizz."
- "Show stats for the spring campaign."

## Update

```bash
npx skills update bikram-cold-email-skill
```

Writing references originally derived from [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills/tree/main/skills/cold-email).
