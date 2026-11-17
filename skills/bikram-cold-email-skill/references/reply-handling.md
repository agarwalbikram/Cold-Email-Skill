# Handling Replies

The sequence's job ends when someone replies. What happens in the next hour decides whether that reply becomes a meeting. This reference covers classifying replies, responding to each type, speed, booking, and what an agent can handle on its own.

This reference defaults to B2B cold conversations. For promotional permission and cross-brand opt-out scope, follow [campaign-modes.md](campaign-modes.md) and [mailwizz-mcp.md](mailwizz-mcp.md). Never inspect a different client's data to suppress this client's recipient.

## Classify every reply

| Type | Looks like | Action |
|------|------------|--------|
| **Positive** | "Sure, let's talk," "Send times," "Tell me more" | Respond fast, propose times, book (below) |
| **Information request** | "What does it cost?" "Do you work with X?" | Answer the actual question briefly, then offer a call |
| **Objection** | "We already use X," "No budget," "Not a priority" | Respond once, using the objection guidance below |
| **Not now** | "Reach out next quarter," "After our launch" | Thank them, set a reminder for the date they gave, stop the sequence |
| **Referral** | "Talk to Sam, she owns this" | Thank them; contact Sam citing the referral (with permission to use their name if unclear) |
| **Wrong person, no referral** | "Not my area" | Ask once who owns it; otherwise stop |
| **Out of office** | Auto-reply | Pause; record the return date and any named stand-in. Resumption requires eligibility checks and explicit approval of the exact remaining items and absolute schedule |
| **Unsubscribe or hostile** | "Remove me," "Stop," anger | Suppress from all cold email campaigns immediately. Apologize briefly if you reply at all. Never argue |
| **Bounce** | Delivery failure | Suppress hard bounces; pause and investigate repeated soft bounces. Never delete the suppression evidence |

Every reply stops automated cold email follow-ups for that person across all lists and campaigns, not just the campaign that received it. After an out-of-office return date, re-check eligibility and obtain explicit operator approval of the exact remaining items and absolute schedule; a general resumption policy or eligibility check alone is insufficient. Confirm cancellation of queued sends where supported; if recipient-level stopping is unavailable, pause affected campaigns and have an operator exclude the contact before resuming. See [mailwizz-mcp.md](mailwizz-mcp.md).

## Speed

Answer positive replies within minutes during business hours. The research behind the famous speed-to-lead multipliers is old (2007–2011), but the direction holds. Interest fades fast, and a prospect who replied to you has often replied to others too. Notify the responsible human promptly and keep someone accountable for replies every working hour.

## Booking

- **Propose two specific times** in their time zone, and include a booking link as a fallback ("or grab any time here"). Two concrete options get a faster yes than a bare link, which can feel like homework.
- **Send the calendar invite immediately** once they pick, with a one-line agenda.
- **Confirm the day before** with something useful: the agenda, a relevant case study, or (for an agency) the teardown you'll discuss. Pre-reads raise show rates.
- **Reminder an hour before**, by email.
- **Reschedule no-shows the same day,** warmly, once. After a second no-show, stop automated outreach; do not silently enroll them in nurture.

## Objections in reply to cold outreach

Early objections are usually reflexes. Answer once, briefly, and make it easy to say no:

| Objection | Response approach |
|-----------|-------------------|
| "We already use [competitor]" | Acknowledge it. Name the one situation where teams like theirs still look elsewhere. Ask if it applies |
| "No budget" | Ask when they plan budgets, or offer something that doesn't need one (an audit, a benchmark) |
| "Not a priority" | Ask what is a priority this quarter. If it isn't connected, step back and set a reminder |
| "Send me more info" | Send one specific resource and one question that makes a reply easy |
| "How did you get my email?" | Answer honestly with the actual source, and offer to remove them |

Escalate pricing negotiation, security reviews, contractual claims, and deal-stage objections to the responsible human. Do not invent approved answers.

## What an agent can handle

| Reply type | Pre-authorized agent action | Human approval required |
|------------|-----------------------------|-------------------------|
| Out of office | Pause; record return date | Explicit approval of the exact remaining items and absolute schedule; a general resumption policy is insufficient |
| Unsubscribe or hostile | Suppress across all cold email campaigns | Any reply at all |
| Bounce | Suppress hard bounces; flag repeated soft bounces | Any change that would restore eligibility |
| Not now | Stop the sequence; record the requested date | Acknowledgment and any future re-enrollment |
| Positive | Classify, stop follow-ups, draft a response | Send response and book |
| Information request | Classify, stop follow-ups, draft from approved facts | Send response |
| Objection | Classify, stop follow-ups, draft a brief answer | Send response |
| Referral | Stop the original sequence; draft a thank-you | Send response or contact the referred person |

These actions require actual MCP support and scoped authorization; the table grants neither. Never infer permission to send from a reply, a subscriber status, or prior agent accuracy. If suppression cannot be confirmed, pause affected sending and escalate. This dedicated client bot keeps outbound replies human-approved; each reply send requires explicit operator approval, not standing authorization.

## Log it

Record recipient-level reply type, date, identity, list/campaign identifiers, email step, outcome, and confirmed stop/suppression evidence only in the authorized host/MCP contact system, using supported fields. Keep campaigns.json limited to aggregate counts and non-identifying evidence references, not recipient identities or reply bodies. If authorized logging is unavailable, report the operator action required without copying contact data into the register. Preserve opt-outs across imports and lists; never re-subscribe a suppressed address to reset a sequence.
