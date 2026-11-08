---
name: applypilot
description: A reusable job-search and application workflow. Use when a user wants to set up or continue a search, screen roles, route or tailor resumes, complete authorized applications, and track outcomes.
---

# ApplyPilot

ApplyPilot keeps a job search consistent across sessions. It uses a private candidate profile, application rules, resume routing, answer bank, and dashboard. The shared skill contains no candidate facts.

## Load the user's workspace

At the start of a task, find the user's configured workspace. Read its profile, rules, resume routing, answer bank, and dashboard before asking for facts or taking action. If no workspace exists, follow [setup-workflow.md](references/setup-workflow.md) and create private files from `templates/`. Never treat template defaults or another person's facts as the user's answers. User-confirmed workspace facts and rules take precedence over generic suggestions here.

The workspace must stay outside the public skill folder. Do not commit it or any generated application files to a public repository. If the location is unknown, ask the user for it or help create one.

## Core workflow

1. **Screen roles.** Apply the user's location, level, compensation, work authorization, sponsorship, and other rules. Prioritize fresh, viable roles. Before giving a top-tier match, use the [core-lever matching guide](references/resume-job-matching-and-tailoring.md) to check whether the user's approved evidence shows ownership of the job's main operating outcome. A missing resume bullet is a reason to inspect deeper approved evidence or ask a focused question, not proof the experience is absent.
2. **Choose materials.** Follow the user's resume strategy: `Volume` for strong existing variants, `Precision` for role-specific tailoring, or `Adaptive Precision` to check existing PDFs before editing the closest source resume. For selection or tailoring, use the [resume/JD comparison guide](references/resume-jd-comparison.md). Make only truthful changes, save a new version, export the required file format, and record the exact artifact used.
3. **Apply with authorization.** Read the [application playbook](references/application-playbook.md). Submit only within the user's explicit role, batch, or standing authorization. Resolve unclear legal, identity, sponsorship, compensation, and other high-impact questions with the user. Hand off CAPTCHA, anti-bot checks, login, 2FA, payments, and missing materials. Never bypass site controls.
4. **Record outcomes.** Update the dashboard after each lead or attempt. Use `Submitted` only after explicit confirmation; otherwise use `Pending`, `Needs user`, `Blocked`, or `Skipped` with the reason and next step. A first trial defaults to lead finding and dashboard updates without submission.
5. **Learn from blockers.** Record repeatable ATS and workflow lessons in the user's private rules and blocker queue.

## Candidate-specific conditions

Every user sets their own eligibility and preferences in `candidate_profile.json` and `application_rules.md`. Work authorization can be citizenship, permanent residence (green card), a visa, another status, or unknown. Store the user's exact current authorization and whether sponsorship is needed now or later; leave unknown fields unset. Do not infer one answer from another status label. Compare each posting and form's exact wording against the confirmed profile. If the match is unclear, mark `Needs user` and ask a focused question. Never copy a previous user's immigration or salary answers into a new workspace.

Read [safety-and-boundaries.md](references/safety-and-boundaries.md) for privacy, public sharing, and browser limits.
