# 🚀 LeetCoach – 1-Day Agile Sprint Plan

## 🗓 Sprint Goal

Build a functional MVP of **LeetCoach**, a personal LeetCode coaching app, that allows users to:

- Sign up and track their coding progress
- Get problem recommendations
- Submit solutions
- Receive AI-powered hints and feedback

---

## 🧩 Sprint Summary

| Sprint Duration | Team Size | Methodology | Tools                          |
|-----------------|-----------|-------------|--------------------------------|
| 1 Day (12 hrs)  | 1–3 Devs  | Agile Sprint | Vite, React, Node.js, Prisma, OpenAI API |

---

## 🏁 Sprint Backlog (Feature Breakdown)

### ✅ Core MVP Goals
| ID  | Task                                   | Time Est. | Owner     |
|-----|----------------------------------------|-----------|-----------|
| 1.1 | Setup project repo and tech stack      | 0.5 hrs   | Dev       |
| 1.2 | Create ERD & database with Prisma      | 1 hr      | Dev       |
| 1.3 | Implement user auth (Clerk/Firebase)   | 1 hr      | Dev       |
| 1.4 | Create dashboard layout (React)        | 1 hr      | Frontend  |
| 1.5 | Build "Problem of the Day" API         | 1 hr      | Backend   |
| 1.6 | Code submission form (editor + API)    | 1 hr      | Frontend  |
| 1.7 | Integrate OpenAI for code feedback     | 1.5 hrs   | Backend   |
| 1.8 | Store & display attempt history        | 1 hr      | Fullstack |
| 1.9 | Basic analytics (streak, solved count) | 1 hr      | Fullstack |
| 1.10| UI polish (loading, errors, UX)        | 1 hr      | Frontend  |

---

## 🧠 Stretch Goals (If time permits)

| ID  | Task                                       | Time Est. |
|-----|--------------------------------------------|-----------|
| S1  | AI hint levels (easy → hard)               | 1 hr      |
| S2  | Chat-based session history (AIMessage log) | 1.5 hrs   |
| S3  | Topic filter & focus settings              | 1 hr      |
| S4  | LeetCode data sync (static JSON fallback)  | 1 hr      |

---

## ⚙️ Tech Stack

| Layer      | Tool/Framework           |
|------------|--------------------------|
| Frontend   | React + Tailwind + Vite  |
| Backend    | Node.js + Fastify/Express |
| Database   | Prisma + PostgreSQL      |
| Auth       | Clerk.dev or Firebase    |
| AI         | OpenAI GPT-4o API        |
| Hosting    | Vercel / Railway         |

---

## ⏰ Timeline (One-Day Hourly Breakdown)

| Time Slot     | Focus Area                      |
|---------------|---------------------------------|
| 9:00–9:30 AM  | Repo setup + DB schema          |
| 9:30–10:30 AM | Auth + user model               |
| 10:30–12:00PM | Frontend: dashboard + problem UI|
| 12:00–1:00 PM | Backend: problem + attempt APIs |
| 1:00–2:00 PM  | Lunch break / debugging         |
| 2:00–3:00 PM  | AI feedback integration         |
| 3:00–4:00 PM  | Storing/submitting attempts     |
| 4:00–5:00 PM  | Analytics & streaks             |
| 5:00–6:00 PM  | UX polish + deploy to Vercel    |

---

## ✅ Definition of Done (DoD)

- User can sign up and log in  
- See a recommended problem (hardcoded or seeded)  
- Submit a solution (mocked or actual run)  
- Get GPT-generated feedback and store the attempt  
- See solved count and current streak on dashboard  

---

## 🚨 Risk Areas

- OpenAI API response delay or rate limits  
- LeetCode API limitations (use static JSON fallback)  
- Auth integration time (skip custom logic if blocked)

---

## 📦 Deliverables

- [x] GitHub repo with fullstack code  
- [x] Working web app deployed on Vercel/Railway  
- [x] `README.md` with install/run instructions  
- [x] `DATA_MODEL.md` and `SPRINT_PLAN.md`

---

