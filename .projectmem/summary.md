# projectmem - Cold Email Skill

_Last updated: 2026-11-17_

## Project purpose
Replace this placeholder with a concise description of what this project does, who it serves, and the main technologies or runtime assumptions.

## Recent issues
- [DONE] #0001 Skill installation lacks README and agent routing; agent links and client workspace paths are broken [Skills_AGENTS.md] (fixed)

## Decisions
- Publish one portable cold-email skill under skills/cold-email/ with references and blank JSON templates in assets/. Keep private runtime data in client-data/ outside installed skill files; root AGENTS.md routes by skill name. [skills/cold-email/]

## Notes
- Initial commit
- Downloaded all 12 files under coreyhaines31/marketingskills skills/cold-email into cold-email/ from tree 1f837447b20bb6f0e72d87b80ece1c221c362c7d. Verified every local Git blob SHA-1 and file count. Download only; no installation, activation, or execution. [cold-email/]
- Purpose: portable client-email instruction skill, no executable runtime. Entry: skills/cold-email/SKILL.md; assets holds blank JSON, references holds workflow/policy, evals holds prompts. Root README and AGENTS explain installation/routing. Existing project map is still an init placeholder. [skills/cold-email/]
- GitHub main still has old cold-email/ layout and long installation README referencing absent cold-email/AGENTS.md. Local new layout is verified only; no commit or push requested/performed. Remote install will use old content until publication. [README.md]

## Key files
- `.gitattributes`
- `AGENTS.md`
- `1.9.0`
- `skills/cold-email/SKILL.md`
- `cold-email/AGENTS.md`

## Open questions
- None logged yet.
