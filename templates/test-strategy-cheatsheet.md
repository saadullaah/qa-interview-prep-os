# Test Strategy Cheat Sheet

Quick reference for QA interviews. Print it. Read it before every loop. Know it cold.

---

## The Testing Pyramid

```
          /\
         /  \
        / E2E\          ← Few, slow, expensive, high confidence
       /------\
      /Integration\     ← Some, moderate speed, good coverage
     /------------\
    /  Unit Tests  \    ← Many, fast, cheap, isolated
   /----------------\
```

**The rule:** More unit tests, fewer E2E tests. The pyramid should not be inverted (more E2E than unit = fragile, slow, expensive).

---

## Testing Types — Know the Difference

| Type | What It Tests | When You Run It |
|---|---|---|
| Unit Testing | Individual functions/methods in isolation | Every commit, in CI |
| Integration Testing | How components work together | On PR merge |
| System Testing | Full application end-to-end | Before release |
| Regression Testing | That existing features still work after changes | Every release cycle |
| Smoke Testing | Basic critical paths to verify the build is stable | After every deployment |
| Sanity Testing | Narrow test of a specific fix or change | After a bug fix is deployed |
| Exploratory Testing | Unscripted investigation to find unexpected issues | During active development |
| Acceptance Testing (UAT) | That the product meets business requirements | Before sign-off |
| Performance Testing | Speed, load, and stability under stress | Pre-launch, periodically |
| Security Testing | Vulnerabilities, auth issues, data exposure | Pre-launch, periodically |
| Accessibility Testing | Compliance with WCAG standards | During development, pre-launch |
| Usability Testing | User experience quality | Design and pre-launch stage |
| Compatibility Testing | Cross-browser, cross-device, cross-OS behavior | Pre-launch |
| Localization Testing | Language, date formats, currency in different regions | Pre-international launch |

---

## Test Design Techniques

### Equivalence Partitioning
Divide inputs into groups that should behave the same way. Test one value from each group.

Example — age field (valid: 18-65):
- Partition 1 (invalid below): 0-17 → test with 10
- Partition 2 (valid): 18-65 → test with 35
- Partition 3 (invalid above): 66+ → test with 80

### Boundary Value Analysis
Test at the boundaries of valid ranges, not just the middle.

Example — same age field:
- Test: 17 (just below min), 18 (min), 19 (just above min)
- Test: 64 (just below max), 65 (max), 66 (just above max)

### Decision Table Testing
Used when there are multiple conditions with different combinations.

Example — discount calculation with conditions: member? (Y/N) + cart > $100? (Y/N):
| Member | Cart > $100 | Discount |
|---|---|---|
| Y | Y | 20% |
| Y | N | 10% |
| N | Y | 5% |
| N | N | 0% |

### State Transition Testing
Used for systems with states (e.g., order status: created → processing → shipped → delivered → returned).
Test valid transitions and invalid ones (e.g., can you go from created directly to delivered?).

### Error Guessing
Use experience and intuition to guess where bugs are likely:
- Empty inputs
- Null values
- Special characters in text fields
- Extremely long strings
- Concurrent operations
- Network interruptions mid-transaction

---

## Defect Severity vs Priority

| | High Priority | Low Priority |
|---|---|---|
| **High Severity** | Fix immediately — blocks users | Schedule fix soon — serious but workaround exists |
| **Low Severity** | Fix in current sprint — noticeable but not breaking | Fix in backlog — cosmetic or edge case |

**Severity** = How bad is the impact? (Data loss = critical, typo = minor)
**Priority** = How urgently must it be fixed? (Determined by business impact, not just technical severity)

---

## What Makes a Great Bug Report

Every bug report must include:

1. **Title** — Clear, specific, one sentence. "Login fails on Safari 16 with correct credentials" not "Login broken"
2. **Environment** — OS, browser, device, app version, test environment (staging/prod)
3. **Steps to Reproduce** — Numbered, exact, reproducible by anyone
4. **Expected Result** — What should happen
5. **Actual Result** — What actually happens
6. **Severity and Priority** — Your assessment
7. **Evidence** — Screenshot, video, logs, network trace
8. **Frequency** — Does it happen 100% of the time? Intermittently?
9. **Workaround** — Is there one?

---

## SDLC and QA Touchpoints

| SDLC Phase | QA Activity |
|---|---|
| Requirements | Review specs, flag ambiguities, define acceptance criteria |
| Design | Review architecture for testability, flag risks |
| Development | Write test plans, prepare test data, review unit tests |
| Testing | Execute tests, log bugs, track coverage |
| Release | Sign-off, smoke test post-deployment, monitor |
| Maintenance | Regression testing, monitoring production quality |

---

## Agile/Scrum QA Involvement

| Ceremony | QA's Role |
|---|---|
| Sprint Planning | Estimate testing effort, flag risks |
| Backlog Grooming | Review stories, add acceptance criteria, flag missing info |
| Daily Standup | Report test status, blockers, and risks |
| Sprint Review | Demonstrate test coverage and quality results |
| Retrospective | Contribute to process improvements around quality |
| Definition of Ready | Ensure stories have clear, testable acceptance criteria |
| Definition of Done | Include: tests written, tests passing, coverage threshold met |

---

## Key QA Metrics to Know

| Metric | What It Measures |
|---|---|
| Defect Density | Number of defects per size of software (e.g., per KLOC or feature) |
| Defect Escape Rate | Percentage of bugs found in production vs total bugs found |
| Test Coverage | Percentage of features/code covered by tests |
| Test Pass Rate | Percentage of tests passing in current suite |
| Mean Time To Detect (MTTD) | How quickly defects are found after introduction |
| Mean Time To Resolve (MTTR) | How quickly defects are fixed after discovery |
| Automation Coverage | Percentage of test cases automated |
| Flakiness Rate | Percentage of tests that produce inconsistent results |
| Regression Failure Rate | Percentage of regressions found per release |

---

## Common Interview Landmines — Know These Cold

**Q: What is the difference between QA and QC?**
- QA (Quality Assurance) = Process-oriented. Preventing defects through process improvement.
- QC (Quality Control) = Product-oriented. Detecting defects in the product.

**Q: What is shift-left testing?**
- Moving testing earlier in the SDLC — involving QA in requirements and design, not just at the end.

**Q: What is a test plan vs a test strategy?**
- Strategy = High-level approach to quality for the project (scope, objectives, tools, risks)
- Plan = Specific, detailed plan for a particular test cycle (what to test, who, when, how)

**Q: What is the difference between verification and validation?**
- Verification = Are we building the product right? (Does it match the spec?)
- Validation = Are we building the right product? (Does it meet the user's needs?)

**Q: How do you handle testing with no requirements?**
- Talk to stakeholders, reverse-engineer from existing behavior, use industry standards and common sense, document assumptions, test based on user goals not just feature specs.
