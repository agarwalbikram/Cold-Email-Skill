# #0001 Skill installation lacks README and agent routing; agent links and client workspace paths are broken

- 2026-11-17T04:49:12Z `issue`: Skill installation lacks README and agent routing; agent links and client workspace paths are broken [Skills_AGENTS.md]
- 2026-11-17T04:54:18Z `attempt`: Moved skill to skills/cold-email, JSON to assets; added name-based AGENTS, workspace policy and install README. skills@1.9.0 discovered one skill and installed all 18 files unchanged for Codex. Three JSON files and 71 relative links validated. [skills/cold-email/] (worked)
- 2026-11-17T04:55:30Z `fix`: Verified local installable cold-email package, name-based AGENTS and install-first README. skills@1.9.0 discovers one skill and copies all 18 files for Codex; 3 JSON and 71 links pass. Live host conversation/MailWizz untested; GitHub remains unchanged until push. [skills/cold-email/]
