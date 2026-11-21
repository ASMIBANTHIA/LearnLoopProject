
# LearnLoop — Product Requirements Document

## 1. Feature overview

**Feature:** Personalised Next-Task Recommendation

**Objective:** Help learners identify the most useful learning task to complete next based on their deadlines, available study time and learning progress.

## 2. User story

As an online learner managing multiple courses, I want LearnLoop to recommend a realistic next task so that I can make progress without manually deciding what to study every time.

## 3. Functional requirements

### FR1 — Task creation
- Users can add a task.
- Each task must have a title, associated course and deadline.
- Users can specify estimated effort.
- Users can update task details and completion status.

### FR2 — Availability management
- Users can enter available study time.
- Availability can be updated whenever their schedule changes.

### FR3 — Task recommendation
- The system considers pending tasks.
- It evaluates deadline urgency, estimated effort, course priority and available time.
- It recommends a suitable next task.
- It displays an explanation for the recommendation.

### FR4 — Recommendation controls
- Users can accept or dismiss a recommendation.
- Users can choose another task.
- Completed tasks should no longer appear as pending recommendations.

## 4. Non-functional requirements

- Recommendations should load quickly.
- User tasks and schedules should remain private.
- Recommendations should be understandable.
- The interface should work on desktop and mobile.

## 5. Edge cases

| Scenario | Expected behaviour |
|---|---|
| No pending tasks | Show a message that all tasks are complete |
| No available study time | Ask the learner to update availability |
| Task effort exceeds available time | Suggest a smaller task or a manageable portion |
| Multiple urgent tasks | Explain which task has priority |
| Missed deadline | Mark task as overdue and recalculate recommendations |
| Missing effort estimate | Ask the learner to estimate effort or use a clearly labelled default |

## 6. Acceptance criteria

The feature is ready for initial testing when:

- A learner can add tasks across multiple courses.
- A learner can enter available study time.
- LearnLoop can recommend a pending task.
- The recommendation includes a clear explanation.
- Completing a task updates the pending task list.
- The system handles the defined edge cases.

## 7. Out of scope

- Automatic integrations with all learning platforms.
- AI-generated study material.
- Predicting student withdrawal.
- Social learning features.
- Fully automated calendar management.

## 8. Open questions

- How should course priority be determined?
- Should learners be able to split large assignments into subtasks?
- How should the system handle tasks with missing deadlines?
- How much control should learners have over recommendation ranking?
