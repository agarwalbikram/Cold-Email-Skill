# projectmem - Cold Email Skill

_Last updated: 2026-11-17_

## Project purpose
Replace this placeholder with a concise description of what this project does, who it serves, and the main technologies or runtime assumptions.

## Recent issues
- [DONE] #0002 Pull left main in an unresolved add/add README merge after local packaging commit [README.md] (fixed)
- [DONE] #0001 Skill installation lacks README and agent routing; agent links and client workspace paths are broken [Skills_AGENTS.md] (fixed)

## Decisions
- Publish one portable cold-email skill under skills/cold-email/ with references and blank JSON templates in assets/. Keep private runtime data in client-data/ outside installed skill files; root AGENTS.md routes by skill name. [skills/cold-email/]
- Refactor: refactor: rename to Bikram Cold Email Skill [skills/bikram-cold-email-skill/assets/campaigns.json]
- Root Skill_Agents.md is explicitly loaded email-bot guidance, not coding-agent instructions. Renamed from AGENTS.md and removed repository-maintenance section. README documents explicit host loading and installed-resource resolution. Local filename/link checks pass; not yet published. [Skill_Agents.md]
- Approved improvement scope: persistent host greeting-load evidence, explicit action-specific approval for replies/calendar/reminders, five file-backed persistence evals, and deletion of obsolete deployment guidance. Keep all client/send boundaries; no live sends or automatic publication. [skills/bikram-cold-email-skill/]
- Clarified campaign scope: no infrastructure/deliverability audits or DNS/seed proof launch gate; report MCP-exposed metrics/status read-only with unknowns distinct from zero; preserve tracking unless explicitly approved, then read back. Updated owned agent guidance and eval dataset/cases.
- User scope: client/brand email and sequence writing, approved MailWizz create/schedule, on-request status/opens/clicks/unsubs/bounces plus suggestions. Remove infrastructure audits/booking duties. Tracking defaults off but explicit approved choices allowed; reports read-only, missing != zero. [skills/bikram-cold-email-skill/]

## Notes
- Compared original 3d47d37 cold-email/AGENTS.md: bundled agent-policy preserves all 8 request steps except private-profile path; persistent-file and safety sections identical. Root now mandates loading full policy; removed recursive invocation and README rename section. Published f89e8ff; 73... [AGENTS.md]
- Committed Skill_Agents.md handoff/README as 343f15b (not pushed). Read-only review suggests clearer greeting-load handoff, fixture-backed evaluations (30 cases, no attached files), and harmonized reply/booking approval wording. No improvement edits authorized or made. [Skill_Agents.md]
- Eval cases 31–35 use offline synthetic fixtures; copy each files[] input into a fresh .tmp/<case>/client-data/ with explicit profile/register mapping. Fixtures are datasets, never run results; no MCP or live send is authorized.
- Case 35 requires the local register to represent the persisted pre-mutation approved campaign; a blank register would contradict the required save-before-remote-operation workflow.
- High churn detected: skills\bikram-cold-email-skill\evals\README.md (4 edits in 10 min) [skills\bikram-cold-email-skill\evals\README.md]
- Implemented approved four improvements. Dataset 35 cases/5 file-backed; 6 JSON fixtures valid, malformed fixture rejected, 75 links pass. Offline file-tool smoke verified onboarding, scoped correction+history, unchanged greeting/malformed/recovery records. Approval wording review passed; live... [skills/bikram-cold-email-skill/evals/]
- Read-only upstream comparison: core voice rules retained; custom prewriting lost explicit why-this-prospect/proof/signal brief, adds workflow-first routing and mandatory metadata. Quality impact remains a hypothesis: no paired outputs or host traces supplied. No skill edits. [skills/bikram-cold-email-skill/SKILL.md]
- High churn detected: skills\bikram-cold-email-skill\evals\evals.json (4 edits in 10 min) [skills\bikram-cold-email-skill\evals\evals.json]
- Scope cleanup v3.4.0: replaced infra guide with copy-quality; removed booking playbook; approved tracking choices + read-only metrics/suggestions. 9 JSON/40 IDs/79 links pass. Two offline reporting generations correct; independent boundary review passed. Live MCP untested, no commit. [skills/bikram-cold-email-skill/]
- Rewrote 13 framework sections with evidence-scoped examples, no default PAS, no invented named-brand results, no-proof and affiliate modes; aligned SKILL shapes and added cases 41-42. 9 JSON/42 IDs/81 links pass. Two offline drafts avoided fabricated proof; live performance unmeasured. [skills/bikram-cold-email-skill/references/frameworks.md]

## Key files
- `.gitattributes`
- `AGENTS.md`
- `1.9.0`
- `skills/cold-email/SKILL.md`
- `cold-email/AGENTS.md`
- `README.md`
- `v3.3.0`
- `skills/bikram-cold-email-skill/assets/campaigns.json`
- `skills/bikram-cold-email-skill/SKILL.md`
- `skills/bikram-cold-email-skill/assets/client-profile.json`
- `skills/bikram-cold-email-skill/evals/evals.json`
- `skills/bikram-cold-email-skill/references/agent-policy.md`
- `skills/bikram-cold-email-skill/references/benchmarks.md`
- `skills/bikram-cold-email-skill/references/bot-flow.md`
- `skills/bikram-cold-email-skill/references/campaign-modes.md`
- `SKILL.md`
- `Skill_Agents.md`
- `skills\bikram-cold-email-skill\evals\README.md`
- `skills\bikram-cold-email-skill\evals\evals.json`
- `evals.json`

## Open questions
- None logged yet.
