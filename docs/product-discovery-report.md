
# LearnLoop — Product Discovery Report

**Project Type:** Product Discovery & Learning Analytics  
**Product:** LearnLoop  
**Status:** Discovery Phase  
**Version:** 1.0

## 1. Product Overview

LearnLoop is a proposed learning-planning companion designed
to help university students manage multiple online courses.

It aims to bring course activities, deadlines and learning
progress into one place and help students decide what to
prioritise next.

The product focuses on three core activities:
- Organising multiple courses and their academic tasks.
- Prioritising learning activities based on deadlines and effort.
- Helping students recover when they fall behind.

## 2. Target Audience

University students enrolled in two or more online courses.

These students may have to manage:
- Lectures and learning materials.
- Assignments and quizzes.
- Examination schedules.
- Different course deadlines.
- Limited and changing study time.

## 3. Problem Definition

Students managing multiple online courses may struggle
to coordinate academic activities across different platforms.

Three potential problems have been identified:

1. Fragmented information:
   Course materials, deadlines and progress may be spread
   across different platforms.

2. Difficulty prioritising:
   Students may struggle to decide which academic activity
   deserves attention first.

3. Falling behind:
   Missing planned study sessions may create a backlog
   that becomes difficult to manage.

These are initial problem hypotheses and require further
investigation.

## 4. Product Vision

Help students manage their learning workload with clarity
and make consistent progress across multiple courses.

## 5. Proposed Solution

LearnLoop will explore four core capabilities:

1. Unified Dashboard
   A consolidated view of courses, deadlines and progress.

2. Study Planner
   A way to organise academic activities around available
   study time.

3. Next-Best-Task Recommendation
   A recommendation of what the student should work on next,
   based on urgency, effort and course priorities.

4. Catch-Up Mode
   A revised study plan when students miss planned activities.

## 6. Initial Product Hypotheses

H1: Students managing multiple courses experience difficulty
coordinating deadlines and learning activities.

H2: A consolidated view of academic workload can improve
students' visibility into upcoming commitments.

H3: Prioritised task recommendations can reduce the effort
required to decide what to study next.

H4: A catch-up plan may help students resume learning after
periods of inactivity.

These hypotheses are not yet validated.

## 7. Research Approach

The discovery process will use:

- Published academic research on online learning and
  self-regulated learning.
- Competitor feature analysis.
- Open University Learning Analytics Dataset (OULAD).
- Exploratory data analysis of student engagement,
  assessments and academic outcomes.

## 8. Success Metrics — Initial Candidates

- Weekly active users.
- Planned-task completion rate.
- Overdue-task rate.
- Catch-up plan completion rate.
- Recommendation adoption rate.
- Weekly and monthly retention.

These metrics will be refined after the product hypotheses
and proposed user experience are better understood.

## 9. Current Limitations

- The problem hypotheses have not been validated through
  primary user research.
- OULAD does not directly represent students coordinating
  multiple independent learning platforms.
- Historical learning activity cannot prove that a
  proposed product intervention will improve outcomes.
- Competitor capabilities require a detailed feature audit.

## 10. Next Steps

1. Conduct secondary research.
2. Analyse existing learning platforms and competitors.
3. Explore OULAD to understand student engagement patterns.
4. Identify evidence-backed user problems.
5. Prioritise product opportunities and define the MVP.
6. Finalise product metrics and discovery recommendations.



## 11. Primary problem to solve

**Target user:** Students enrolled in multiple online courses who struggle to begin or organise their learning.

**Primary problem:** Students may fail to establish a consistent learning routine early in a course, increasing their risk of disengagement.

**Evidence:** In the OULAD dataset, 79.88% of students with zero recorded VLE activity during their first 28 days eventually withdrew. The relationship was observed across all seven course modules.

**Product opportunity:** Help learners move from intention to action by recommending a realistic first study task based on their course deadlines, available time and progress.

**Initial product hypothesis:** If LearnLoop helps students identify and complete their next manageable learning task, it may improve early engagement and consistency.

**Important limitation:** The dataset does not establish that this intervention will reduce withdrawal. This needs to be tested with users.




## 12. Minimum Viable Product (MVP)

**MVP goal:** Help learners decide what to study next by recommending a manageable task based on their workload and available time.

### Core features

1. **Course and task management**
   - Manually add courses.
   - Add learning tasks and deadlines.
   - Track task completion.

