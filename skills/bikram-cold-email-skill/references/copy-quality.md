# Email Copy Quality and Campaign Signals

This skill writes brand-specific cold emails and sequences, creates/schedules approved MailWizz campaigns, and interprets available campaign statistics on request. It does not inspect received emails, run inbox-placement tests, audit DNS/authentication or IP reputation, manage warmup, or configure sending infrastructure. Those are the operator/provider's responsibility, not extra bot onboarding questions or a requirement to upload audit evidence before drafting or scheduling.

## Review the copy before presenting it

- Match the selected brand, audience, offer, language and requested format. A style example guides voice, useful detail and organization, not sentences to repeat. Compose original copy unless exact wording is explicitly requested; preserve requested variables, signatures and required disclosures. Do not force a teaser or researched trigger.
- Choose a subject around a specific reader motivation the body satisfies: a relevant opportunity, useful answer, practical workflow improvement or verified trigger. Privately compare different hooks; reject topic labels, feature summaries and generic benefit slogans even when factually accurate. Curiosity must be resolved by the actual offer, not fake familiarity, urgency or promises. No fixed word-count/lowercase target or guaranteed opens; see [subject-lines.md](subject-lines.md).
- Use plain language and one primary conversion goal. Follow the requested detail/length: a service-led email may need roughly 90–140 body words, but neither that range nor an ultra-short target is mandatory. An opening relevance question and closing audit CTA may share one goal. A signature website and opt-out do not count as additional sales asks. Preserve appropriate promotional links under [campaign-modes.md](campaign-modes.md).
- Remove filler, repeated pitches, excessive capitals/punctuation, fabricated urgency and unsupported guarantees. Words such as "free", "discount" and accurate prices are not automatically banned; review meaning and evidence, not an arbitrary keyword score.
- For service-led copy, connect capabilities to the selected recipient goal and a practical benefit rather than copying a website menu. Prefer direct relevance over a generic industry lesson. Preserve a requested full-suite explanation or supplied style, grouping related functions. Do not invent a pain, differentiator, guarantee or customer result to make copy persuasive.
- Read the subject and complete body together before returning them. Revise vague hooks, repeated setup, catalog paragraphs and unsupported claims now, not only after the operator complains. Return the requested number of finished drafts, not unsolicited variants, a scoring report or internal deliberation.
- Separate reference style, editorial format and exact-copy intent. Requested reusable variables may remain while the surrounding sentences are original. "Like this" does not lock wording; explicit "keep this exact body" does. Ordinary drafts omit unverified editorial tokens. Neither format excuses invented observations; reading a sender's site is not recipient research.
- Preserve the operator's actual conversion goal. A meeting invitation must not become a free audit or other incentive unless that offer is supported and requested. For multi-service introductions, explain what the related work does and why it matters before the invitation; a capability slogan is not a full explanation. Explicit brief-copy requests still take precedence.
- "Quick question", em dashes, a truthful free audit and a direct company/service introduction are allowed when they fit the requested voice. Judge clarity and accuracy rather than isolated words or punctuation.
- Never disguise words with symbols, invisible characters or random spintax to evade filters. No wording guarantees inbox placement or an open-rate lift.
- Keep sender identity, affiliate disclosures, truthful terms, postal address and required opt-out/unsubscribe content intact. Allow the operator-approved website in a signature, including first touch. Avoid shorteners and unnecessary links/attachments; do not remove compliance links. "Reply no and I won't follow up" requires supported stop handling before scheduling; a standalone "Unsubscribe" label must become a working supported unsubscribe mechanism, never an invented URL.
- Preview available MailWizz fields and missing-value fallbacks before scheduling. Never send unresolved tags, editorial notes or invented recipient facts.
- In ordinary drafts, missing meeting URLs or personal sender names call for reply-based invitations and confirmed company signatures, not invented placeholders. In explicitly requested reusable templates, preserve the operator's editorial variables instead; verify/map them before sending, not before drafting. Preserve signature/disclosure requirements and report unresolved sending details outside the copy without claiming send readiness.
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
