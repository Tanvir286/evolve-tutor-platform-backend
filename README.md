# 🎓 Evolve-Tutor-Platform

A comprehensive, scalable multi-role Learning Management System engineered to facilitate seamless online education. The platform empowers tutors to create structured subjects, schedule live Zoom sessions, and share learning materials, while students can enroll, attend live classes, and manage schedules. Complete with a robust Admin panel for revenue commissions, user moderation, and dispute management.

🔗 **Live Demo:** [live-link](https://www.evolvetutoring.ai)  
---
## 🌟 Role-Based Features

### 👨‍🏫 Tutor Features
* **Subject & Course Creation:** Create, organize, and structure custom subjects and curriculums.
* **Session Management:** Set up individual, group, or multi-week class sessions.
* **Live Scheduling with Zoom:** Schedule live lectures with integrated Zoom meeting links.
* **Study Material Hub:** Upload and distribute lecture notes, PDFs, assignments, and reference links.
* **Payment & Earnings:** View accrued session earnings, track payment statuses, and manage withdrawals.
* **Tutor Support Desk:** Direct support channel to resolve technical and operational issues.

### 👨‍🎓 Student Features
* **Subject Enrollment:** Browse subject directories, evaluate course syllabi, and enroll instantly.
* **Live Session Access:** Join scheduled live Zoom classes with a single click from the dashboard.
* **Schedule Change Requests:** Submit formal rescheduling requests for upcoming classes based on availability.
* **Secure Checkout:** Easy payment flow for subject enrollments and session bookings.
* **Student Support:** Integrated ticket system to report issues or ask for platform assistance.

### 🛡️ Admin Features
* **Analytics Dashboard:** High-level metrics on total active users, ongoing sessions, and platform cash flow.
* **Tutor & Student Management:** Review, approve, verify, and moderate tutor profiles and student accounts.
* **Session Oversight:** Real-time visibility and control over all scheduled, ongoing, and completed sessions.
* **Commission & Revenue Engine:** Configure dynamic platform commission rates and manage automated payouts.
* **Support & Dispute Center:** Resolve platform support tickets and mediate tutor-student disputes.
---

## 📊 Workflow & Permissions Matrix

| Features / Permissions | Tutor | Student | Admin |
|---|:---:|:---:|:---:|
| Create Subjects & Courses | ✅ | ❌ | 👁️ (Review) |
| Host Sessions & Zoom Classes | ✅ | ❌ | 👁️ (Monitor) |
| Join Live Classes | ❌ | ✅ | ❌ |
| Request Reschedule | ❌ | ✅ | 👁️ |
| Upload Learning Materials | ✅ | ❌ | ❌ |
| Manage Platform Commission | ❌ | ❌ | ✅ |
| Manage Support Tickets | 🎫 (Submit) | 🎫 (Submit) | 🛠️ (Resolve) |
---

## 🛠️ Tech Stack

* **Frontend:** Next.js (App Router) / React, TypeScript, Tailwind CSS ,
* **Backend:** Node.js, NestJS
* **Database:** PostgreSQL (Prisma)
*  **ORM:** Prisma
* **State Management:** Redux Toolkit & RTK Query
* **Authentication:** JWT with Role-Based Access Control (RBAC)
* **Payments:** Stripe
---
---

## Config

Stripe webhook:

```
http://{domain_name}/api/payment/stripe/webhook
```

for development run stripe cli:

```
stripe listen --forward-to localhost:4000/api/payment/stripe/webhook
```

trigger a event for testing:

```
stripe trigger payment_intent.succeeded
```

## Installation

Install all dependencies

```
yarn install
```

## Setup

Copy .env.example to .env and config according to your needs.

Migrate database:

```bash
npx prisma migrate dev
```

Seed dummy data to database

```
yarn cmd seed
```

## Running:

```bash
# development
yarn start

# watch mode
yarn start:dev

# production mode
yarn start:prod

# watch mode with swc compiler (faster)
yarn start:dev-swc
```
For docker:
```
docker compose up
```
## Api documentation
```
Swagger: http://{domain_name}/api/docs
```

