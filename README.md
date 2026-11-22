
# LearnLoop
### Helping online learners decide what to study next.

LearnLoop is a product discovery and strategy case study exploring how online learners managing multiple courses can make better study decisions, prioritise competing deadlines, and maintain consistent learning habits.

The proposed solution is a personalised study-planning companion that recommends the next learning task based on deadline urgency, estimated effort, available study time, course priority, and learning progress.

**Project Type:** Product Discovery & Strategy  
**Role:** Product Management (Self-directed case study)  
**Research:** Secondary Research, Competitive Analysis, Learning Analytics  
**Dataset:** Open University Learning Analytics Dataset (OULAD)

---

## 1. Problem Statement

Online learners often manage multiple courses, assignments, deadlines, and study commitments simultaneously.

Even when learners know what they need to complete, deciding what deserves attention next can become difficult, particularly when:

- Multiple deadlines compete for attention.
- Available study time changes from day to day.
- Learners fall behind on planned coursework.
- Large assignments feel difficult to break into manageable tasks.
- Existing tools require learners to manually prioritise and organise their work.

**Core product question:**

> Given all my courses, deadlines, and available study time, what should I do next?

LearnLoop explores how a learning-specific recommendation experience could help learners turn competing commitments into manageable next actions.

## 2. Proposed Solution

LearnLoop is designed around one central capability: **Personalised Next-Task Recommendations.**

Instead of simply displaying a list of pending tasks, LearnLoop proposes to recommend a suitable next action by considering:

- **Deadline urgency:** How soon a task is due.
- **Estimated effort:** How much time the task requires.
- **Available study time:** How much time the learner can spend studying.
- **Course priority:** Which courses the learner wants to prioritise.
- **Learning progress:** Which tasks are incomplete, overdue, or in progress.

Each recommendation should explain why a task was selected and allow learners to override it.

## 3. Research & Discovery Approach

The project combines academic research, competitor analysis, public user evidence, and exploratory data analysis.

### A. Secondary Research

Reviewed academic research on:

- Self-regulated learning.
- Time management in online education.
- Learner motivation and effort regulation.
- Procrastination and online course engagement.
- Scheduling interventions in MOOCs.

The research helped establish the importance of planning, consistency, and effort regulation in online learning.

[Read Secondary Research](research/secondary-research.md)

### B. Competitive Analysis

Reviewed four existing products:

| Product | Primary focus |
|---|---|
| Google Classroom | Classroom and assignment management |
| Moodle | Learning management and course activities |
| Coursera | Online courses and learning progress |
| Notion | General-purpose organisation and task management |

**Identified opportunity:**

Existing products support course management, task organisation, deadlines, and progress tracking.

LearnLoop explores a more focused experience: helping learners decide which task to work on next based on their available time and learning commitments.

[Read Competitor Analysis](research/competitor-analysis.md)

### C. Public User Evidence

Reviewed publicly available learner discussions and academic evidence to explore difficulties involving:

- Managing multiple online courses.
- Maintaining consistent study schedules.
- Catching up after falling behind.
- Organising competing learning commitments.

Public discussions provide qualitative signals, not representative evidence of how common these problems are.

[Read Public User Evidence](research/public-user-evidence.md)

## 4. Data Analysis & Key Findings

To investigate early engagement and learning outcomes, I analysed the **Open University Learning Analytics Dataset (OULAD)**.

The dataset contains information about students, courses, assessments, registrations, and interactions with virtual learning environments.

### Dataset

The analysis primarily used:

- `studentInfo.csv`
- `studentRegistration.csv`
- `studentAssessment.csv`
- `assessments.csv`
- `studentVle.csv`
- `courses.csv`
- `vle.csv`

The large `studentVle.csv` file was processed in chunks to reduce memory usage.

### Key Finding 1: Student Outcome Distribution

Across 32,593 student-course records:

| Final outcome | Records | Percentage |
|---|---:|---:|
| Pass | 12,361 | 37.93% |
| Distinction | 3,024 | 9.28% |
| Fail | 7,052 | 21.64% |
| Withdrawn | 10,156 | 31.16% |

Withdrawal represented 31.16% of the records.

### Key Finding 2: Early Engagement and Withdrawal

I compared recorded VLE activity during the first 28 days of a course with final student outcomes.

| Final outcome | Zero early activity |
|---|---:|
| Distinction | 0.99% |
| Pass | 1.63% |
| Fail | 10.14% |
| Withdrawn | 37.02% |

A substantial proportion of withdrawn student-course records had no recorded VLE clicks during their first 28 days.

### Key Finding 3: Withdrawal Rates by Early Activity

I then examined withdrawal rates within each early-activity group.

| Early activity status | Records | Withdrawn | Withdrawal rate |
|---|---:|---:|---:|
| Some activity | 27,886 | 6,396 | 22.94% |
| Zero activity | 4,707 | 3,760 | 79.88% |

The withdrawal rate among zero-activity records was approximately 3.5 times the rate among records with some activity.

### Key Finding 4: Course-Level Comparison

The relationship between early inactivity and withdrawal was examined across seven course modules.

