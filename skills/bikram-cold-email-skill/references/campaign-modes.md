# Own-product, affiliate and ClickBank modes

Two separate decisions: **who sells the offer** (`commercial_relationship`: `own_product`, `affiliate`, `clickbank_affiliate`) and **why this person may get the email** (`campaign_mode`). An affiliate account or a MailWizz subscriber status is not permission to market.

| Mode | Use | Copy | Needed before sending |
| --- | --- | --- | --- |
| `b2b_cold` | Business outreach where law and provider policy allow it | Peer-style note, reply-first CTA, no marketing link in the body of email one (signature website is fine) | Business relevance, lawful contact basis, provider acceptance, opt-out, sender identity, postal address |
| `permission_based_promotion` | Audience that opted in to this sender and this kind of offer | Honest promotional subject, one benefit, one CTA; the approved offer link may appear in email one | Consent source, scope and date, expected frequency, offer terms, unsubscribe, provider permission |

Never convert a bought or scraped list into permission-based. If permission or provider acceptance is unknown, draft locally and mark it blocked for sending.

## Own product

Use the client's approved identity, proof and terms. Never treat writing examples as client evidence.

## Affiliate

- Record the real seller, product, program, allowed email methods, approved URL, prohibited claims and disclosure on the offer.
- Never write "we built" or "our product". The sender is the promoter.
- Put a clear disclosure near the CTA, e.g. "I may earn a commission if you buy through this link." Use the operator's approved wording.
- Use the exact approved HTTPS link with its attribution. Don't create IDs, shorten, cloak or redirect links.
- No implied personal use, neutral review, endorsement, testimonials, cures, income promises, fake discounts or resetting countdowns.

## ClickBank

- Record `clickbank_affiliate`, seller, offer, approved HopLink and current terms. Check the seller's affiliate rules and ClickBank's [Promotional](https://support.clickbank.com/en/articles/10535354-promotional-guidelines) and [Advertising](https://support.clickbank.com/en/articles/10535342-advertising-guidelines) guidelines for each new offer; re-check on material changes.
- Eligibility depends on program terms, provider policy, audience and law. If any prohibits it, don't schedule.
- Honest subject and headers, opt-out, advertisement identification and affiliate disclosure where required.
- Verify price, recurring billing, real deadlines and refund terms against current seller material. Mention recurring billing whenever price is mentioned.
- Health, supplement, weight-loss, investment and income offers need substantiated claims and human compliance review. Never infer a recipient's health or finances.
- Time-bound offers: the whole send window must close before the deadline ([mailwizz.md](mailwizz.md)).

## Promotional sequences

Approved frequency, permission scope, deadline and stop rules. Unsubscribes, complaints and hard bounces block further sends. A conversational reply pauses automation for review. Purchase-based stopping needs a verified purchase source; otherwise don't promise it. Same approval packet and readback as any campaign. Don't apply B2B reply benchmarks to promotions.
