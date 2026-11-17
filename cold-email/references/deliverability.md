# Cold Email Deliverability

The best cold email does nothing if it lands in spam. Deliverability is set up before the first send and watched every week after. This reference covers the sending setup, the mailbox providers' rules, volume limits, warmup, monitoring, and when to stop.

Numbers here come mostly from sending-infrastructure vendors and mailbox providers' own guidelines. Mailbox providers change enforcement without notice, so treat the volume figures as starting points and let your own placement tests decide. Mailbox-based examples apply only when that is the actual sending infrastructure; they are not MailWizz delivery-server or IP limits. Follow the MailWizz host's and delivery provider's acceptable-use policies. If they prohibit unsolicited email, do not send it through them.

These domain/mailbox and first-touch copy recommendations default to B2B cold email. Permission-based promotions may use an established, authenticated brand domain and an approved first-email offer link when provider policy and consent permit; see [campaign-modes.md](campaign-modes.md). Do not impose cold-mailbox rotation or warmup-network assumptions on a delivery-server-based promotional setup.

## The rules from Google, Yahoo, and Microsoft

| Provider | What it requires | Enforcement |
|----------|------------------|-------------|
| **Gmail** | SPF or DKIM for all senders; bulk senders need both, plus DMARC, alignment, and one-click unsubscribe on marketing mail. Other requirements include DNS, TLS, message format, and low spam complaints; see the linked guidelines | Non-compliance can cause temporary or permanent rejections, or spam placement |
| **Yahoo** | SPF or DKIM, valid forward/reverse DNS, RFC compliance, and complaints below 0.3%; bulk senders additionally need both SPF and DKIM, passing DMARC, and easy unsubscribe honored within 2 days | Requirements phased in from February 2024; do not assume Google's bulk threshold applies |
| **Microsoft** (Outlook.com, Hotmail, Live) | SPF, DKIM, and DMARC for senders above 5,000 a day | Since May 5, 2025, non-compliant mail is rejected (`550 5.7.515`) |

Google's bulk-sender classification counts aggregate traffic to personal Gmail accounts from the same primary domain, including subdomains: close to 5,000 messages in 24 hours can qualify. Once reached, bulk status is permanent; a smaller current campaign does not remove it. These recipient rules do not apply to Google Workspace business addresses. This skill recommends SPF, DKIM, and aligned DMARC even when the provider minimum is lower. Sources: [Google sender guidelines](https://support.google.com/mail/answer/81126?hl=en), [Google enforcement and bulk definition](https://support.google.com/mail/answer/14229414?hl=en), [Yahoo requirements](https://senders.yahooinc.com/best-practices/). Re-check before launch; authentication alone does not make unsolicited mail permitted.

**Complaint rate:** keep spam complaints under 0.1% and never reach 0.3%. Practitioners report Workspace sending degrading well before 0.3%.

## Sending setup

**Never send cold email from your primary domain.** One bad campaign can damage the domain your customers, invoices, and password resets depend on.

1. **Buy secondary domains** that are obviously yours (`getacme.com`, `acmehq.com`, `tryacme.com`). Redirect each to your main site.
2. **Authenticate every domain:** SPF, DKIM, and DMARC (start at `p=none` with reporting), aligned to the From domain. Keep open and click tracking disabled.
3. **For mailbox-based sending, plan 2–3 real mailboxes per domain** as a starting layout, each with an authorized sender identity and honest signature. Size the actual setup to verified provider limits and business needs. Aliases share their underlying mailbox's limits and are not additional sending capacity. MailWizz delivery-server setups need their own capacity plan rather than mailbox multiplication.
4. **Only buy mailboxes from properly licensed tenants.** In late 2025 Google reportedly suspended large numbers of resold Workspace mailboxes built on education, nonprofit, or legacy accounts. Cheap "reseller" inboxes are disposable at best.
5. **Match the provider to your prospects where you can.** Google-hosted mailboxes for audiences on Google Workspace (most startups and SaaS), Microsoft-hosted for enterprise audiences on Microsoft 365. Vendors report better inbox placement when the two match. Check a prospect's mail host from their MX record.

### Volume math

| Setting | Starting point |
|---------|----------------|
| Sends per mailbox per day | 20–30 (Google-hosted); test lower for Microsoft-hosted, where 2026 operator reports range from single digits to dozens |
| Mailboxes per domain | 2–3 |
| Daily volume | Mailboxes × sends per mailbox |