| Course | Some activity | Zero activity |
|---|---:|---:|
| AAA | 14.50% | 87.50% |
| BBB | 17.59% | 80.89% |
| CCC | 36.87% | 91.49% |
| DDD | 28.73% | 86.15% |
| EEE | 16.94% | 80.51% |
| FFF | 23.10% | 89.45% |
| GGG | 8.37% | 26.85% |

Zero early activity was associated with a higher withdrawal rate in all seven modules, although the size of the difference varied.

### Data Interpretation

These findings suggest that early engagement is an important area to investigate when designing support experiences for online learners.

However:

- The findings represent associations, not causal relationships.
- Zero recorded VLE clicks do not necessarily mean zero learning activity.
- OULAD contains historical data from one online university, not multiple unrelated learning platforms.
- The dataset does not include learners' available study hours.
- Student-course records should not be interpreted as unique individual students.

The analysis informs the product opportunity but does not validate LearnLoop's proposed solution.

[Read Product Discovery Report](docs/product-discovery-report.md)

[Explore the Jupyter Notebook](notebooks/01_oulad_data_exploration.ipynb)

## 5. Product Strategy

### Target Users

Online learners managing multiple courses alongside work, education, or other responsibilities.

### Primary Problem

Learners may struggle to decide what to study next when managing competing deadlines, varying study availability, and unfinished coursework.

### Product Opportunity

Help learners move from intention to action by recommending realistic learning tasks that fit their available time.

### Proposed Differentiation

LearnLoop focuses on:

1. Cross-course task prioritisation.
2. Workload-aware recommendations.
3. Explainable task selection.
4. Flexible planning when schedules change.

## 6. Minimum Viable Product (MVP)

The proposed MVP focuses on four core capabilities.

| Feature | Description |
|---|---|
| Course and Task Management | Add courses, tasks, deadlines, and estimated effort |
| Study Availability | Specify available study time |
| Next-Task Recommendation | Receive a recommended task based on workload and priorities |
| Progress Tracking | Mark tasks complete and monitor pending work |

### Out of Scope for the MVP

- Automatic integrations with every learning platform.
- AI-generated learning content.
- Advanced predictive models.
- Social learning features.
- Full calendar synchronisation.

## 7. Product Requirements & User Experience

The project includes:

- User journey mapping.
- User stories.
- Functional requirements.
- Non-functional requirements.
- Edge cases.
- Acceptance criteria.

The main user journey covers onboarding, adding courses, setting availability, receiving recommendations, completing tasks, and recovering from missed study sessions.

[Read User Journey](docs/user-journey.md)

[Read Product Requirements Document](docs/product-requirements.md)

## 8. Product Metrics & Experimentation

### North Star Metric

**Weekly Active Learning Days**

The number of distinct days in a week on which a learner completes at least one planned learning task.

### Supporting Metrics

- Task completion rate.
- Recommendation acceptance rate.
- Weekly active learning days.
- Onboarding activation rate.

### Guardrail Metrics

- Overdue task rate.
- Recommendation dismissal rate.
- User-reported workload stress.

### Proposed A/B Experiment

Compare two experiences:

| Control Group | Treatment Group |
|---|---|
| Standard deadline-sorted task list | Personalised next-task recommendations |

**Primary metric:** Task completion rate.

**Proposed duration:** Four weeks, subject to sample-size and statistical-power calculations.

The experiment has been designed but not conducted. These metrics and hypotheses require validation using real product usage data.

## 9. Limitations & Future Work

This is a self-directed product discovery and strategy case study, not a launched product.

The following work remains:

- Validate the problem through primary user research and usability testing.
- Test the recommendation experience using a clickable prototype.
- Refine recommendation ranking based on user feedback.
- Calculate experiment sample size and statistical power.
- Conduct a controlled experiment to measure actual product impact.
- Explore integrations with existing learning platforms.

The OULAD analysis is retrospective and cannot establish that LearnLoop would reduce student withdrawal.

## 10. Repository Structure

```text
LearnLoopProject/
│
├── README.md
│
├── data/
│   ├── README.md
│   └── oulad/                 # Local dataset files (not tracked)
│
├── docs/
│   ├── product-discovery-report.md
│   ├── portfolio-case-study.md
│   ├── product-requirements.md
│   └── user-journey.md
│
├── notebooks/
│   └── 01_oulad_data_exploration.ipynb
│
└── research/
    ├── secondary-research.md
    ├── competitor-analysis.md
    └── public-user-evidence.md
```

## 11. How to Reproduce the Analysis

1. Download the Open University Learning Analytics Dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/349/open+university+learning+analytics+dataset).
2. Extract the dataset.
3. Place the seven CSV files inside `data/oulad/`.
4. Open `notebooks/01_oulad_data_exploration.ipynb` in Jupyter Notebook or VS Code.
5. Install the required Python packages if they are not already available:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-posthocs
```

6. Run the notebook cells sequentially.

The raw dataset is excluded from GitHub because of its size. Download it separately before running the notebook.

---

## Project Status

**Completed:** Secondary research, competitor analysis, public evidence review, exploratory data analysis, product opportunity definition, MVP proposal, user journey, PRD, product metrics, and experiment design.

**Not completed:** Primary user validation, prototype testing, and live experimentation.

---

**Author:** Asmi Banthia  
**Project:** LearnLoop — Product Discovery & Strategy
