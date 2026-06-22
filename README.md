# QA Interview Prep OS

A free, open-source multi-agent mock interview system for QA and Automation Engineers.


Runs in Claude Code, Claude Cowork, or Cursor.

---

## The Problem

QA and Automation Engineers are being laid off at scale. Interview prep resources are generic, shallow, and designed for engineers who have never stopped practicing. This is not that.

This system is built for experienced QA engineers who need to get back into interview shape fast — with real, tough, honest feedback that simulates what a real loop feels like.

---

## What Is Inside

### 5 Specialized Interview Agents

Each agent is a distinct persona with a specific role in the interview loop:

| Agent | Persona | What They Cover |
|---|---|---|
| **Hiring Manager** | Alex Chen — 14 years, 60+ hires | Leadership, ownership, process, judgment |
| **Technical Interviewer** | Priya Nair — Staff QA, 11 years | QA fundamentals, test design, SDLC, Agile |
| **Automation Interviewer** | Marcus Webb — Principal Automation, 13 years | Selenium, Cypress, Playwright, CI/CD, framework design |
| **Behavioral Interviewer** | Sarah Mitchell — People Partner + ex-QA lead | STAR-format, conflict, ownership, adaptability |
| **Recruiter** | Jamie Torres — 8 years technical recruiting | Screening, positioning, salary, first impression |

Plus a **Salary Negotiator** agent for offer evaluation and counter-offer scripting.

---

### 8 Templates

| Template | What It Is |
|---|---|
| Test Strategy Cheat Sheet | Everything you need to know cold before any interview |
| Automation Frameworks Guide | Deep reference: Selenium, Cypress, Playwright, Appium, API tools |
| Story Bank | 12 required STAR-format stories with prompts and practice tracking |
| Smart Questions to Ask | Questions that signal seniority and genuine interest |
| 30-60-90 Day Plan | For final rounds — what your first 90 days look like |
| Company Research Template | How to research a company's QA culture before your loop |
| Bug Report Template | How to write a great bug report in interviews |
| Test Case Template | Full test suite example for a login feature |

---

### Full Command System

Type commands like:
- `kickoff` — Start here
- `mock hiring-manager` — Full mock interview
- `drill cypress` — Focused topic drill
- `score [your answer]` — Get any answer scored
- `storybank` — Practice your behavioral stories
- `debrief` — Debrief a real interview
- `negotiate` — Salary negotiation coaching
- `research [company]` — Company research brief

See `commands/COMMANDS.md` for the full list.

---

## How To Use It

### Step 1 — Clone or Download

```bash
git clone https://github.com/[your-username]/qa-interview-prep-os.git
cd qa-interview-prep-os
```

Or download as ZIP and unzip.

### Step 2 — Open in Claude Code or Cursor

Open the folder in Claude Code or Cursor.

For Claude Code:
```bash
claude
```

### Step 3 — Fill In Your Profile

Open `candidate/my-profile.md` and fill in your background, target role, and goals.

### Step 4 — Say Kickoff

```
kickoff
```

The system will read your profile, assess your starting point, and give you a prioritized action plan.

### Step 5 — Practice

Pick your first agent and start. Use your microphone for mock interviews — you need to practice speaking your answers, not just writing them.

---

## Tips For Getting the Most Out of This

**Practice out loud.** Reading answers in your head is not practice. Speaking them is.

**Do not skip the behavioral agent.** Technical skills get you into the loop. Behavioral performance determines the offer.

**Use the debrief command.** After every real interview — good or bad — debrief immediately. The system learns your patterns and gets sharper.

**Customize your story bank.** The 12 stories are prompts. Fill them in with your real experience. Do not use generic examples.

**Read the cheat sheet the morning of your interview.** 20 minutes of focused review beats 3 hours of unfocused cramming.

---

## Free Forever

This costs nothing. It runs on Claude (claude.ai has a free tier) or any Claude API key.

If you want to use the Groq API instead (faster, completely free, no credit card):
1. Get a free Groq API key at console.groq.com
2. Update your Claude Code / Cursor settings to use Groq's Llama 3 model

Instructions for Groq setup: see `references/groq-setup.md`

---

## Credits

Inspired by Allison Davern's PM Interview Prep OS.
Built for the QA community.

If this helped you land a role, let me know. That is the only metric that matters.

---

## Contributing

Found a question that should be in the bank? A template that is missing? Open a PR.

This is a living document. The QA interview landscape changes — this should too.

---

## License

MIT — take it, fork it, make it yours.
