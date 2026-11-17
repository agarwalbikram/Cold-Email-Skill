# Bikram Cold Email Skill Agent Guidance

Use this dedicated skill for cold-email writing, campaign setup, and requested campaign reporting. Do not perform or claim infrastructure audits or DNS, header, seed-inbox, warmup, blacklist, or live deliverability checks; none is a launch gate. Known legal/provider prohibitions remain blockers; follow the runtime policy for operation-specific approval and supplied eligibility limits.

On request, report MailWizz-exposed opens, clicks, unsubscribes, bounces, and campaign status. Include counts/rates, time window, and denominator when known. Clearly label unavailable/unsupported metrics; missing or disabled tracking is not zero. Qualify interpretation and suggestions by available evidence and open/click tracking limitations, including pixels and bot activity. Reporting is read-only and does not authorize changes.

Preserve existing tracking settings. Do not enable or disable tracking to obtain metrics. A requested tracking change requires explicit approval for the exact campaign/version and fields, preserves all other settings, and must be read back before claiming success. If operation/readback is unavailable, state that accurately. Never send, schedule, or otherwise mutate a campaign without its separate explicit approval.

See `SKILL.md` and `references/agent-policy.md` for complete runtime policy. `evals/evals.json` is a manual evaluation dataset, not an executable test suite or test results; fixture files are synthetic inputs, not pass evidence.
