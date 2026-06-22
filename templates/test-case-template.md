# Test Case Template

Use this when asked to write test cases in an interview.
Demonstrates structure, thoroughness, and systematic thinking.

---

## Test Case Format

**Test Case ID:** TC-[Module]-[Number] (e.g., TC-LOGIN-001)
**Test Case Title:** [Clear, one-line description of what is being tested]
**Module / Feature:** [e.g., Login, Payment, Search, Registration]
**Test Type:** [Functional / Negative / Boundary / Security / Performance / Usability]
**Priority:** [High / Medium / Low]
**Preconditions:** [What must be true before this test can run]
**Test Data:** [Specific data values needed]
**Steps:** [Numbered, exact actions]
**Expected Result:** [Specific, verifiable outcome]
**Actual Result:** [Filled in during execution]
**Status:** [Pass / Fail / Blocked / Not Run]
**Notes:** [Any relevant observations]

---

## Example — Login Feature Test Suite

### TC-LOGIN-001 — Successful login with valid credentials
**Type:** Functional — Positive
**Priority:** High
**Preconditions:** User account exists with email: testuser@example.com, password: Test@1234
**Test Data:** Email: testuser@example.com | Password: Test@1234

**Steps:**
1. Navigate to https://app.example.com/login
2. Enter email: testuser@example.com in the Email field
3. Enter password: Test@1234 in the Password field
4. Click the "Sign In" button

**Expected Result:** User is redirected to the dashboard (/dashboard). User's name appears in the top navigation. Session cookie is set.

---

### TC-LOGIN-002 — Login fails with incorrect password
**Type:** Functional — Negative
**Priority:** High
**Preconditions:** Valid user account exists: testuser@example.com
**Test Data:** Email: testuser@example.com | Password: WrongPassword123

**Steps:**
1. Navigate to login page
2. Enter valid email: testuser@example.com
3. Enter incorrect password: WrongPassword123
4. Click "Sign In"

**Expected Result:** Error message displayed: "Invalid email or password." User remains on login page. No session created.

---

### TC-LOGIN-003 — Login fails with empty email field
**Type:** Functional — Negative / Validation
**Priority:** High
**Preconditions:** None
**Test Data:** Email: [empty] | Password: Test@1234

**Steps:**
1. Navigate to login page
2. Leave the Email field empty
3. Enter password: Test@1234
4. Click "Sign In"

**Expected Result:** Inline validation error appears: "Email is required." Form does not submit.

---

### TC-LOGIN-004 — Login fails with empty password field
**Type:** Functional — Negative / Validation
**Priority:** High
**Test Data:** Email: testuser@example.com | Password: [empty]

**Steps:**
1. Navigate to login page
2. Enter valid email: testuser@example.com
3. Leave Password field empty
4. Click "Sign In"

**Expected Result:** Inline validation error: "Password is required." Form does not submit.

---

### TC-LOGIN-005 — Login fails with invalid email format
**Type:** Functional — Negative / Validation
**Priority:** Medium
**Test Data:** Email: notanemail | Password: Test@1234

**Steps:**
1. Navigate to login page
2. Enter invalid email format: notanemail
3. Enter password: Test@1234
4. Click "Sign In"

**Expected Result:** Validation error: "Please enter a valid email address." Form does not submit.

---

### TC-LOGIN-006 — Account lockout after multiple failed attempts
**Type:** Security / Functional
**Priority:** High
**Preconditions:** Account exists: testuser@example.com. System locks after 5 failed attempts.
**Test Data:** Incorrect password: WrongPass123 (used 5 times)

**Steps:**
1. Navigate to login page
2. Enter valid email: testuser@example.com
3. Enter incorrect password: WrongPass123
4. Click "Sign In"
5. Repeat steps 2-4 four more times (total: 5 failed attempts)
6. On 6th attempt, enter correct password: Test@1234

