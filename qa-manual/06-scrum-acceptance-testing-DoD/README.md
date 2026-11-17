# Module: The Definition of Done (DoD)

## Overview
The **Definition of Done (DoD)** is a shared, written agreement by the entire Scrum team (developers, testers, and 
Product Owner) that defines the minimum quality standard every user story must meet before it is considered complete and ready for release.
* **The Metaphor:** The DoD is the **floor, not the ceiling**. It establishes the lowest acceptable quality bar, not the ultimate perfection of a feature.
* **Team Contract:** It applies universally to all user stories across every sprint—not just a single feature.

---

## Standard Items in a Scrum Definition of Done
A typical DoD checklist includes:
* Code written and peer-reviewed by at least one other developer.
* Unit tests written and passing with no failures in the Continuous Integration (CI) pipeline.
* Acceptance criteria verified by a QA tester against agreed scenarios.
* No critical or high-severity defects left open.
* Documentation updated where applicable.
* Feature reviewed and approved by the Product Owner.

---

## Acceptance Criteria vs. Definition of Done

| Feature | Acceptance Criteria | Definition of Done (DoD) |
| :--- | :--- | :--- |
| **Scope** | Specific to a **single user story**. | Applies to **every user story** on the board. |
| **Question Answered** | "What does this specific story need to do?" | "What does every piece of work need to meet before leaving the team?" |
| **Nature** | Functional user-facing behavior. | System-wide quality, code review, and release readiness. |

> **Crucial Rule:** A user story can pass 100% of its Acceptance Criteria and still **fail** the DoD if technical
> requirements (like peer review or CI pipeline checks) are unmet. Both standards must be satisfied.

---

## How QA Enforces the DoD (Shifting Left)
QA acts as a quality champion, but accountability belongs to the entire Scrum team. Engagement happens continuously across the sprint:
1. **Backlog Refinement:** Review upcoming stories and flag unclear criteria (e.g., vague performance requirements like "load fast") *before* development begins.
2. **During the Sprint:** Track stories against the DoD checklist progressively rather than waiting until the final day.
3. **Before Sprint Review:** Confirm every "done" story has genuinely cleared every item on the DoD checklist. If not, it goes back.

# Module: Behavior-Driven Development (BDD) & Gherkin Syntax

## Overview
**Behavior-Driven Development (BDD)** is a collaborative approach that encourages teams to define a feature's requirements based on its expected behavior from the user's perspective *before* coding begins.
* **Core Purpose:** Closes the communication gap between technical (developers, QA) and non-technical (product owners, business analysts) team members using a shared, plain-language vocabulary.
* **Living Documentation:** BDD scenarios act as an up-to-date, plain-language record of how the system is supposed to behave, which can later be linked to automated test frameworks.

---

## The Given-When-Then (Gherkin) Format
BDD uses a structured, three-keyword syntax called Gherkin to write testable scenarios:

| Keyword | Purpose | Example |
| :--- | :--- | :--- |
| **Given** | The initial context, precondition, or starting state. | `Given the user is on the login page` |
| **When** | The specific action performed by the user. | `When the user enters valid credentials and selects Submit` |
| **Then** | The observable outcome or result that proves success. | `Then the user is redirected to their dashboard` |

* **The `And` Keyword:** Can be used to extend any clause (`Given`, `When`, or `Then`) with additional conditions without repeating the main keyword.

---

## From Vague Story to Testable Scenarios
Vague user stories (e.g., *"As a user, I want to authenticate securely"*) cause ambiguity and end-of-sprint bugs. QA drives clarification during backlog refinement by asking behavioral questions:
* *What are the validation rules?*
* *What error message appears on failure?*
* *What happens with blank inputs?*

### Example: Promo Code Application
* **Happy Path:**
    * **Given** the user is logged into their account
    * **And** a product has been added to their cart
    * **When** the user enters a valid promo code
    * **Then** they receive the specified discount on the chosen product

* **Negative Path:**
    * **Given** the user is logged into their account
    * **And** a product has been added to their cart
    * **When** the user enters an invalid promo code
    * **Then** the discount is declined and an invalid promo code message is displayed