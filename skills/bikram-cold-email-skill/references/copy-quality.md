# Email Copy Quality and Campaign Signals

This skill writes brand-specific cold emails and sequences, creates/schedules approved MailWizz campaigns, and interprets available campaign statistics on request. It does not inspect received emails, run inbox-placement tests, audit DNS/authentication or IP reputation, manage warmup, or configure sending infrastructure. Those are the operator/provider's responsibility, not extra bot onboarding questions or a requirement to upload audit evidence before drafting or scheduling.

## Review the copy before presenting it

- Match the selected brand, audience, offer, language and requested format. Lead with a relevant problem or benefit, not a company introduction.
- Use a short, honest subject and an opening that delivers on it. Avoid fake Re:/Fwd:, account warnings, invented prior contact and misleading sender names.
- Use plain language, one useful idea and one clear CTA. For B2B cold first touches, start around 25–75 body words; required footer/disclosures are separate. Permission-based promotions can use an approved offer link and appropriate promotional wording under [campaign-modes.md](campaign-modes.md).
- Remove filler, repeated pitches, excessive capitals/punctuation, fabricated urgency and unsupported guarantees. Words such as "free", "discount" and accurate prices are not automatically banned; review meaning and evidence, not an arbitrary keyword score.
- Never disguise words with symbols, invisible characters or random spintax to evade filters. No wording guarantees inbox placement or an open-rate lift.
- Keep sender identity, affiliate disclosures, truthful terms, postal address and required opt-out/unsubscribe content intact. Avoid shorteners and unnecessary links or attachments; do not remove compliance links.
- Preview available MailWizz fields and missing-value fallbacks before scheduling. Never send unresolved tags, editorial notes or invented recipient facts.
- Each follow-up adds a new relevant angle, fact or resource; stop rules remain part of the approved sequence.

## Campaign setup boundary

Use the selected authorized MailWizz list/segment, sender and existing delivery-server choices. Confirm operator-provided eligibility and sending limits; preserve exclusions and approved timing. Do not claim independent verification of list quality, provider acceptance or infrastructure health. A known prohibition or invalid audience remains a blocker; unavailable infrastructure diagnostics alone are not a new launch gate.

Open/click tracking defaults to off in the blank templates, not a permanent prohibition. Reuse stored preferences as proposals and confirm the operator's choice in the final packet. Enable or change tracking only when explicitly included in the approved campaign/version and supported by MCP; read back the actual settings. Preserve existing campaign settings during reports. Do not enable tracking merely to populate missing metrics. See [mailwizz-mcp.md](mailwizz-mcp.md).

## Interpret statistics, then suggest

Use actual MailWizz MCP data or clearly attributed operator reports, not inferred inbox outcomes. Report current status, sent/processed counts, available opens/clicks, unsubscribes, bounces and complaints, with reporting time and definitions. Include replies/conversions only from a verified source. Missing or disabled tracking means unavailable, not zero. Sent/accepted is not inbox placement; opens can include privacy prefetches and clicks can include security scanners.

| Observed signal | Suggested next step, not a proven diagnosis |
|-----------------|-------------------------------------------|
| Low reported opens | Check tracking availability and sample/window first; propose a more relevant subject/opening and comparable subject test. Do not claim spam placement or a subject failure from opens alone |
| Opens but few clicks | If a link CTA was intended, review benefit, body/subject agreement and the approved destination. A reply-first email may not need clicks |
| Rising bounces or delivery errors | Show available hard/soft/error breakdown and recommend operator review of the audience or delivery provider; do not fix DNS, replace servers or prescribe mailbox multiplication |
| Rising unsubscribes or complaints | Review relevance, audience expectations and frequency; suggest narrowing the audience, revising copy or pausing for review |
| Weak replies or conversions | When verified data exists, compare offer, targeting, proof and CTA without attributing the result to copy alone |

Compare like-for-like campaigns or the client's baseline over comparable windows; distinguish unique from total events and state rate denominators when known. There is no universal "good" open rate or guaranteed safe volume. Do not select a winner from tiny samples or fabricate missing conversion evidence.

Reports are read-only. Suggest changes with reasons; obtain explicit approval before edits, rescheduling, tracking changes or pauses, except an already authorized protective action. Existing unsubscribe, hard-bounce and reply-stop protections still apply. No autonomous monitoring or follow-up job is implied. Follow [bot-flow.md](bot-flow.md) for snapshots and [benchmarks.md](benchmarks.md) for interpretation.
