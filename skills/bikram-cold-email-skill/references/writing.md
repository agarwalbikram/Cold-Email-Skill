# Writing the email

This is the whole writing method: brief, body, subject, footer, review. Follow it in order for every new email, variation, sequence step and rewrite. Then run [humanizer.md](humanizer.md).

## 1. Build a working brief (private)

Fill these from the profile, sources and current request. Don't show this to the operator.

| Field | Source |
| --- | --- |
| Sender | Company, brand, website, personal sender name (or `[Your Name]`) |
| Reader | Role and company type. One reader, not "businesses" |
| Their goal | The main reason this reader would buy. For a growth service it is growth (more stores, more pipeline), not a dashboard or portal |
| What we do toward it | 2–3 connected capabilities that serve that goal, in plain verbs |
| Proof | Only approved, sourced proof. "None" is a valid answer |
| Next step | The confirmed CTA (reply, meeting by reply, free audit, link). Keep it exactly; never swap a meeting for an audit or add an incentive |
| Mode | `b2b_cold` or `permission_based_promotion` ([campaign-modes.md](campaign-modes.md)) |
| Voice | Operator sample or saved brand tone, else: plain, friendly, direct |

If the reader, the offer or the CTA is unknown and the profile can't answer, ask one short question. Otherwise write. Broad targeting ("brands worldwide") is enough for a segment-level draft.

## 2. Write the body

Default shape for a first touch. Bend it when the brief calls for something else.

1. **Opening (1–2 sentences): their world.** The goal or bottleneck this reader has, stated as something they'd agree with. No greeting fluff, no "I", no lecture about the industry.
2. **What we do (2–3 sentences): the work.** Who you are in half a sentence, then what you actually do toward that goal, in verbs: "We contact retail buyers for you and follow up until they order." Group related services; don't list the menu.
3. **Why it matters (optional, 1 sentence).** A practical result for them, only if supported. Proof goes here if you have it.
4. **One ask (1 sentence).** A question they can answer quickly, tied to the confirmed CTA.

Rules that matter more than the shape:

- **Length follows the job.** A simple offer: 50–80 words. A multi-service introduction: 80–140. Follow explicit "shorter"/"longer" requests. Never pad.
- **Plain words.** Write like the sender talks to a peer. Contractions are fine. Short and long sentences mixed.
- **"You" more than "we", but "we" is allowed.** A clear company introduction is fine; marketing intent is not something to hide.
- **One CTA.** A signature website and the unsubscribe link don't count as extra asks.
- **Ground every claim.** Each benefit traces to a sender source. Each observation about the recipient traces to a real, dated recipient source. Without one, use segment-level relevance ("Most brands at your stage...") and never write "I noticed", "I saw" or praise.
- **Executives:** shorter and peer-level, but still explain the work. **Technical buyers:** precise mechanism, no hype. **Managers:** concrete workflow change.
- **Don't invent** pain, results, customers, numbers, urgency, prior contact or incentives.

### Shapes to choose from

Use the one that fits the facts; freeform is fine.

- **Goal → work → ask** (default, service-led intro).
- **Observation → implication → capability → ask** (only with a verified recipient observation).
- **Problem → consequence → capability → small ask** (PAS; keep the consequence proportionate).
- **Question → value → ask** (a real question about their workflow, not a loaded diagnostic).
- **Value-first teardown:** email 1 offers one specific finding about their page and asks permission to send the rest. Only with a real finding; a human reviews it.
- **Case → ask:** only with a permission-cleared customer story.

## 3. Write the subject (after the body)

Privately draft 3 subjects with different angles (their goal, a specific outcome, a plain question), then pick the one the body pays off best. Return one unless variants are requested.

- 2–7 words, sentence case or lowercase, reads like a colleague typed it. Specific beats clever: "more retail buyers for [COMPANYNAME]" beats "Wholesale growth".
- Front-load the topic. No ALL CAPS, emojis, "!", fake "Re:"/"Fwd:", fake urgency or unsupported numbers.
- `[COMPANYNAME]` can appear in a subject; avoid `[FNAME]` in B2B subjects.
- Don't repeat the subject as the first line of the body.
- A supplied subject is kept unless it's deceptive; flag it rather than silently replacing it. Subject-only requests return a new subject and leave the body byte-for-byte unchanged.

## 4. Tags and footer (every full email, variant and step)

Every newly composed email is a reusable MailWizz draft:

- Greeting `Hi [FNAME],`. Use `[COMPANYNAME]` where the recipient's company belongs (B2B). `[COMPANYNAME]` is the **recipient**, never the sender, and it is a custom field, not a built-in MailWizz tag.
- End with this footer. Use the real sender identity for the selected brand; for Get Wholesale Orders that is `Get Wholesale Orders` and `https://getwholesaleorders.com`. Never reuse it for another business. Unknown values stay as `[Your Name]`, `[Your Company]`, `[Your Website]`.

