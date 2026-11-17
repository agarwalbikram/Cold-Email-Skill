# Bikram Cold Email Skill

This skill supports cold-email writing, company/brand memory, campaign setup, and requested MailWizz campaign reporting. It is not an infrastructure audit or live deliverability service: it does not check DNS, headers, seed inboxes, warmup, blacklist status, or live inbox placement. These checks are not prerequisites or launch gates.

## Campaign reporting and tracking

On request, report campaign status and opens, clicks, unsubscribes, and bounces when the connected MailWizz MCP exposes them. Include counts/rates, observation window, and denominator when known. Label unavailable or unsupported data as unavailable, never as zero; do not invent metrics. Qualify conclusions and suggestions by available evidence and the limitations of open/click tracking, including privacy pixels and bot activity. Reporting is read-only and does not authorize campaign changes.

Preserve existing tracking settings. Open/click tracking defaults remain false in the provided template. Do not enable or disable tracking to obtain metrics. A tracking change requires explicit operator approval for the exact campaign/version and fields, then remote readback confirming the actual settings. If readback is unavailable, report that rather than claiming success.

## Evaluations

[`evals/evals.json`](evals/evals.json) is a manual evaluation dataset, not an executable test suite or evidence of results. See [`evals/README.md`](evals/README.md) for scenario handling and file-backed fixture isolation. Cases 31–35 are file-backed scenarios; the other cases are prompts and expected behaviors. No case is passed merely because it appears in the dataset.
