# Evaluations

`evals.json` holds 70 manual scenarios: prompts, expected behavior, assertions and fixture links. It is a dataset, not a test runner or a record of passes. A case counts as passed only after someone runs it against the installed skill, inspects the reply and file/host trace, and records the result outside this folder.

| Cases | Area |
| --- | --- |
| 1–11, 29–30, 36–44, 48–50, 61, 65–66, 68–70 | Writing, subjects, tags/footer, humanizer pass, reports, replies |
| 12–28, 51–57 | Scope pickers, memory vs draft edits, MailWizz setup, approval, autoresponders |
| 31–35, 45–47 | File-backed persistence: onboarding, returning greeting, corrections, malformed file, save failure |
| 58–60, 67 | Multi-turn conversation replays |
| 62–64 | URL research coverage and recipient recommendations |

Case 69 is the humanizer regression: an AI-sounding draft must come back as one natural email with every listed tell removed and the offer/CTA unchanged.

## Isolation setup

Run only in a fresh, disposable project-local scratch workspace. For each individual scenario, make a new empty directory named `client-data/` under a dedicated scratch project inside the repository's ignored `.tmp/` directory (for example `.tmp/eval-31/client-data/`). Do not point the host at a real client project, shared workspace, installed skill `assets/`, or live MailWizz account. Confirm `.tmp/` is excluded from version control before putting files there. Do not enable MCP, remote integrations, scheduling, or sending; the synthetic operator identity is fixture-only and grants no real authority.

For each case, copy only its listed fixture files into the fresh `client-data/` directory, using this exact mapping:

| Fixture | Destination in scratch `client-data/` |
| --- | --- |
| `fixtures/onboarding-profile.json` | `client-profile.json` |
| `fixtures/empty-campaigns.json` | `campaigns.json` |
| `fixtures/two-brand-profile.json` | `client-profile.json` |
| `fixtures/two-brand-campaigns.json` | `campaigns.json` |
| `fixtures/price-correction-campaigns.json` | `campaigns.json` |
| `fixtures/approved-campaign-register.json` | `campaigns.json` |
| `fixtures/malformed-profile.txt` | `client-profile.json` (copy bytes exactly; keep the `.txt` source extension only in the eval fixture) |
| `fixtures/post-schedule-save-failure.txt` | Host evidence input only; do not install as client JSON |

The files in `files[]` are evidence/input links, not destination paths or instructions to overwrite a fixture in place. For case 33, copy `two-brand-profile.json` to `client-profile.json` and `price-correction-campaigns.json` to `campaigns.json`. For case 35, copy `approved-campaign-register.json` to `campaigns.json` and provide the host evidence file read-only to the simulated operator. The register contains the approved pending operation saved before the remote action; it does not claim that the post-schedule result was persisted. For case 34, preserve the malformed source bytes and compare the destination bytes to the fixture before and after. Never reuse a scratch directory between cases; never edit fixtures as part of scenario execution.

## Operator identity assumption

Prompts that say “verified operator” assume the isolated harness presents a synthetic identity reference, `fixture:verified-operator`, for test context only. It is not authentication, a credential, or production approval. No actual operator identity, client, account, MailWizz resource, or send authorization is represented. Case 35's host evidence is synthetic and does not authorize contacting a remote service.

## Scenario runs and observable checks

Execute each case independently by supplying its `prompt` and fixture inputs to the skill in an offline local-file harness. Record the response and observed file/host trace outside the fixture dataset as the run result. Do not infer successful writes from an assistant's statement: inspect the files.

- **31 — onboarding:** initialize from the profile fixture. Confirm the saved profile has a stable synthetic client ID/name and one confirmed company and brand, revision advances only after successful persistence, and unknown data remains null. Confirm `campaigns.json` still has `"campaigns": []`; approval remains required, standing send authorization false, tracking off. Trace contains no remote calls, send, or schedule.
- **32 — returning greeting:** initialize from the two-brand profile and register. Confirm response greets Cedar Lantern Studio and offers relevant returning-client actions without choosing Cedar Lantern or Cedar Lantern Home. Compare both files byte-for-byte before/after; trace shows fresh local reads only and no writes or remote calls.
- **33 — durable price correction:** initialize with the two-brand profile and the price-correction register. Confirm only `syn-offer-starter` changes from `$29/month` to `$39/month`; `syn-brand-cedar-home` and its `$49/month` sibling offer are unchanged. Check the change record includes timestamp, operator event reference, record ID, changed field, old/new values, reason and resulting profile revision. Check profile revision increments and a fresh process/read sees `$39/month`. The campaign register and remote trace remain unchanged; no remote sends/mutations.
- **34 — malformed profile:** copy the malformed `.txt` fixture bytes to `client-profile.json`. Confirm the response reports malformed JSON, the destination bytes/hash exactly match the pre-run copy, and no replacement, template reset, or write occurs. No campaign/register mutation or remote action.
- **35 — post-schedule save failure:** start from `approved-campaign-register.json` and supply the synthetic host evidence. Confirm the response reports UID `SYNTH-MW-UID-735`, the last observed scheduled state, and the failed local save; it must not claim a current remote readback or successful local persistence. With no connected reconciliation tool, leave the register unchanged, halt mutations, and request authorized readback before retry or recovery. Trace contains no duplicate create/schedule. The supplied host evidence is not a live readback.

The template-shaped JSON fixtures intentionally use reserved `.example` URLs and synthetic IDs/names. They contain no real client data or credentials. Keep test outputs and scratch data local and disposable; do not publish a run result as a dataset change.