Example: 500 sends a day ≈ 20 mailboxes at 25 each ≈ 7–10 domains. Follow-ups count toward the daily volume.

If a domain or delivery server loses reputation, pause and investigate before resuming. Do not swap identities or infrastructure to evade provider restrictions, complaints, or suppression.

## Warmup

For new mailbox-based infrastructure, budget roughly 3–4 weeks for a gradual ramp as a planning starting point, not a guaranteed launch date. Begin with low-volume genuine correspondence to engaged recipients, verify authentication and placement, then increase only while delivery signals remain healthy. Use provider-approved limits; the volume examples above are planning inputs, not permission to send at that rate.

Monitor deferrals, bounces, complaints, and reputation throughout. Reduce or pause on deterioration; extend the ramp if needed. For MailWizz delivery servers, use the host's domain/IP ramp plan instead of assuming a mailbox warmup schedule applies. A paid warmup network is not a launch requirement or proof of inbox readiness.

## The email itself

- **Plain text.** No images, no HTML templates, no attachments.
- **No marketing link in the first email,** and at most one in later ones. Never use link shorteners. Required unsubscribe links and headers are exempt.
- **Turn off open tracking.** Privacy features and automated fetches make tracked opens unreliable. Measure replies instead; disabling a pixel does not guarantee inbox placement or a fixed reply lift.
- **Turn off click tracking.** Measure replies instead.
- **Under about 80 words** for the first email.
- **Vary the copy.** Identical bodies across thousands of sends look like bulk mail. Segment-specific copy and real personalization fix this naturally. Keep spintax as a last resort.
- **Unsubscribe and identity.** Include an honest sender identity, valid postal address, and clear opt-out. Preserve required unsubscribe links and one-click unsubscribe headers even when marketing links and tracking are disabled. Confirm applicable recipient-country law and the delivery provider's policy; business contact details are not blanket permission to email. Where consent is required, do not send without it.

## Verify before you send

This skill uses conservative operating targets of under 2% bounces per campaign, preferably under 1%; these are not published universal provider thresholds. Apply any stricter provider limit and investigate deterioration before increasing volume.

- Verify every list before upload, and re-verify anything older than about a week.
- Exclude invalid addresses. Hold catch-all or unverifiable addresses unless an approved verification policy explicitly allows them; never treat an import or a MailWizz subscriber record as verification evidence.
- Pause any campaign automatically when its bounce rate passes 2%.

## Monitoring

| Check | How | When |
|-------|-----|------|
| Inbox placement | Approved seed-inbox tests; use a MailWizz MCP operation only if the connected server actually exposes one | Before every new campaign and weekly |
| Domain reputation | Google Postmaster Tools; Microsoft SNDS | Weekly |
| Bounce rate | MailWizz campaign and delivery-server data exposed by the connected MCP, or verified operator reports | Daily |
| Spam complaints | Postmaster Tools; replies containing "spam" or "stop" | Weekly |
| Blocklists | A blocklist checker for each sending domain | Weekly |
| Authentication | DMARC aggregate reports | Monthly |

## Stop-loss rules

Decide these before launch and enforce them automatically where your tool allows:

| Trigger | Action |
|---------|--------|
| Bounce rate above 2% on a campaign | Pause the campaign and re-verify the list |
| Inbox placement below ~70% on a mailbox or domain | Pause that sender, investigate, and validate placement before resuming |
| Spam complaints approaching 0.1% | Pause, cut volume, review targeting and copy |
| Domain appears on a major blocklist | Stop sending from it; delist or retire it |
| Reply rate under ~1% after 300+ sends | Stop the campaign; the targeting or offer is wrong, and more volume makes it worse |

## Common mistakes

- Sending from the primary domain
- Buying the cheapest reseller mailboxes and losing all of them at once
- Skipping verification "because the data provider verified it"
- Leaving open tracking on and optimizing for a number that isn't real
- Scaling volume to fix a low reply rate
- Running warmup and cold sends at full volume from day one

## MailWizz MCP

Use [mailwizz-mcp.md](mailwizz-mcp.md) for the only campaign integration in this skill. Confirm the actual delivery infrastructure, provider-approved sending limits, unsubscribe support, and monitoring before launch. DNS authentication, list verification, inbox placement, and reputation checks require evidence; do not assume MailWizz MCP can perform them.

Google Postmaster Tools, Microsoft SNDS, and DMARC aggregate reports remain evidence sources, not alternate campaign integrations. If monitoring or a required safety action is unavailable through MCP, request verified operator evidence or action and leave affected sending paused.
