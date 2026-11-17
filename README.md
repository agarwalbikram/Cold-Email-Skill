# Agent Instructions: Install or Update the Client Email Skill

Use this file as the installation brief for another agent. **Install the customized package shipped beside this file, not the original upstream cold-email skill.** Do not send email, initialize a client with invented facts, or activate MailWizz campaigns during installation.

## Operator handoff

You may point an agent at this file with:

> Read GIT-INSTRUCTIONS.md and install this customized cold-email skill for my dedicated client bot. Inspect the bot's existing host configuration first. Use one private, persistent, writable deployment per client; preserve existing client data and other instructions. Verify discovery and a no-send greeting smoke test. Report installed paths, source revision, MailWizz capability gaps, and any approval-gateway blocker. Do not schedule, activate, send tests, or modify infrastructure.

This is a generic host-aware procedure, not a universal one-command installer. If the host, target client workspace, authorized source repository/revision, or permission to modify the target cannot be determined from the supplied project/configuration, ask only for that missing decision. Do not guess a GitHub URL or an installation path.

## 1. Identify the source and destination

1. Read the source [SKILL.md](cold-email/SKILL.md), [AGENTS.md](cold-email/AGENTS.md), and [bot-flow.md](cold-email/references/bot-flow.md) before installing. Respect the target project's existing instructions and security boundaries.
2. Prefer the supplied local checkout when it contains this customized package. Record its exact path and Git commit if available. A downloaded folder without Git metadata is a valid local source: record a content digest/version instead; do not initialize or publish a repository just to install it.
3. For a remote source, use the operator's repository containing **this customized package**, verify its owner/path and an approved commit or immutable release, and obtain it in project-local staging. The original `coreyhaines31/marketingskills` repository will not contain this client's custom memory, guided setup, or campaign register changes. Never substitute it silently.
4. Inspect the actual bot host's documented skill discovery and instruction-loading mechanism. Prefer its project/bot-local skill location, not a global shared install. A host may use a path such as `.claude/skills/cold-email/` or `.agents/skills/cold-email/`, but these are examples, not permission to assume compatibility. If external skill paths are supported, a dedicated private folder is also acceptable.
5. Choose exactly one canonical installed package per client with the directory name `cold-email` and a `SKILL.md` entry point. All relative references and both JSON files stay together. Never run several clients from one writable skill folder or use a shared symlink/hardlink for client state. Do not run the live bot in the Git staging/source checkout.
6. Use a persistent writable private client workspace for the full deployed package. If the host only supports shared or read-only skills, do not pretend in-folder JSON memory will work: use an explicitly configured per-client private deployment if supported, otherwise report the host incompatibility and leave scheduling disabled.

### Optional Git acquisition commands

Use only when a remote source is needed and Git is already available. Resolve all four variables first: `REPO_URL` is the approved customized repository, `APPROVED_COMMIT` its verified full commit ID, `PROJECT_ROOT` the authorized project, and `SOURCE_DIR` a new directory under that project's `.tmp/` staging area. Do not overwrite an existing checkout or put a live client there. Use the project's established scratch directory if it differs.

```bash
: "${REPO_URL:?Set the approved customized repository URL}"
: "${APPROVED_COMMIT:?Set the approved full commit ID}"
: "${PROJECT_ROOT:?Set the authorized project root}"
: "${SOURCE_DIR:?Set a new project-local staging directory}"
git clone --no-checkout -- "$REPO_URL" "$SOURCE_DIR"
git -C "$SOURCE_DIR" checkout --detach "$APPROVED_COMMIT"
git -C "$SOURCE_DIR" rev-parse HEAD
```

Validate destination containment and source identity before executing; the variable checks only reject unset values, not unsafe paths. Create any required parent staging directory inside the project first. Do not use credentials in URLs, run repository-provided setup scripts, initialize submodules, install dependencies, or execute remote code to copy this Markdown/JSON package. If the approved commit is unavailable, report it rather than installing the current branch tip. Network/git acquisition needs its own operator authorization where the environment requires it.