```text
Best,
[Your Name]
Sender Company
https://sender-website.com

[Unsubscribe]([UNSUBSCRIBE_URL])
```

- HTML campaigns: `<a href="[UNSUBSCRIBE_URL]">Unsubscribe</a>`. Plain text: `Unsubscribe: [UNSUBSCRIBE_URL]`. A bare "Unsubscribe" label or "reply no" is not an unsubscribe.
- Add required postal address and affiliate/ad disclosures on top of the footer.
- Tags are proposals until the list's fields are checked. Drafting never waits on this; sending does ([mailwizz.md](mailwizz.md)). If the list uses `[COMPANY]` instead, show the mapping change for approval; never silently rename or strip a tag.
- Generate square-bracket tags only. Curly-brace variables survive only when the operator supplied them in exact copy.

### Exact copy vs style reference

- **"Use this exact text / keep this body":** keep the wording and their variables. Still repair a missing signature, website or unsubscribe link, and say so in one line outside the email.
- **"Like this" / "use this as a reference":** match its voice, length and level of detail; write new sentences. Don't copy its hook or incentive.

## 5. Variations and sequences

- **Variations:** the requested count, each a genuinely different angle (goal-led, outcome-led, question-led), each labeled, each with full tags and footer. Alternatives, not a send plan.
- **Sequence:** default 3 emails at days 0, 3, 7; max 5 for unsolicited B2B. Each step shows step number, day, angle, subject, body. Every step adds something new (a different benefit, a useful resource, a specific idea, approved proof) and stands alone. Follow-ups get shorter. Never "just checking in", "bumping this", "following up on my last email", "did you see my email". The last step is a short, honest close:

> I'll stop here so I'm not cluttering your inbox. If getting into more stores comes up later, just reply and I'll pick it up.

- Any reply stops the sequence for that person; opt-outs and hard bounces are suppressed everywhere ([mailwizz.md](mailwizz.md)).
- Starting send time: Tue–Thu, 9–11 am or 1–3 pm recipient local time. A default, not a rule.

## 6. Review before presenting

Read subject and full body together, as the recipient. Fix anything that fails, in this response:

1. Would this reader know in the first two lines why it's for them?
2. Is the work explained in plain verbs, connected to their goal, not a service list?
3. Is every claim sourced and nothing invented about the recipient?
4. One CTA, the confirmed one, as an easy question?
5. Does the subject promise something the body delivers?
6. Tags, signature, website and linked unsubscribe present on every item?
7. [humanizer.md](humanizer.md) pass done: no AI tells, no dashes (unless the voice sample uses them), varied rhythm?

Then present: company/brand label, subject, body. Put blockers (missing sender name, unverified tags, missing address) in one or two short lines after the email, not inside it. No self-grading, no "here are some options", no offer to "make it punchier".

## 7. Feedback

- "Too generic", "sounds bad", "sounds like AI": keep the reader, goal, offer and CTA. Rewrite the opening, the explanation and the rhythm with a stricter humanizer pass. Return one better email, no long apology.
- "Too short": add specific, useful detail about the work, not adjectives. "Too long": cut the weakest paragraph, not the explanation.
- "Change the CTA / remove the link / more casual" applies to this draft only. Save it as a preference only when the operator says "always" or "from now on" ([workflow.md](workflow.md)).

## 8. What good looks like

Two short examples written from limited facts. Learn the moves, don't reuse the sentences.

**Agency services, no proof, meeting CTA by reply:**
> Subject: retail buyers for [COMPANYNAME]
>
> Hi [FNAME],
>
> A lot of brands have a product stores would happily carry. What they don't have is someone whose whole job is getting it in front of buyers.
>
> That's what we do at Get Wholesale Orders. We find retail buyers who fit your category, pitch them for you and follow up until there's an answer. We also run your Faire and RangeMe listings so orders coming in through those don't sit.
>
> Open to a 20-minute call next week to see if it fits? Just reply with a day that works.
>
> Best,
> [Your Name]
> Get Wholesale Orders
> https://getwholesaleorders.com
>
> [Unsubscribe]([UNSUBSCRIBE_URL])

**SaaS tool, one confirmed capability, reply CTA:**
> Subject: catching missing receipts earlier
>
> Hi [FNAME],
>
> If month-end at [COMPANYNAME] still means someone chasing receipts in the last week, this could give them those days back.
>
> Our tool flags expense reports with missing receipts as soon as they're submitted, so your team sees the gaps during the month.
>
> Would a two-minute walkthrough be useful?
>
> (Same footer as above. Every real draft includes it in full.)
