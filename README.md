# CareerPilot

**An end-to-end job search workflow for AI agents, from finding the right roles to tracking application outcomes.**

CareerPilot helps experienced professionals, students, new graduates, and career changers run a more organized job search. It gives an AI agent a repeatable process for understanding a candidate, finding and screening jobs, choosing or tailoring truthful resumes, completing authorized applications, and learning from results. You set the goals and rules; the agent keeps the workflow moving and the records up to date.

This repository is a reusable **skill**, not a job board or a collection of one person's application materials. It can be used with Codex or adapted for another AI agent that can read the instructions in `SKILL.md` and access the tools you authorize.

## What it covers

| Stage | What CareerPilot does |
| --- | --- |
| Set up | Builds a private candidate profile, search rules, resume routing, answer bank, and dashboard. |
| Find and screen | Finds roles, checks freshness and eligibility, and prioritizes jobs based on your goals and evidence. |
| Prepare | Selects a strong existing resume or tailors a new version without inventing experience. |
| Apply | Helps complete application forms and submits only within your authorization rules. |
| Interview and follow up | Prepares truthful interview examples, drafts follow-ups, and tracks employer responses. |
| Track | Records leads, submissions, blockers, interviews, offers, and outcomes in one place. |
| Improve | Uses results and recurring blockers to refine the search rules. |

CareerPilot works for different levels and fields. A student can configure internships and entry-level roles; an experienced candidate can prioritize senior roles and deeper evidence of ownership; a career changer can define transferable experience and target roles. The matching process does not assign anyone else's background or preferences to you.

## Quick start

1. Install the repository as an agent skill. For Codex, clone it into `~/.codex/skills/careerpilot/`, or copy the repository contents there.
2. Start a chat with: **“Use $careerpilot to set up my private job-search workspace and run a lead-finding trial.”**
3. Give the agent your target roles, location preferences, resume files, and any job-search rules you already know. It will draft the private profile and dashboard from `templates/` and ask focused questions for facts it cannot infer.
4. Review the first few recommended roles and adjust your rules. Authorize applications only when you are ready.

Keep the completed profile, dashboard, resumes, and application materials **outside this skill directory and outside a public repository**. The templates are blank starting points; your private workspace becomes the source of truth for future sessions.

## Make it yours

Your private workspace controls the workflow:

- `candidate_profile.json`: identity, experience, target roles, location, compensation, work authorization, sponsorship, and resume files.
- `application_rules.md`: jobs to prioritize, consider, skip, or hand off; account and submission rules.
- `resume_routing.md`: when to reuse a resume and when to tailor one.
- `answer_bank.md`: wording you have reviewed for repeated application questions.
- Dashboard: leads, attempts, outcomes, blockers, follow-ups, and lessons.

For example, a person who has confirmed U.S. permanent residence and does not need employer sponsorship might set this in their **private** profile:

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

This is only an example. A visa holder or candidate in another country sets different facts. CareerPilot leaves unknown fields unset and checks each form's actual wording before answering.

## Trust and control

- CareerPilot does not invent credentials, employment history, metrics, work authorization, or salary answers.
- It treats a saved job or clicked button as different from a confirmed submission.
- It hands CAPTCHA, login, 2FA, unclear legal questions, and missing materials back to you.
- Its first run defaults to finding and screening leads without submitting applications.
- Your rules decide whether the agent may submit a role or batch; you can require review before every application.

The available job boards, document editors, browser controls, and dashboards depend on the tools connected to your agent. CareerPilot provides the workflow and templates; you provide access and authorization for the services you choose.

## Repository map

- [`SKILL.md`](SKILL.md): the agent's main instructions.
- [`references/`](references/): setup, matching, application, and safety guidance.
- [`templates/`](templates/): blank private-workspace files and CSV dashboard templates.
- [`agents/openai.yaml`](agents/openai.yaml): Codex display metadata and starter prompt.

**Privacy:** Do not commit real resumes, contact details, immigration documents, account data, or application history. See [`references/safety-and-boundaries.md`](references/safety-and-boundaries.md).

## License

MIT. See [`LICENSE`](LICENSE).
