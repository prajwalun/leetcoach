# 🧠 LeetCoach – Data Model

This document defines the database schema for **LeetCoach**, an intelligent LeetCode coaching platform. It includes all core entities, their relationships, and key field definitions.

---

## 📘 Entity Relationship Overview

- **User** owns many **ProblemAttempts**, has one **UserPreference**, many **SkillProgress**, and may participate in **CoachSessions**.
- **Problem** belongs to a **Topic**, and is attempted in many **ProblemAttempts**.
- **AIHint** and **Feedback** are linked to specific **ProblemAttempts**.
- **CoachSessions** are chat sessions between the user and the AI, made up of **AIMessages**.

---

## 📋 Table Definitions

### `users`

| Column         | Type      | Description                             |
|----------------|-----------|-----------------------------------------|
| id             | UUID (PK) | Unique user ID                          |
| email          | String    | Email address                           |
| username       | String    | Display name                            |
| leetcode_id    | String    | Optional LeetCode profile               |
| role           | Enum      | `student`, `admin`, `guest`             |
| created_at     | Timestamp | Account creation timestamp              |

---

### `auth_providers`

| Column         | Type      | Description                             |
|----------------|-----------|-----------------------------------------|
| id             | UUID (PK) | Unique auth ID                          |
| user_id        | UUID (FK) | Linked to `users.id`                    |
| provider_type  | Enum      | `email`, `google`, `github`             |
| provider_id    | String    | External provider identifier            |

---

### `problems`

| Column         | Type      | Description                             |
|----------------|-----------|-----------------------------------------|
| id             | UUID (PK) | Problem ID                              |
| title          | String    | Problem title                           |
| slug           | String    | URL slug                                |
| difficulty     | Enum      | `Easy`, `Medium`, `Hard`                |
| topic_id       | UUID (FK) | Linked to `topics.id`                   |
| source_url     | String    | Link to LeetCode                        |

---

### `topics`

| Column         | Type      | Description                             |
|----------------|-----------|-----------------------------------------|
| id             | UUID (PK) | Topic ID                                |
| name           | String    | Topic name (e.g. Arrays, Graphs)        |

---

### `problem_attempts`

| Column           | Type      | Description                           |
|------------------|-----------|---------------------------------------|
| id               | UUID (PK) | Attempt ID                            |
| user_id          | UUID (FK) | Linked to `users.id`                  |
| problem_id       | UUID (FK) | Linked to `problems.id`               |
| language         | String    | e.g., Python, Java                    |
| code_submitted   | Text      | Submitted code                        |
| result           | Enum      | `AC`, `WA`, `TLE`, `Runtime Error`    |
| runtime_ms       | Integer   | Runtime in ms                         |
| memory_mb        | Integer   | Memory usage in MB                    |
| attempted_at     | Timestamp | Time of submission                    |

---

### `ai_hints`

| Column             | Type      | Description                          |
|--------------------|-----------|--------------------------------------|
| id                 | UUID (PK) | Hint ID                              |
| problem_attempt_id | UUID (FK) | Linked to `problem_attempts.id`      |
| hint_level         | Enum      | `low`, `medium`, `high`              |
| content            | Text      | AI-generated hint                    |
| created_at         | Timestamp | Time generated                       |

---

### `feedback`

| Column             | Type      | Description                          |
|--------------------|-----------|--------------------------------------|
| id                 | UUID (PK) | Feedback ID                          |
| problem_attempt_id | UUID (FK) | Linked to `problem_attempts.id`      |
| type               | Enum      | `code_review`, `explanation`, `tip` |
| content            | Text      | GPT/Claude-generated feedback        |

---

### `user_preferences`

| Column           | Type      | Description                           |
|------------------|-----------|---------------------------------------|
| id               | UUID (PK) | Preference ID                         |
| user_id          | UUID (FK) | Linked to `users.id`                  |
| daily_goal       | Integer   | Daily problem goal                    |
| focus_topics     | JSONB     | Array of topic names                  |
| difficulty_pref  | Enum      | Preferred difficulty (`Easy`, etc.)   |

---

### `skill_progress`

| Column           | Type      | Description                           |
|------------------|-----------|---------------------------------------|
| id               | UUID (PK) | Skill progress ID                     |
| user_id          | UUID (FK) | Linked to `users.id`                  |
| topic_id         | UUID (FK) | Linked to `topics.id`                 |
| mastery_score    | Integer   | Mastery level (0–100)                 |
| last_practiced   | Timestamp | Last practice timestamp               |

---

### `streaks`

| Column           | Type      | Description                           |
|------------------|-----------|---------------------------------------|
| id               | UUID (PK) | Streak ID                             |
| user_id          | UUID (FK) | Linked to `users.id`                  |
| current_streak   | Integer   | Days in current streak                |
| longest_streak   | Integer   | Max days achieved                     |
| last_active      | Date      | Last active date                      |

---

### `coach_sessions`

| Column         | Type      | Description                             |
|----------------|-----------|-----------------------------------------|
| id             | UUID (PK) | Session ID                              |
| user_id        | UUID (FK) | Linked to `users.id`                    |
| started_at     | Timestamp | When the session started                |
| ended_at       | Timestamp | When it ended                           |

---

### `ai_messages`

| Column            | Type      | Description                           |
|-------------------|-----------|---------------------------------------|
| id                | UUID (PK) | Message ID                            |
| coach_session_id  | UUID (FK) | Linked to `coach_sessions.id`         |
| sender            | Enum      | `user`, `ai`                          |
| content           | Text      | Message body                          |
| created_at        | Timestamp | When it was sent                      |

---

## 🧩 Notes

- Index `problem_attempts(user_id, problem_id)` for fast lookups.
- Use `JSONB` for flexible topic preferences.
- Add full-text search support on `feedback.content` and `ai_hints.content`.
- Use Prisma or Sequelize to generate this schema easily if using Node.js backend.

---

