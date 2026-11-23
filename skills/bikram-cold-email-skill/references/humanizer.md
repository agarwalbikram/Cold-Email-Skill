# Humanizer pass for emails

Run this on every draft before you show it. It removes the patterns that make an email read as machine-written. Adapted for cold and promotional email from [blader/humanizer](https://github.com/blader/humanizer) (MIT), which is based on Wikipedia's "Signs of AI writing".

A model writes the most likely next word, so it picks choices that fit any reader. A person writing to one buyer makes uneven, specific choices. Every tell below is a default choice. Replace it with the specific one.

## How to run it

1. **Mark the tells.** Read subject and body once. Mark every pattern below, strongest first. Check paragraph shape too: three parallel paragraphs, or every paragraph ending on a punchline, is the same tell at a larger scale.
2. **Rewrite, don't patch.** State each point directly. If a sentence stays awkward after a word swap, rewrite the paragraph around its one point. Vary sentence length. A short sentence next to a longer one reads human; five medium sentences in a row read generated.
3. **Check facts survived.** Names, prices, services, links, tags (`[FNAME]`, `[COMPANYNAME]`, `[UNSUBSCRIBE_URL]`), disclosures and the CTA must be unchanged. A lost fact or tag is a bug.
4. **Read it aloud as the sender.** Would this person type this to one buyer they respect? If any line sounds like a brochure, a LinkedIn post or a chatbot, rewrite it.

Never show the operator the marked-up pass. Show only the final email.

## Voice override

If the operator supplied a sample they wrote (or a saved brand style), match its sentence length, word choice, punctuation and openings. The sample wins over this file, including the dash rule: if their sample uses dashes, keep about the same rate. A sample guides style only; never copy its sentences unless exact copy was requested.

## A. Staging instead of saying (fix on one sighting)

**1. Not X but Y.** "It's not just outreach, it's a growth engine." "This isn't about more emails. It's about the right ones." Also "X, not Y" tails and "no guesswork". Say the positive half plainly.
> Before: We're not just another agency — we're your wholesale partner.
> After: We handle wholesale sales for product brands.

**2. Punchline closers and fragments.** A one-line paragraph that restates the paragraph above. "Simple as that." "That's the difference." "No contracts. No hassle. Just results." Cut it or fold the fact into a sentence.

**3. Fake depth.** "At its core", "the real question is", "what really matters", "in today's fast-paced market", "in an ever-evolving landscape". Delete and state the claim.

**4. Staged run-up.** "Here's the thing", "Let's be honest", "I'll be brief", "I wanted to reach out because", "I'm reaching out to", "The reason I'm writing is". Start with the point.

**5. Arguing with no one.** "I know you're busy", "I know what you're thinking", "You might be wondering", "Don't worry, this isn't a sales pitch". Delete. (It is a sales email; that is fine.)

## B. Rhythm by rule

**6. Forced triads.** "Save time, cut costs, and grow faster." "Faster, smarter, better." Three items only when there really are three distinct things the reader needs. Otherwise keep the one that matters and develop it.

**7. Dashes.** No em dashes (—) or en dashes (–) or ` -- ` in generated copy unless the voice sample uses them. Use a period, comma, colon or parentheses. Hyphens inside words (`third-party`) and URLs are fine.

**8. Same sentence openings.** Three sentences starting "We..." in a row. Merge or start with the action or the reader.

**9. Stacked hedges.** "could potentially help", "might possibly be worth". One hedge at most, only when real.

**10. Rhetorical-question pileup.** "Struggling to get into stores? Tired of chasing buyers? What if there was a better way?" At most one question before the CTA, and only a real one the reader could answer.

## C. Inflation and sales language

**11. AI vocabulary.** Replace on sight: delve, leverage, utilize, robust, seamless(ly), streamline, elevate, unlock, empower, supercharge, revolutionize, game-changer, cutting-edge, innovative, holistic, synergy, tailored solutions, end-to-end, best-in-class, world-class, comprehensive, crucial, pivotal, key (adjective), landscape, ecosystem (figurative), journey, navigate (figurative), foster, enhance, optimize (outside technical use), take X to the next level, drive results, boost your bottom line, peace of mind, hassle-free.

**12. Inflated significance.** "a pivotal step for your brand", "transform the way you sell", "unlock your full potential". Keep the plain fact underneath: what changes, for whom.

**13. Brochure verbs.** "serves as", "stands as", "boasts", "offers a wide range of", "specializes in providing". Use is/has/does: "We run your Faire account."

**14. -ing tails.** "...helping you grow faster", "...ensuring nothing falls through the cracks", "...allowing you to focus on what matters most". Cut, or make it a real sentence with a concrete result.

**15. Borrowed authority and vague proof.** "Studies show", "experts agree", "trusted by leading brands", "countless clients". Name the real proof or drop it. Never invent it.

## D. Email-specific tells

**16. Canned openers.** "I hope this email finds you well", "I hope you're doing well", "I came across your company/profile", "My name is X and I'm the Y at Z", "Quick question —", "I'll keep this short", "Allow me to introduce". First line is about the reader's situation or goal.

**17. Fake familiarity.** "I was impressed by", "I love what you're doing at [COMPANYNAME]", "Congrats on your recent success". Only with a real, specific observation you can name.

**18. Canned CTAs.** "Would you be open to a quick chat to explore how we can help?", "Let me know if you'd be interested in learning more", "Feel free to reach out", "Worth a quick call?", "Do you have 15 minutes this week?". Use one plain question tied to the offer: "Want me to send the three changes I'd make?" / "Should I look at your current setup?" / "Is this something you're working on this year?"

**19. Focus-on-what-matters close.** "so you can focus on what you do best", "while we handle the rest", "so you can focus on growing your business". The most recognizable agency-email line. Say the concrete thing they get back.

**20. Wrapper residue.** No "Subject:" lines inside the body, no "Here's a draft for you!", no "Feel free to tweak!", no "I hope this helps", no bold labels, emojis or headings in the email. Plain paragraphs.

**21. Uniform paragraphs.** Every paragraph two sentences long, ending on a benefit. Real emails have a one-line paragraph next to a three-sentence one.

## Before and after

Brief: Get Wholesale Orders, retail-buyer outreach and follow-up, Faire/RangeMe and B2B ordering, free wholesale audit. No proof or recipient research available.

**Before (typical AI output):**
> Subject: Unlock Your Wholesale Potential
>
> Hi [FNAME],
>
> I hope this email finds you well! Quick question — are you looking to take [COMPANYNAME] to the next level in retail?
>
> At Get Wholesale Orders, we're not just an agency — we're your end-to-end wholesale partner. We help brands connect with retail buyers, streamline sales outreach, and seamlessly manage Faire, RangeMe, and B2B ordering, so you can focus on what you do best.
>
> Would you be open to a quick chat to explore how we can help?

Tells: canned opener (16), dash and "take to the next level" (7, 11), not-X-but-Y (1), triad plus AI verbs (6, 11), focus-on-what-you-do-best (19), canned CTA (18), title-case slogan subject.

**After:**
> Subject: more stores for [COMPANYNAME]
>
> Hi [FNAME],
>
> Getting a product into stores usually comes down to time. Someone has to find the right buyers, pitch them and keep following up until an order comes in.
>
> That's the work we do at Get Wholesale Orders. We contact retail buyers for you, handle the follow-ups, and run your Faire and RangeMe accounts and B2B orders.
>
> If more retail accounts are a goal this year, I can review your current wholesale setup for free and send you what I'd change first.
>
> Want me to take a look?
>
> Best,
> [Your Name]
> Get Wholesale Orders
> https://getwholesaleorders.com
>
> [Unsubscribe]([UNSUBSCRIBE_URL])

Same facts, same offer, same CTA goal. It now names a real bottleneck, says what the team does in plain verbs, and asks a question the reader can answer with one word.

## When not to act

- Exact-copy requests: leave the supplied wording alone except the mandatory footer repairs in [writing.md](writing.md).
- A plain "Thanks," "Best," or a normal sign-off is human; keep it.
- Don't strip personality to pass this check. After the tells are gone the email must still sound like a specific person, with an opinion or a concrete detail. Flat and generic is also a failure.
