# Handling Replies

This reference supports safe sequence stopping and opt-out handling. When the operator supplies a reply, classify it and draft an answer from approved brand facts if requested. This skill does not run a sales inbox, book meetings, create calendar invitations or manage reminders.

This reference defaults to B2B cold conversations. For promotional permission and cross-brand opt-out scope, follow [campaign-modes.md](campaign-modes.md) and [mailwizz-mcp.md](mailwizz-mcp.md). Never inspect a different client's data to suppress this client's recipient.

Reply copy is a local draft, not permission to send. Hand external reply delivery and booking to the operator. Protective stopping/suppression follows the scoped authorization rules below; a prospect reply never approves a new campaign or resumption.

## Classify every reply

| Type | Looks like | Action |
|------|------------|--------|
| **Positive** | "Sure, let's talk," "Send times," "Tell me more" | Stop follow-ups under scoped authorization; draft an answer if requested and hand off to the operator |
| **Information request** | "What does it cost?" "Do you work with X?" | Draft a brief factual answer and optional call offer; obtain approval before sending |
| **Objection** | "We already use X," "No budget," "Not a priority" | Draft one response using the objection guidance below; obtain approval before sending |
| **Not now** | "Reach out next quarter," "After our launch" | Stop under scoped authorization; note the requested date for operator handoff, not an automatic reminder |
| **Referral** | "Talk to Sam, she owns this" | Draft a thank-you and proposed referral outreach; verify permission to cite their name and obtain operator approval before either send |
| **Wrong person, no referral** | "Not my area" | Draft one question about who owns it for approval; otherwise stop under scoped authorization |
| **Out of office** | Auto-reply | Pause; record the return date and any named stand-in. Resumption requires eligibility checks and explicit approval of the exact remaining items and absolute schedule |
| **Unsubscribe or hostile** | "Remove me," "Stop," anger | Suppress across the applicable cold-email scope under scoped authorization; any apology is a draft requiring approval before sending. Never argue |
| **Bounce** | Delivery failure | Suppress hard bounces; pause and investigate repeated soft bounces. Never delete the suppression evidence |

Every reply stops automated cold email follow-ups for that person across all lists and campaigns, not just the campaign that received it. After an out-of-office return date, re-check eligibility and obtain explicit operator approval of the exact remaining items and absolute schedule; a general resumption policy or eligibility check alone is insufficient. Confirm cancellation of queued sends where supported; if recipient-level stopping is unavailable, pause affected campaigns and have an operator exclude the contact before resuming. See [mailwizz-mcp.md](mailwizz-mcp.md).

## Objections in reply to cold outreach

Early objections are usually reflexes. Draft one brief response for operator review, making it easy to say no; every suggestion in this table is wording guidance, not permission to send, contact someone, or create a reminder:

| Objection | Response approach |
|-----------|-------------------|
| "We already use [competitor]" | Acknowledge it. Name the one situation where teams like theirs still look elsewhere. Ask if it applies |
| "No budget" | Ask when they plan budgets, or offer something that doesn't need one (an audit, a benchmark) |
| "Not a priority" | Acknowledge it, avoid pressure and leave any future outreach to operator review |
| "Send me more info" | Draft an answer with one approved resource and one low-friction question |
| "How did you get my email?" | Answer honestly with the actual source, and offer to remove them |

Escalate pricing negotiation, security reviews, contractual claims, and deal-stage objections to the responsible human. Do not invent approved answers.

## What an agent can handle

| Reply type | Agent action with verified scoped authorization | Human approval required |
|------------|-----------------------------|-------------------------|
| Out of office | Pause; record return date | Explicit approval of the exact remaining items and absolute schedule; a general resumption policy is insufficient |
| Unsubscribe or hostile | Suppress across all cold email campaigns | Any reply at all |
| Bounce | Suppress hard bounces; flag repeated soft bounces | Any change that would restore eligibility |
| Not now | Stop the sequence; record the requested date | Acknowledgment and any future re-enrollment |
| Positive | Classify, stop follow-ups, draft if requested | Operator handles sending and booking |
| Information request | Classify, stop follow-ups, draft from approved facts | Send response |
| Objection | Classify, stop follow-ups, draft a brief answer | Send response |
| Referral | Stop the original sequence; draft a thank-you | Send response or contact the referred person |

These actions require actual MCP support and scoped authorization; the table grants neither. Never infer permission to send from a reply, a subscriber status, or prior agent accuracy. If suppression cannot be confirmed, pause affected sending and escalate. This dedicated client bot keeps outbound replies human-approved; each reply send requires explicit operator approval, not standing authorization.

## Log it

Record recipient-level reply type, date, identity, list/campaign identifiers, email step, outcome, and confirmed stop/suppression evidence only in the authorized host/MCP contact system, using supported fields. Keep campaigns.json limited to aggregate counts and non-identifying evidence references, not recipient identities or reply bodies. If authorized logging is unavailable, report the operator action required without copying contact data into the register. Preserve opt-outs across imports and lists; never re-subscribe a suppressed address to reset a sequence.