2. **Study availability**
   - Set available study hours per day or week.
   - Update availability when schedules change.

3. **Next-task recommendation**
   - Recommend a task based on deadline urgency, estimated effort, course priority and available time.
   - Explain why the task is recommended.

4. **Progress tracking**
   - Mark tasks as completed.
   - View pending and overdue tasks.
   - See progress across courses.

### Out of scope for the first version

- Automatic integrations with every learning platform.
- AI-generated course content.
- Social learning and discussion features.
- Advanced predictive models.
- Full calendar synchronisation.

### MVP success hypothesis

If learners receive realistic, explainable study-task recommendations that fit their available time, they will be more likely to start and consistently complete learning tasks.



## 13. Next-task recommendation logic

LearnLoop will rank pending tasks using four factors:

1. **Deadline urgency:** Tasks with closer deadlines receive higher priority.
2. **Estimated effort:** Tasks should be realistic for the learner's available time.
3. **Course priority:** Learners can indicate which courses need more attention.
4. **Learning progress:** Incomplete or overdue tasks should be considered.

### Recommendation principles

- Prefer urgent tasks that fit the learner's available time.
- Avoid repeatedly recommending large tasks that the learner cannot complete in one session.
- Suggest smaller parts of larger assignments where possible.
- Explain why a task was selected.
- Allow learners to override recommendations.

### Example

If a learner has 40 minutes available:

LearnLoop may recommend the 30-minute Course A quiz because its deadline is tomorrow and it fits the available time.

It should not automatically recommend the 120-minute Course C assignment as the next task.

**Product principle:** The recommendation should be useful, realistic and explainable, rather than simply producing a ranked task list.

**Limitation:** The ranking logic is an initial product hypothesis. It must be tested with learners and refined using observed behaviour.



## 14. Product success metrics

### North Star Metric

**Weekly Active Learning Days**

The number of distinct days in a week on which a learner completes at least one planned learning task.

Why: This measures consistent learning behaviour rather than simply opening the application.

### Primary metrics

| Metric | Definition | What it measures |
|---|---|---|
| Task completion rate | Completed recommended tasks / Total recommended tasks | Whether recommendations lead to action |
| Recommendation acceptance rate | Recommendations accepted / Recommendations shown | Whether learners find suggestions relevant |
| Weekly active learning days | Average number of days per active learner with at least one completed task | Learning consistency |
| Onboarding activation rate | New users who add a course, set availability and complete their first task within 7 days / New users | Whether learners reach initial value |

### Guardrail metrics

| Metric | Why it matters |
|---|---|
| Overdue task rate | Recommendations should not cause learners to neglect other deadlines |
| Recommendation dismissal rate | High dismissal may indicate irrelevant recommendations |
| User-reported workload stress | The product should not increase pressure or anxiety |

### Measurement approach

Compare learner behaviour before and after introducing personalised recommendations. Where feasible, run a controlled experiment comparing the recommendation experience with a basic task-list experience.

**Important:** These are proposed product metrics, not results from the OULAD analysis. LearnLoop would need its own usage data to measure them.



## 15. Experiment design: Personalised task recommendations

### Objective
Determine whether personalised next-task recommendations improve learning-task completion compared with a basic task list.

### Experiment groups

| Group | Experience |
|---|---|
| Control (A) | Learners see their pending tasks in a standard list, ordered by deadline. |
| Treatment (B) | Learners receive personalised next-task recommendations based on deadline, effort, course priority and available study time. |

### Hypothesis

Learners using personalised recommendations will have a higher task completion rate than learners using a basic deadline-sorted task list.

### Primary success metric

Task completion rate:

Completed tasks / Total tasks due during the experiment period.

### Secondary metrics

- Weekly active learning days.
- Recommendation acceptance rate.
- Onboarding activation rate.

### Guardrail metrics

- Overdue task rate.
- Recommendation dismissal rate.
- User-reported workload stress.

### Experiment duration

Run the experiment for 4 weeks, allowing sufficient time to observe repeated learning behaviour.

### Decision criteria

- If task completion improves without worsening guardrail metrics, consider expanding the feature.
- If recommendations are frequently dismissed, investigate relevance and ranking logic.
- If there is no meaningful improvement, revisit the recommendation experience and underlying user problem.

**Limitation:** The experiment duration and metrics are initial proposals. Sample size and statistical power should be calculated before launching the experiment.