## 2. Separate release content from private runtime state

The source distribution has empty JSON starter files. A client deployment will populate them and must keep them private.

| Release content: install/update after review | Client state: initialize once, preserve thereafter |
|---|---|
| `SKILL.md`, `AGENTS.md`, `references/`, `evals/` | `client-profile.json`, `campaigns.json`, client `sources/`, any legacy campaign records, private recovery copies and history |

- The release's client-profile.json and campaigns.json must be empty starter templates, not another client's populated data. Inspect identity/catalog/register values before a fresh copy. If they contain real client data, stop and request a sanitized release; do not copy it into a new client's bot.
- Keep credentials in the host's approved secret/MCP storage, not in these JSON files or the Git source. Client identifiers and resource allowlists in JSON are metadata, not authenticated credentials or enforced isolation.
- Configure the **target workspace's** Git ignores or private untracked runtime location for the installed client's JSON files, sources and backups before onboarding. Preserve existing ignore rules. Check the exact paths are not already tracked: ignore rules do not untrack files. If they are tracked, report it and obtain authorization for the appropriate repository cleanup; never delete history or run `git rm` automatically.
- Do not add a broad `*.json` ignore that would hide unrelated project files. Empty templates in the release may remain versioned; populated live client files must not be pushed in that release.
- Do not initialize, commit, push, or publish a repository as part of this installation. Before any later redistribution, check attribution/license obligations and confirm the package is sanitized.

## 3. Fresh installation

1. Confirm the canonical destination does not already contain a deployed client package or user data. If it exists, treat this as an update, not a fresh install. An unreadable or malformed profile/register is not permission to reset it.
2. Copy the complete reviewed `cold-email/` folder into the resolved private destination, including all reference files, evals and the two **empty** JSON starter templates. Do not copy `.git/`, staging artifacts, another client's sources, credentials or histories. Use a safe filesystem copy that neither follows untrusted links outside the source nor replaces unrelated files.
3. Retain `name: cold-email` and the current compatible frontmatter. Do not add host-only substitutions or change relative references without migrating every consumer.
4. Configure the host to discover this SKILL.md **and explicitly load this package's AGENTS.md for the dedicated bot**, especially on a bare greeting. Skill discovery by task description alone may not load a skill when the user only says "Hi."
5. If a root bot instruction entry must reference the nested AGENTS.md, add a scoped reference using the host's documented mechanism. Preserve existing instructions, never overwrite an existing root AGENTS.md, and do not assume that links automatically execute/load instructions.
6. Configure the host to resolve profile/register/source paths relative to the installed package directory, not an arbitrary process working directory. Grant persistent writes only to this client's authorized storage. Prevent other client bots from reading it.
7. Leave starter identity fields null and arrays empty. On the first greeting, let the bot collect client/company facts and persist operator-confirmed answers. Do not convert templates into fictitious live companies or mark any approval complete.

## 4. MailWizz and execution gates

Installation does not require MailWizz to be connected. Without it, the bot can onboard, remember requirements and draft locally if the host provides file tools.

If an existing approved MailWizz MCP connection is available:

- Discover its actual schemas with authorized read-only operations. Verify client/account ownership and gateway resource scopes before listing lists, segments or delivery servers. No available connection is permission to read every account.
- Bind verified permitted resources through the authorized host/operator configuration. Empty profile allowlists remain deny-by-default; never populate them by copying every visible ID. Record capability evidence and timestamps honestly.
- Verify whether regular/autoresponder create/draft/schedule/disable, segment and delivery-server selection/readback, statistics, suppression and reply-aware stopping are actually supported. API documentation alone is not MCP coverage.
- Do not install a new MCP server, request raw API keys in chat, edit secrets/configuration, grant wider permissions or create a campaign without a separate explicit request and authorized procedure. Report missing capabilities; do not substitute another sender or direct API calls.
- Scheduling requires a host/gateway-enforced authenticated approval check for the exact campaign/version, client resources and approved time or bounded enrollment policy. Prompt instructions and editable JSON are not that control. If the host cannot enforce it, report the deployment as **draft-only** and keep schedule/activation execution blocked.
- No real sends, test messages, imports, autoresponder activation or protective pause checks against live campaigns during installation. An approved future production campaign is not an installation test fixture.

