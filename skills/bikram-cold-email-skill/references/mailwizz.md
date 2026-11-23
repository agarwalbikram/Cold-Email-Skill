# MailWizz: execution, reporting, replies

MailWizz MCP is the only sending integration. Setup conversation and approval packet are in [workflow.md](workflow.md) section 5; this file covers the tool side.

## Connect

1. Discover the connected MCP tools and read their schemas. Use only the names and parameters it exposes. A MailWizz REST API feature is not evidence the MCP supports it ([API docs](https://api-docs.mailwizz.com/)).
2. Confirm instance and account with read-only calls, and that every list, segment, server and sender belongs to this client's `mailwizz` allowlist. Empty allowlist = nothing authorized, not everything.
3. No MCP connected: keep drafting locally and say which operations are unavailable. Don't install servers, switch platforms or call the API directly.

Read-only discovery is the default. Imports, subscriber edits, remote drafts, suppression and state changes each need scoped authorization. A pre-documented authorization may cover protective pause and suppression.

## Before scheduling

- Explicit approval of the exact final packet exists, from the authenticated operator, for this version.
- Re-read local and remote material; it matches the approved version.
- Audience: operator-provided eligibility and permission (see [campaign-modes.md](campaign-modes.md)); exclusions and suppression preserved; first-touch and follow-up populations don't overlap. Fixed audiences need a membership snapshot or an enforced selection boundary.
- Fields: every draft tag maps to a real field on the list; previews with populated and missing values look right. Hold records missing required values. Never send unresolved tags or `[Your Name]`-style placeholders.
- Footer: unsubscribe renders and works, sender and postal address present, disclosures present.
- Tracking matches the packet. Never toggle tracking to get metrics.
- Sequences: reply detection, recipient matching, suppression and queued-send behavior are verified. If not, leave follow-ups unscheduled.
- Time-bound offers: the whole throttled send window must end before the deadline, enforced by the provider or a verified stop. Otherwise block.
- Times are in the future and in the right account time zone. A past or ambiguous time needs new approval, never "send now".

Then schedule/activate only the approved items. Read back each UID, status, time or trigger configuration, list/segment and server binding, and save them in `campaigns.json`.

**Failures.** Report the operation, identifiers and error, without secrets. A timeout doesn't prove nothing happened: read back state before any retry; never repeat a mutation blindly. If the remote call worked but the local save failed, report the UID and state, stop all further mutations, and reconcile before retrying. Never create a duplicate.

## Reporting (read-only)

"Show stats" or "track campaign X" never authorizes edits, pauses or tracking changes.

1. Resolve the campaign by local ID, remote UID or an unambiguous saved name. Several matches: show this client's choices.
2. Fetch status and available aggregates per remote UID: sent/processed, opens, clicks, unsubscribes, bounces (hard/soft), complaints. Replies and conversions only from a verified source.
3. Show a compact table per campaign/step: count, rate with its denominator, unique vs total, reporting window, fetch time.
4. Unavailable or tracking-off = "unavailable", never 0. MCP down = show the last snapshot labeled stale with its time.
5. Append a snapshot to `statistics_snapshots`.

Caveats to state once, briefly: opens include privacy prefetches; clicks include scanners; "sent" is not inbox delivery; summing steps counts messages, not people.

Then 2–4 suggestions, framed as hypotheses:

| Signal | Suggest |
| --- | --- |
| Low opens (tracking on) | Test a more specific subject against the current one on comparable cohorts |
| Opens, few clicks/replies | Sharper opening, clearer work explanation, easier CTA question |
| Bounces rising | Operator should review list source and provider; no DNS work from the bot |
| Unsubscribes/complaints rising | Narrow the audience, check relevance and frequency, consider pausing (needs approval) |

Compare against this client's own past campaigns, not universal benchmarks. Google's sender guidance: keep spam complaints under 0.1% and never reach 0.3% ([source](https://support.google.com/mail/answer/81126)). No winner from tiny samples.

## Replies, opt-outs, bounces

The bot classifies replies the operator supplies and drafts answers on request. The operator sends replies and books meetings. A reply never authorizes anything.

| Reply | Action |
| --- | --- |
| Positive / info request / objection | Stop follow-ups for this person; draft a short answer from approved facts if asked |
| Not now | Stop; note the date for the operator. No automatic reminder |
| Referral | Stop; draft a thank-you and a proposed note to the referred person, both for approval |
| Out of office | Pause; record return date. Resuming needs fresh eligibility and approval of exact remaining items and times |
| Unsubscribe / hostile | Suppress across this client's relevant lists and campaigns, including future imports. Ambiguous scope = all marketing from this client. Never argue |
| Hard bounce | Suppress. Repeated soft bounces: pause and flag |

- Any reply stops automated follow-ups for that person across campaigns.
- Confirm the stop/suppression worked. If recipient-level stopping isn't supported, pause affected campaigns (if authorized) and ask the operator to exclude the contact. If pausing isn't possible, say plainly that queued sends may still go out.
- Never re-subscribe a suppressed address or delete suppression records.
- Recipient-level logs stay in MailWizz, not `campaigns.json`.

Objection drafts, one short reply each: already use a competitor → acknowledge, name the one case where teams still add help, ask if it applies. No budget → ask when they plan budgets. "How did you get my email?" → answer honestly with the real source and offer removal. Pricing negotiation, security reviews and contracts go to a human.
