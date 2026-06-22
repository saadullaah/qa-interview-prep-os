# Commands Reference

All commands you can run in Claude Code, Claude Cowork, or Cursor.
Type any of these to trigger the relevant workflow.

---

## Getting Started

### `kickoff`
Start here if you are new to the system or starting a new job search.

The system will:
1. Ask you to share your resume or background
2. Build your candidate profile
3. Assess your starting point across all dimensions
4. Give you a prioritized action plan
5. Recommend your first session

---

## Mock Interviews

### `mock hiring-manager`
Starts a full mock interview with the Hiring Manager agent (Alex Chen).
Questions focus on: leadership, ownership, process, cross-functional skills, judgment.
Duration: 20-30 minutes. Ends with pass/fail verdict and session summary.

### `mock technical`
Starts a full mock interview with the Technical Interviewer (Priya Nair).
Questions focus on: QA fundamentals, test design, defect lifecycle, SDLC, Agile.
Duration: 25-35 minutes.

### `mock automation`
Starts a full mock interview with the Automation Interviewer (Marcus Webb).
Questions focus on: framework design, Selenium, Cypress, Playwright, API testing, CI/CD.
Duration: 30-40 minutes. May include live coding challenges.

### `mock behavioral`
Starts a full mock interview with the Behavioral Interviewer (Sarah Mitchell).
Questions focus on: STAR-format situational questions across 10 competency areas.
Duration: 20-30 minutes.

### `mock recruiter`
Simulates a recruiter screen with Jamie Torres.
Covers: background summary, motivation, salary discussion, positioning.
Duration: 15-20 minutes.

### `mock full-loop`
Runs a condensed version of all 4 technical rounds back to back.
Warning: This takes 90+ minutes. Do it when you want a full loop simulation.

---

## Drill Mode

### `drill [topic]`
Focused practice on a specific topic. Faster than a full mock — 15-20 minutes.

Available topics:
- `drill testing-pyramid`
- `drill defect-lifecycle`
- `drill test-design`
- `drill boundary-value`
- `drill selenium`
- `drill cypress`
- `drill playwright`
- `drill api-testing`
- `drill mobile-automation`
- `drill cicd`
- `drill performance-testing`
- `drill security-testing`
- `drill agile-qa`
- `drill bug-reporting`
- `drill test-cases`
- `drill salary-negotiation`
- `drill behavioral [competency]` — e.g., `drill behavioral conflict`

---

## Answer Scoring

### `score [your answer]`
Paste any answer you gave in a real or practice interview and get it scored across all 5 dimensions: Substance, Structure, Relevance, Credibility, Differentiation.

Example:
```
score When a developer tells me a bug is not reproducible, I first try to reproduce it myself using the exact steps from the bug report. If I can reproduce it, I screen record the steps and share the recording. If I cannot reproduce it, I check the environment — often the bug is environment-specific. I will document my reproduction attempts and the environments tested, then work with the developer to narrow it down.
```

---

## Story Bank

### `storybank`
Opens a story bank coaching session.
The system reviews all 12 required stories, checks which are written and practiced, and runs you through verbal practice on your weakest ones.

### `storybank [story name]`
Practice a specific story.
Example: `storybank bug-in-production` or `storybank conflict-with-developer`

---

## Interview Debrief

### `debrief`
Use this within 24 hours of a real interview.
The system will ask you:
- What questions were asked
- How you answered
- What you felt went well and poorly
- What the outcome was

It will then score your performance, identify patterns, and give you specific coaching for the next round.

---

## Negotiation

### `negotiate`
Triggers the Salary Negotiator agent (Dana Kim).
Share your offer details and get:
- Market comparison
- Negotiation strategy
- Exact scripts to use on the call
- Guidance on what to push for and what to accept

---

## Research

### `research [company name]`
Generates a QA-specific company research brief covering:
- Product complexity and quality risk areas
- Known tech stack and QA tools
- Engineering culture signals
- Recent company news
- Tailored questions to ask
- Most relevant stories from your story bank

Example: `research Stripe` or `research Shopify` or `research [your target company]`

---

## Status and Progress

### `status`
Gives you a full progress report:
- Sessions completed per agent
- Story bank completion status
- Drill history and scores
- Active interview loops
- Recommended next session
- Overall readiness assessment

### `gaps`
Shows only your identified weak spots and what to focus on next.
Faster than `status` for quick daily check-ins.

---

## Utilities

### `profile`
Opens your candidate profile for review and editing.

### `questions [interviewer type]`
Shows the full question bank for a specific agent without running the interview.
Use for passive review before a real interview.

Example: `questions hiring-manager` or `questions automation`

### `tips [topic]`
Quick tips for a specific scenario.
Example: `tips when I get a question I do not know` or `tips salary negotiation on a call`

### `reset`
Clears the coaching state and starts fresh. Use with caution.
