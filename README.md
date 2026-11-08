# ApplyPilot

ApplyPilot is a reusable AI-agent skill for finding jobs, judging fit, selecting or tailoring resumes, completing authorized applications, and tracking outcomes.

## Install

Copy this repository's contents to your agent's `applypilot` skill directory. For Codex, use `~/.codex/skills/applypilot/` and invoke `$applypilot` in a chat. Other agents can load `SKILL.md` as their workflow instructions.

On first use, ask the agent to set up a **private workspace** from `templates/`. Keep your profile, resumes, answer bank, rules, and application dashboard outside this repository. Do not commit the completed files. The agent should ask only for facts it cannot safely infer.

## Set your own conditions

Edit the private `candidate_profile.json` and `application_rules.md` created from the templates. Set your target roles, locations, compensation, resume files, application authorization, and work authorization. For example, a person with a green card can record their own current authorization and sponsorship answers; someone on a visa can record different answers. The templates leave those fields blank. The agent must use your confirmed facts and check the wording of each form.

For a candidate who has confirmed U.S. permanent residence and does not need employer sponsorship, the private profile could contain:

```json
"work_authorization": {
  "country": "United States",
  "current_authorization": "Lawful permanent resident",
  "requires_sponsorship_now": false,
  "requires_sponsorship_in_future": false,
  "answer_exactly_as": "",
  "notes_for_unclear_forms": "Ask me before answering if the wording differs."
}
```

This is an example, not a default or a legal determination. Each candidate confirms their own answers.

Start with a lead-finding trial. Review the first results and adjust your rules before authorizing submissions.

## Privacy

This repository contains instructions and blank templates only. Do not add real resumes, contact details, immigration documents, account data, or application history. See `references/safety-and-boundaries.md`.
