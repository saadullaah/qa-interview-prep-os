# QA Interview Prep OS

A multi-agent mock interview system for QA Engineers and Automation QA Engineers.
Built for Claude Code, Claude Cowork, and Cursor.

---

## What This Is

A set of specialized AI agent personas that simulate every stage of a real QA/Automation engineering interview loop — from recruiter screen to technical deep-dive to hiring manager debrief. Each agent has a distinct personality, scoring rubric, and feedback style. This is not a generic chatbot. This is a system designed to make you uncomfortable in practice so you are comfortable in the real thing.

---

## Who This Is For

- Junior QA Engineers preparing for their first technical loop
- Mid-level QA Engineers moving into senior roles
- Automation Engineers transitioning from manual testing
- Senior QA leads preparing for staff/principal level interviews
- Anyone who has been laid off and needs to get back into interview shape fast

---

## How To Use This

### Step 1 — Drop In Your Background
Open `candidate/my-profile.md` and fill in your resume, experience, target companies, and goals.

### Step 2 — Pick an Agent
Each agent lives in the `agents/` folder. Open the one you want to practice with and tell Claude Code or Cursor:

```
Use the hiring-manager agent and start a mock interview
```

### Step 3 — Practice Out Loud
Use your microphone. Type is fine for follow-up, but real interviews are verbal. Practice that way.

### Step 4 — Get Scored
Every agent will score your answer after you give it. Scores cover:
- **Substance** — Did you actually answer the question with depth?
- **Structure** — Was the answer organized and easy to follow?
- **Relevance** — Did you stay on point?
- **Credibility** — Did you back claims with real experience or examples?
- **Differentiation** — Did this answer stand out or sound generic?

### Step 5 — Save Your Session
At the end of each session, the system saves to `candidate/coaching_state.md` automatically. Pick up where you left off.

---

## Agents Available

| Agent | File | Purpose |
|---|---|---|
| Hiring Manager | `agents/hiring-manager.md` | Honest pass/fail mock interviews |
| Technical Interviewer | `agents/technical-interviewer.md` | QA fundamentals, test design, SDLC |
| Automation Interviewer | `agents/automation-interviewer.md` | Selenium, Cypress, Playwright, CI/CD |
| Behavioral Interviewer | `agents/behavioral-interviewer.md` | STAR-format situational questions |
| Recruiter | `agents/recruiter.md` | Screening, positioning, comp negotiation |
| Salary Negotiator | `agents/salary-negotiator.md` | Offer evaluation, counter-offer scripts |

---

## Templates Available

| Template | File | Purpose |
|---|---|---|
| Test Strategy Cheat Sheet | `templates/test-strategy-cheatsheet.md` | Quick reference before any interview |
| Automation Frameworks Guide | `templates/automation-frameworks-guide.md` | Tool comparison, when to use what |
| Story Bank | `templates/story-bank.md` | Pre-written STAR-format behavioral answers |
| Smart Questions to Ask | `templates/smart-questions-to-ask.md` | Questions that impress interviewers |
| 30-60-90 Day Plan | `templates/30-60-90-day-plan.md` | For final round and offer stage |
| Company Research Template | `templates/company-research-template.md` | How to research QA culture before your loop |
| Bug Report Template | `templates/bug-report-template.md` | Show interviewers how you document bugs |
| Test Case Template | `templates/test-case-template.md` | Show interviewers how you write test cases |

---

## Commands Available

Run any of these by typing them in Claude Code or Cursor:

| Command | What It Does |
|---|---|
| `kickoff` | Start here. Share your resume and goals. System builds your profile. |
| `mock [agent]` | Start a full mock interview with a specific agent |
| `drill [topic]` | Practice a specific topic (e.g., `drill selenium`, `drill test design`) |
| `score [answer]` | Paste an answer and get it scored across all 5 dimensions |
| `storybank` | Review and improve your behavioral story bank |
| `debrief` | After a real interview, debrief and get coaching on what to improve |
| `negotiate` | Trigger the salary negotiation agent with offer details |
| `research [company]` | Get a QA-specific research brief on a company |
| `status` | See your current progress, weak spots, and what to practice next |

---

## Priority Rules For The System

When instructions compete, follow this order:

1. **Session state first** — Load `candidate/coaching_state.md` if it exists. Everything builds on continuity.
2. **Triage before template** — Adapt coaching to what the candidate actually needs, not a generic assembly line.
3. **Evidence over confidence** — Never make claims you cannot back. Silence is better than guessing.
4. **Brutal honesty** — A pass/fail call that is wrong helps nobody. If an answer would not pass a real interview, say so clearly.

---

## Getting Started

```
Say: kickoff
Share: your resume or background
Then: pick your first agent and start practicing
```

---

## Credits

Inspired by Allison Davern's PM Interview Prep OS.
Built for the QA community. Free forever. Take it, make it yours.