## 5. Safe updates

1. Verify the currently installed client identity, register ownership, schema versions and selected source revision. Pause bot **file writers/jobs locally** through authorized host controls before replacing instructions; this does not pause remote MailWizz sends. Report existing remote activity without altering it unless separately authorized.
2. Make an authorized recoverable private backup inside the client workspace, including JSON files, sources and original instructions. Backups need the same access/privacy controls as live data. Record content digests of existing client state and client-specific instruction overrides; do not log file contents or secrets.
3. Review the new release in staging. Replace only reviewed release-owned files; preserve operator overrides by merging them deliberately. Never blanket-copy the entire folder over a populated deployment, force-reset it, clean it, or use a sync/delete operation that can erase client state.
4. **Never replace existing client-profile.json or campaigns.json with release starter files.** Additive schema/template additions may be merged only with validated preservation of live data. Unknown schema versions or incompatible changes block the update until an explicit migration and recoverable backup are approved. Preserve stable IDs, approval/event references and remote campaign IDs; migration cannot grant new approval.
5. Preserve old per-campaign records until an authorized validated migration has moved them into campaigns.json without loss. Resolve duplicate IDs and designate one active source of truth; do not keep the bot silently writing to both formats.
6. After copying, verify existing private state digests are unchanged unless an authorized migration explains every difference. Confirm client-specific overrides and host instruction loading remain effective. If a check fails, stop and use the authorized backup rollback for local files; never compensate by resending or recreating remote campaigns.
7. Re-run the no-send checks below and report the installed source revision and preserved client identity. Restart only the authorized local bot jobs. An update is not approval to resume remote sends or change scheduled material.

## 6. No-send acceptance checks

Use the target host's real interface/tools where available; report any untested layer explicitly.

- Every installed reference link resolves; frontmatter has usable name/description; JSON parses and schema versions are supported. Fresh templates remain empty. On update, existing companies, corrections, campaigns and remote IDs remain intact.
- The host discovers one cold-email skill, actually loads the dedicated AGENTS.md on greeting, and resolves writable JSON paths to this private installed directory. Do not claim instruction loading from file existence alone.
- Fresh simulated greeting: asks client/first company in a small batch. Returning greeting: offers relevant create/add/update/continue/track choices, without choosing an ambiguous brand or resuming sends.
- Using synthetic data in an isolated test workspace—not live client records—verify a lasting scoped correction survives a fresh conversation/profile read and preserves sibling brands. A local copy edit must not change a saved default without instruction.
- Guided setup: actual authorized list/segment choices when MCP is available; regular/autoresponder distinction; frozen authorized server selection; zero-delay/existing-contact and expiry safeguards; final approval before any execution. Do not mutate MailWizz for this check.
- Approval-denial smoke check must be host/gateway-level or a safe dry run: setup yes, stale approval, changed audience/server, foreign client resources, and unsupported required controls cannot reach a real schedule/send operation. If it cannot be safely verified, label it unverified and keep execution disabled.
- Tracking simulation: saved remote IDs resolve, unavailable metrics stay null, stale snapshots are labeled, and a failed local post-operation save does not cause duplicate creation. Do not turn tracking on or promise background monitoring.

Report: canonical install path; exact source commit/digest and skill version; host discovery/instruction-loading evidence; private memory/register paths; preserved state on updates; MailWizz read-only capability evidence; checks actually run; and any draft-only or execution-gate blocker. Mark installation complete only for layers actually verified.
