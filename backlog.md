# 📦 LeetCoach – Agile Backlog (Epics & User Stories)

This backlog supports the 1-day sprint plan to build the MVP of **LeetCoach**, a smart LeetCode coaching assistant. It is organized into Epics → User Stories with clear acceptance criteria for implementation.

---

## 🧩 Epic 1: User Authentication & Onboarding

### 🧑‍💻 User Story 1.1 – Sign up with email or OAuth
**As a** new user  
**I want** to sign up using email or Google  
**So that** I can create an account and save my progress

- ✅ Acceptance Criteria:
  - User can register using email/password or Google
  - User data is stored in the database
  - Duplicate emails are prevented

---

### 🧑‍💻 User Story 1.2 – Personalized onboarding
**As a** new user  
**I want** to select preferred topics and daily goals  
**So that** I can tailor the experience to my skill level

- ✅ Acceptance Criteria:
  - User can choose topics (Arrays, Graphs, etc.)
  - User can set a daily problem goal (1–5 problems)

---

## 🧩 Epic 2: Problem Recommendation & Solving

### 🧑‍💻 User Story 2.1 – View recommended problem
**As a** logged-in user  
**I want** to see a daily recommended LeetCode problem  
**So that** I know what to practice next

- ✅ Acceptance Criteria:
  - Problem title, description, difficulty are shown
  - Topics match user preferences
  - If solved, show next recommended problem

---

### 🧑‍💻 User Story 2.2 – Submit my code
**As a** user  
**I want** to submit my code for a problem  
**So that** the system can store my attempt and generate feedback

- ✅ Acceptance Criteria:
  - User selects a language and pastes code
  - Code is stored with a result (mocked or real)
  - Success/failure is recorded in attempt history

---

## 🧩 Epic 3: AI Coaching & Feedback

### 🤖 User Story 3.1 – Get AI-powered code feedback
**As a** user  
**I want** to receive GPT-based explanations of my code  
**So that** I can understand what's wrong or how to improve

- ✅ Acceptance Criteria:
  - Feedback is shown in a structured format
  - Can include tips, corrections, time/space analysis
  - Feedback is stored with the attempt

---

### 🤖 User Story 3.2 – Receive problem-solving hints
**As a** user  
**I want** to get AI hints if I’m stuck  
**So that** I can still make progress

- ✅ Acceptance Criteria:
  - Click “Need Hint” gives progressive hints (low → high)
  - AI remembers the current problem context

---

## 🧩 Epic 4: Progress Tracking & Analytics

### 📈 User Story 4.1 – View streaks and solved count
**As a** user  
**I want** to see how many problems I’ve solved  
**So that** I stay motivated

- ✅ Acceptance Criteria:
  - Dashboard shows current streak and total solved
  - Breaks in streak reset count
  - Updated on successful submission

---

### 📈 User Story 4.2 – Skill heatmap by topic
**As a** user  
**I want** to view my mastery level by topic  
**So that** I know where to improve

- ✅ Acceptance Criteria:
  - Heatmap or list view of topics (Arrays, Trees, etc.)
  - Mastery score calculated from correctness/attempts

---

## 🧩 Epic 5: UI & UX Foundation

### 🎨 User Story 5.1 – Use a clean, gamified dashboard
**As a** user  
**I want** a visual dashboard  
**So that** I can quickly navigate and track goals

- ✅ Acceptance Criteria:
  - Simple, responsive layout (desktop/mobile)
  - XP, streaks, and progress ring indicators
  - Dark mode enabled

---

## 🧩 Epic 6: DevOps & Deployment

### ⚙️ User Story 6.1 – Deploy MVP to cloud
**As a** developer  
**I want** to deploy the MVP to Vercel/Railway  
**So that** users can access it online

- ✅ Acceptance Criteria:
  - Site is publicly accessible
  - Environment variables for GPT keys are secure
  - GitHub repo includes setup instructions

---

## 🧩 Epic 7: Database & Schema Setup

### 🧱 User Story 7.1 – Implement Prisma schema
**As a** backend developer  
**I want** to create a database schema for users, problems, and attempts  
**So that** I can persist all user actions

- ✅ Acceptance Criteria:
  - Prisma schema file created
  - Models: User, Problem, ProblemAttempt, Feedback, AIHint, SkillProgress
  - DB migration runs successfully

---

## 🧩 Epic 8: AI Integration

### 🧠 User Story 8.1 – Use OpenAI for feedback
**As a** system  
**I want** to send user code to GPT-4  
**So that** I can return smart, contextual feedback

- ✅ Acceptance Criteria:
  - Input: code, problem, language
  - Output: AI-generated text with explanation
  - Error handling for API timeouts

---

## 🧩 Epic 9: Static Problem Source (MVP Shortcut)

### 🧾 User Story 9.1 – Load problems from static JSON
**As a** developer  
**I want** to use local problem data  
**So that** I don’t depend on LeetCode API for MVP

- ✅ Acceptance Criteria:
  - Local JSON includes ID, title, topic, difficulty
  - Loaded into dropdown or recommender service
  - Extendable in future

---

## 🗃 Backlog Notes

- Tag stretch stories with `S:` for future sprints
- Use labels: `frontend`, `backend`, `AI`, `DB`, `UX`, `infra`
- Prioritize Epics 1–4 for 1-day MVP sprint
- Track progress in Kanban tool (Trello, GitHub Projects, etc.)

---