**Expected Result:** After 5th failed attempt, error message: "Account locked due to too many failed attempts. Try again in 30 minutes." 6th attempt with correct password also fails with lockout message.

---

### TC-LOGIN-007 — Password field masks input
**Type:** Security / UI
**Priority:** Medium

**Steps:**
1. Navigate to login page
2. Click in the Password field
3. Type any characters: abcde12345

**Expected Result:** Characters appear as dots or asterisks (●●●●●●●●●●). No plain text visible.

---

### TC-LOGIN-008 — "Remember me" checkbox retains session after browser close
**Type:** Functional
**Priority:** Medium
**Preconditions:** Valid user account exists

**Steps:**
1. Navigate to login page
2. Enter valid credentials
3. Check the "Remember me" checkbox
4. Click "Sign In"
5. Verify login succeeds
6. Close the browser completely
7. Reopen browser and navigate to the application

**Expected Result:** User is still logged in — directed to dashboard without needing to re-enter credentials.

---

### TC-LOGIN-009 — "Forgot password" link is present and functional
**Type:** Functional
**Priority:** Medium

**Steps:**
1. Navigate to login page
2. Observe presence of "Forgot password?" link
3. Click "Forgot password?"

**Expected Result:** "Forgot password?" link is visible on login page. Clicking it navigates to the password reset page (/reset-password).

---

### TC-LOGIN-010 — Login page is accessible via keyboard navigation only
**Type:** Accessibility
**Priority:** Medium

**Steps:**
1. Navigate to login page
2. Do not use mouse — keyboard only
3. Press Tab to move focus to Email field
4. Type valid email
5. Press Tab to move to Password field
6. Type valid password
7. Press Tab to move to Sign In button
8. Press Enter to submit

**Expected Result:** All form elements are reachable via Tab key. Focus order is logical (Email → Password → Sign In). Login succeeds via keyboard alone.

---

### TC-LOGIN-011 — Login form works on mobile (responsive)
**Type:** Compatibility / UI
**Priority:** High
**Test Data:** Device: iPhone 15 Pro / Chrome Mobile 122

**Steps:**
1. Open login page on mobile device/emulator
2. Verify layout renders correctly (no overflow, no cut-off elements)
3. Tap Email field
4. Verify keyboard appears
5. Enter valid email
6. Tap Password field
7. Enter valid password
8. Tap "Sign In"

**Expected Result:** Page renders correctly on mobile viewport. Keyboard appears on field tap. Login succeeds. No horizontal scroll required.

---

### TC-LOGIN-012 — Login is protected against SQL injection
**Type:** Security
**Priority:** High
**Test Data:** Email: ' OR '1'='1 | Password: ' OR '1'='1

**Steps:**
1. Navigate to login page
2. Enter SQL injection string in Email: ' OR '1'='1
3. Enter SQL injection string in Password: ' OR '1'='1
4. Click "Sign In"

**Expected Result:** Login fails. Error: "Invalid email or password." Application does not crash or expose database errors. No unauthorized access granted.

---

## What to Say When Writing Test Cases in an Interview

When given a feature and asked to write test cases, always cover these categories:

**Positive / Happy Path**
- The feature works as expected with valid inputs

**Negative / Validation**
- Empty fields, invalid formats, wrong data types

**Boundary Values**
- Minimum, maximum, and just outside the boundaries

**Security**
- SQL injection, XSS, auth bypass, session handling

**Performance**
- What happens at scale? Under slow network?

**Accessibility**
- Keyboard navigation, screen reader compatibility

**Compatibility**
- Cross-browser, cross-device, cross-OS

**State-based**
- Different user states (new user, existing user, admin, locked account)

**Usability**
- Is the error message helpful? Is the flow intuitive?

---

## Interview Tip

Before writing test cases, always say:

> "Before I write the test cases, let me understand the requirements. Can you tell me about the expected behavior, any validation rules, and the user types involved? I want to make sure my test cases are complete."

This signals mature QA thinking — you do not blindly start writing without understanding the scope.
