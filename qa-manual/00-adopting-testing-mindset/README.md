# Lab: Adopting the Testing Mindset

*First lab from the **Software Testing Fundamentals and Methodologies** course by Microsoft.*

---

## 📌 Executive Summary & Objectives

This lab focuses on transitioning from a standard **builder mindset** to an analytical, **exploratory mindset**—learning to question assumptions, anticipate user errors, and look beyond happy-path scenarios.

### Key QA Principles & Mindset Shifts

* **Critical Evaluation:** Looking at software from the end-user's perspective to ensure usability, stability, and reliability.
* **Proactive Exploration:** Actively searching for edge cases, missing requirements, and boundary violations rather than assuming the system works just because it loads.
* **Discrepancy Tracking:** Accurately capturing the gap between **expected behavior** (what the specification requires) and **actual behavior** (what the application actually does).

---

## 🛠️ Practical Application (MindBridge Lab)

* **Environment Setup:** Successfully launched the MindBridge test environment locally (`http://localhost:3000`).
* **Seeded Defect Discovery:** Uncovered a deliberate validation flaw in the checkout module where non-numeric input is accepted in the zip code field.
* **Documentation:** Applied structured bug reporting techniques to document the defect, including steps to reproduce, expected results, and actual outcomes.

---

## 🐛 Bug Reports

### Report 1: Student Submission

* **Title:** The System is accepting the wrong zip-code and letting user to continue
* **Environment:** MindBridge (`http://localhost:3000`)
* **Severity:** High — This is a critical part of the payment process. If inaccurate data is submitted, the system must capture valid user credentials to ensure trace-ability and re-checking upon customer request.

#### Steps to Reproduce
1. Log in and add a course to the cart.
2. Navigate to the **Checkout** page.
3. Enter invalid characters in the Zip Code field (e.g., `WrongZip123@#`).
4. Attempt to complete the order.

#### Expected vs. Actual Results
* **Expected Result:** The application must only accept numeric zip codes. If invalid input is provided, the order must be rejected with a clear guide prompting the user to enter numbers only.
* **Actual Result:** The application accepted the invalid zip code and allowed the user to complete the payment.

> **Notes / Evidence:**  
> A robust checkout should reject a non-numeric zip with a clear error message such as *"Zip code must contain only numbers."* This missing validation is the seeded defect.

---

### Report 2: Solution Key Reference

* **Title:** Checkout accepts a non-numeric Zip code ("testing") and completes the order
* **Environment:** MindBridge (`http://localhost:3000`)
* **Severity:** Medium — Invalid delivery data is accepted, which can break fulfillment downstream and indicates missing input validation on checkout.

#### Steps to Reproduce
1. Log in at `http://localhost:3000` with the provided test account.
2. Add any course to the cart and open **Checkout**.
3. Leave the pre-filled card details in place.
4. Enter `testing` in the **Zip code** field.
5. Select **Place order**.

#### Expected vs. Actual Results
* **Expected Result:** The order is rejected with a validation error such as:
  > *"Zip code must contain only numbers."*  
  *(Note: A valid zip code should be a 5-digit number).*
* **Actual Result:** The order is accepted and a success message is shown (`Order ORD-… placed successfully…`), even though the zip code is non-numeric.

#### Recommendations
* The checkout module lacks a server-side check ensuring the zip code is numeric, allowing any text value to pass through.
* **Fix:** Add a 5-digit numeric format validation check before the order is confirmed.

---

## 🏗️ Roles of QA, QC, and UAT in the SDLC

| Role | Metaphor | Core Objective | Key Activities |
| :--- | :--- | :--- | :--- |
| **QA** *(Quality Assurance)* | The **Architect** | Process-oriented: Establishes standards and reduces defect likelihood before creation. | • Reviewing requirements<br>• Creating test strategies<br>• Defining standards<br>• Identifying risks & mapping strategies |
| **QC** *(Quality Control)* | The **Building Inspector** | Product-oriented: Identifies defects in the actual product once built. | • Executing test cases<br>• Reviewing product against specs<br>• Inspecting outputs & verifying product |
| **UAT** *(User Acceptance Testing)* | The **Final Buyer** | Validation-oriented: Final stage before release to ensure business value. | • Validating business requirements<br>• Supporting real user workflows<br>• Ensuring delivery of expected value |

### Tester's Scope of Exploration
Testing the application across different environments to identify failure points:
* **Special Characters:** Verifying input field boundaries and injection prevention.
* **Browser Compatibility:** Ensuring consistent behavior across major browsers.
* **Button Behavior:** Checking click handlers, loading states, and double-submission limits.

---

## ⚡ 7 Fundamental Testing Principles

1. **Testing Shows the Presence of Defects:** Testing can reveal that defects are present, but cannot prove that software is 100% defect-free.
2. **Exhaustive Testing Is Impossible:** Testing all combinations of inputs and preconditions is unfeasible. Focus efforts based on risk, usage frequency, and business impact.
3. **Early Testing:** The sooner defects are detected in the SDLC, the cheaper and faster they are to fix.
4. **Defect Clustering:** A small number of modules typically contain the majority of defects discovered during pre-release testing.
5. **Pesticide Paradox:** If the same tests are repeated over and over, eventually the same set of test cases will no longer find new bugs. Test suites must be continuously refreshed and varied.
6. **Testing is Context-Dependent:** Testing is performed differently in different contexts (e.g., e-commerce vs. safety-critical medical software).
7. **Absence-of-Errors Fallacy:** Finding and fixing defects does not help if the system built is unusable or does not fulfill user requirements and business goals.

---

## 👥 The RACI Matrix

The **RACI** model enables team members to understand their responsibilities and collaborate effectively:

* **R — Responsible:** The person who completes the task.
* **A — Accountable:** The person who makes the final decision and owns the outcome.
* **C — Consulted:** The subject matter expert who provides input and advice.
* **I — Informed:** The person kept updated on progress and outcomes.