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

1. **Opening (1–2 sentences): their world.** The goal or bottleneck this reader has, stated as something they'd agree with. No greeting fluff, no "I", no lecture about the industry. Write it fresh from this brief; never start from an example's opening line.
2. **What we do (2–3 sentences): the work.** Who you are in half a sentence, then what you actually do toward that goal, in verbs: "We contact retail buyers for you and follow up until they order." **First touch: at most 2 services**, the ones closest to the reader's goal. Save the rest for follow-ups, one per step.
3. **Why it matters (optional, 1 sentence).** A practical result for them, only if supported. Proof goes here if you have it.
4. **One ask (1 sentence).** A question they can answer quickly, tied to the confirmed CTA. Offer the work itself, not a link to it: "Want me to look at your current setup and send back what I'd change first?" beats "Want the link to our audit?". Describe what they get from the CTA using the sender's own source wording.

Rules that matter more than the shape:

- **Length follows the job.** A simple offer: 50–80 words. A multi-service introduction: 80–140. Follow explicit "shorter"/"longer" requests. Never pad.
- **Plain words.** Write like the sender talks to a peer. Contractions are fine. Short and long sentences mixed.
- **"You" more than "we", but "we" is allowed.** A clear company introduction is fine; marketing intent is not something to hide.
- **One CTA.** A signature website and the unsubscribe link don't count as extra asks.
- **Ground every claim.** Each benefit traces to a sender source. Each observation about the recipient traces to a real, dated recipient source. Without one, use segment-level relevance ("Most brands at your stage...") and never write "I noticed", "I saw" or praise.
- **Numbers only from pages you actually read.** A figure seen in a snippet, teaser or listing summary is unverified: read the full page or drop the number.
- **Don't assume their stack.** Unless the brief says so, condition it: "If you sell on Faire", not "Faire takes 15% of your orders".
- **Describe the CTA as it actually works.** If sources disagree on what the reader gets (e.g. "we review your setup" vs a self-serve quiz that emails a PDF), use the description from the CTA's own page and flag the conflict in one line after the email. Don't say the CTA covers a topic its page doesn't list, even when it's the topic of this email.
- **Use the sender's fit statement.** If the sender's site says who it's for ("brands that can already fill repeat orders"), use it as a condition in the opening. It qualifies the reader honestly and sounds specific.
- **Give before you ask.** The sender's own FAQ, guides and pricing pages hold real expertise. One practical tip from them (what buyers ask for, how a fee works) is worth more to the reader than another service description. Quote only from pages you read.
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
- **Sequence:** default 3 emails at days 0, 3, 7; max 5 for unsolicited B2B. Each step shows step number, day, angle, subject, body. Never "just checking in", "bumping this", "following up on my last email", "did you see my email".
  - **Plan before writing (privately).** One row per step: angle, the one new thing, its source page, the opening move, the ask wording. If two rows share an opening move or ask wording, change one before drafting.
  - **Each step stands alone.** Assume they never read the earlier ones: say who you are and what the CTA is in one clause each time ("our free 4-minute audit, which scores your setup and sends a plan").
  - **Each step adds one new thing:** a service held back from email 1, a specific useful fact, approved proof or a resource. One new thing per step, not a recap.
  - **Vary the ask's wording and angle** while keeping the same CTA goal. Four identical "want the link?" questions is a failure.
  - Follow-ups get shorter: 40–80 words. Lead with the reader's benefit, not your pricing mechanics, unless price is the point of that step.
  - **Vary the shape across steps.** Not every step can be "fact → At [Company] we… → audit offer" in three paragraphs. Change the opening move (a question, a fact, a one-line note) and the paragraph count.
  - The last step is a short, honest close in your own words: say this is the last email, leave one useful thing, and say how to restart (reply).

- Any reply stops the sequence for that person; opt-outs and hard bounces are suppressed everywhere ([mailwizz.md](mailwizz.md)).
- Starting send time: Tue–Thu, 9–11 am or 1–3 pm recipient local time. A default, not a rule.

## 6. Review before presenting

Read subject and full body together, as the recipient. Fix anything that fails, in this response:

1. Would this reader know in the first two lines why it's for them?
2. Is the work explained in plain verbs, connected to their goal, with at most 2 services in a first touch?
3. Is every claim sourced, every number from a page you actually read, and nothing invented or assumed about the recipient's tools?
4. One CTA, the confirmed one, as an easy question that offers the work, described the way its own page describes it?
5. Does the subject promise something the body delivers?
6. Does the reader get something useful even if they never reply (a fact, a tip, a clear picture of the work)?
7. Tags, signature, website and linked unsubscribe present on every item?
8. Is the opening and every sentence original, not reused from an example in this skill?
9. Sequences: does each step stand alone, add one new thing, open differently, word its ask differently, and stay within 40–80 words after step 1?
10. [humanizer.md](humanizer.md) pass done: no AI tells, no dashes (unless the voice sample uses them), varied rhythm? Read it aloud in your head: would a busy owner believe one person typed this?

Then present: company/brand label, subject, body. Put blockers (missing sender name, unverified tags, missing address) in one or two short lines after the email, not inside it. No self-grading, no "here are some options", no offer to "make it punchier".

## 7. Feedback

- "Too generic", "sounds bad", "sounds like AI": keep the reader, goal, offer and CTA. Rewrite the opening, the explanation and the rhythm with a stricter humanizer pass. Return one better email, no long apology.
- "Too short": add specific, useful detail about the work, not adjectives. "Too long": cut the weakest paragraph, not the explanation.
- "Change the CTA / remove the link / more casual" applies to this draft only. Save it as a preference only when the operator says "always" or "from now on" ([workflow.md](workflow.md)).

## 8. What good looks like

Two short examples for **fictional** businesses. They show the moves (fresh opening, at most two services, an ask that offers the work). Never reuse their sentences, openings or subjects for a real client; every real draft starts from its own brief.

**Fictional product-photo studio, no proof, meeting CTA by reply:**
> Subject: product photos that sell on Amazon
>
> Hi [FNAME],
>
> When a listing gets traffic but few sales, the photos are usually the first thing shoppers judge and the last thing brands update.
>
> At Brightframe Studio we shoot white-background and lifestyle images sized for Amazon and Shopify, and we retouch the ones you already have.
>
> Could we do a 20-minute call next week? Reply with a day and I'll send a time.
>
> Best,
> [Your Name]
> Brightframe Studio
> https://brightframe.example
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
