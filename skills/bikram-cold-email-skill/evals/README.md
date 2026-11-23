# Evaluations

`evals.json` holds 36 manual scenarios. Each has an `area`, a `prompt`, the `expected_output`, checkable `assertions` and optional fixture `files`. It is a dataset, not a test runner: a case passes only after someone runs it against the installed skill, inspects the reply and the file/host trace, and records the result outside this folder.

| Area | Cases | What it checks |
| --- | --- | --- |
| writing | 1–8 | First touch, sequence, humanizer rewrite, style reference, exact copy, subject-only, variations |
| research | 9–11 | URL research coverage, blocked site, multi-product site |
| memory | 12–18 | Onboarding, returning greeting, scoped correction, malformed file, second company, draft-only edit, lasting preference |
| scope | 19–20 | Brand picker, duplicate company names |
| conversation | 21–23 | First "Hi", multi-turn recovery and rewrite, "too short" |
| modes | 24–25 | Affiliate promotion, ClickBank health claim |
| mailwizz | 26–31 | Setup flow, version-bound approval, save failure after schedule, server set, missing reply-stop, deadline |
| reporting | 32–33 | Stats table with denominators, stale snapshot |
| replies | 34–35 | Pricing question, unsubscribe with limited tools |
| safety | 36 | Instructions hidden in a source document |

Writing cases are the ones to run first after any change to `writing.md` or `humanizer.md`. Score them by reading the email as the recipient would, not only by ticking assertions.

## Running a case

1. Make a fresh scratch project under the repo's ignored `.tmp/`, e.g. `.tmp/eval-14/`, with an empty `client-data/`.
2. Copy the case's fixtures in:

| Fixture | Copy to `client-data/` as |
| --- | --- |
| `onboarding-profile.json` | `client-profile.json` (same as the blank template) |
| `empty-campaigns.json` | `campaigns.json` (same as the blank template) |
| `two-brand-profile.json` | `client-profile.json` |
| `two-brand-campaigns.json` | `campaigns.json` |
| `price-correction-campaigns.json` | `campaigns.json` |
| `approved-campaign-register.json` | `campaigns.json` |
| `malformed-profile.txt` | `client-profile.json` (copy bytes exactly) |
| `post-schedule-save-failure.txt` | Not copied. Give it to the bot as host evidence |

3. Send the `prompt`. No MailWizz, no real accounts, no sending. "Verified operator" means the synthetic `fixture:verified-operator` identity only.
4. Inspect the files after the run. Never trust the bot's own "saved" claim. For case 15, compare file bytes before and after.
5. Never reuse a scratch directory or edit fixtures.

Fixtures use `.example` domains and synthetic IDs. They contain no real client data or credentials.
