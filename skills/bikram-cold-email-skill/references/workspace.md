# Skill Resources and Private Client Workspace

## Two locations, one source of truth each

- **Installed skill:** `bikram-cold-email-skill` (Bikram Cold Email Skill), containing instructions, `references/`, and blank JSON templates in `assets/`. Treat these resources as read-only. Resolve resource links from the installed skill, never from the current working directory.
- **Private client workspace:** a dedicated bot project with a `client-data/` directory containing the live `client-profile.json`, `campaigns.json`, and optional `sources/`. All unqualified runtime filenames in this skill refer to this private directory, not `assets/`.

Use one private bot project per client. A global skill installation may share instructions, never client state. If the host has not identified a stable private project, resolve it with the operator before saving; do not guess a directory from client names or document contents. Configure the host to use the same project across sessions.

## First use

1. Establish the client identity and private project. Keep `client-data/` excluded from version control before writing; an ignore rule does not remove files already tracked. Do not put client data in the public skill repository.
2. Inspect existing storage before creating anything. If private JSON exists, read and validate it; never replace it with a template. A malformed file requires recovery, not reset.
3. For a genuinely new client only, copy [client-profile.json](../assets/client-profile.json) and [campaigns.json](../assets/campaigns.json) into `client-data/` using create-only writes. Fill only confirmed client facts. The templates are JSON document shapes, not JSON Schema validators or actual customer records.
4. Bind both documents to the same established client ID before saving campaigns. Keep unknown facts null and catalogs/registers empty until real records exist. Do not copy sample/template records into real arrays without onboarding facts.
5. Create `client-data/sources/` only when authorized materials are supplied. Keep credentials in the host's secret store, not these files. Apply the safe update/revision rules in [client-workflow.md](client-workflow.md).

Installation alone must not create client data, install MailWizz, connect credentials, or authorize a campaign. If persistent tools are unavailable, draft from the supplied brief and state that requirements were not saved. Never claim durable onboarding or tracking from chat history alone.

## Host boundaries

Restrict all client reads/writes to this private workspace; reject traversal, external absolute paths, and symlink escapes. Exclude data from Git and backups shared with other clients; `.gitignore` is not access control. Keep host permissions and MailWizz resource authorization client-scoped. Prompts and JSON alone cannot enforce isolation or approval.
