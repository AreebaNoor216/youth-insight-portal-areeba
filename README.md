# 🌟 Youth Insight National Platform & Portal

[![Live Demo](https://img.shields.io/badge/🚀_LIVE_WEBSITE-CLICK_HERE_TO_VISIT-success?style=for-the-badge&logo=vercel&logoColor=white)](https://youth-insight-portal-areeba-gn9x.vercel.app)
[![Framework](https://img.shields.io/badge/Next.js_14-App_Router-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![Database](https://img.shields.io/badge/Prisma-SQLite-2D3748?style=for-the-badge&logo=prisma)](https://www.prisma.io/)
[![Styling](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Tests](https://img.shields.io/badge/Playwright-Verified_Pass-45ba4b?style=for-the-badge&logo=playwright)](https://playwright.dev/)

> **Live Production URL:** [https://youth-insight-portal-areeba-gn9x.vercel.app](https://youth-insight-portal-areeba-gn9x.vercel.app)  
> *The premier multi-university student leadership and civic engagement portal across Pakistan.*

---

## 🌐 Live Platform Overview

**Youth Insight Portal** is a production-grade full-stack web platform connecting campus leadership, executive reporting, public chapter registries, and flagship national events (Haripur, NUST, LUMS, FAST, and nationwide).

### 🔗 Quick Links
- 🌍 **Live Website:** [youth-insight-portal-areeba-gn9x.vercel.app](https://youth-insight-portal-areeba-gn9x.vercel.app)
- 🏛️ **Public Chapter Directory:** [View Chapters](https://youth-insight-portal-areeba-gn9x.vercel.app/chapters)
- 📅 **Flagship Events & Summits:** [View Events](https://youth-insight-portal-areeba-gn9x.vercel.app/events)
- 📊 **Executive Dashboard:** [Admin Portal](https://youth-insight-portal-areeba-gn9x.vercel.app/admin)
- 🔐 **President Login:** [Portal Access](https://youth-insight-portal-areeba-gn9x.vercel.app/login)

---

## ✨ Key Features & Architecture

1. **Public Campus Directory & Profiles (`/chapters`)**:
   - Filter chapters by province, university, and impact tier.
   - Interactive search with instant debounce and animated transition cards.
   - Detailed chapter showcase (e.g. Haripur University Chapter, NUST Islamabad, LUMS Lahore).

2. **President Portal & Activity Report Wizard (`/portal/dashboard`)**:
   - Multi-step report wizard for chapter presidents to log monthly civic drives, budget expenditures, and volunteer attendance.
   - Real-time client & server validation with Zod schemas.

3. **Central Executive Oversight Dashboard (`/admin`)**:
   - Nationwide statistics, total volunteers, verified events, and downloadable compliance records.
   - Role-based security (Super Admin, Central Cabinet, Chapter President).

4. **Event Registration & Ticketing (`/events`)**:
   - Dynamic event detail pages, seat booking, and guest speaker rosters.

---

## 🔐 Demo Credentials (For Reviewers)

| Role | Email | Password | Access Area |
| :--- | :--- | :--- | :--- |
| **Central Admin** | `admin@youthinsight.org` | `admin123` | Nationwide Admin Dashboard |
| **Haripur Chapter President** | `haripur.president@youthinsight.org` | `chapter123` | Haripur Chapter Reports & Submissions |
| **NUST Chapter President** | `nust.president@youthinsight.org` | `chapter123` | NUST Executive Submissions |

---

## 🛠️ Tech Stack

- **Frontend & Full-Stack:** Next.js 14 App Router (React 18, TypeScript)
- **Styling & UI:** Tailwind CSS, Lucide React, Framer Motion
- **ORM & Database:** Prisma ORM, SQLite database (`dev.db`)
- **Validation:** Zod Schema Validation
- **Authentication:** Custom JWT-compatible secure session cookies
- **Testing:** Playwright E2E Test Suite (Chromium automated test runner)
- **Cloud Hosting:** Deployed on Vercel Serverless Platform with Edge Optimization

---

## 💻 Local Setup & Development

```bash
# 1. Clone repository
git clone https://github.com/AreebaNoor216/youth-insight-portal-areeba.git
cd youth-insight-portal-areeba

# 2. Install dependencies
npm install

# 3. Generate Prisma client & seed database
npx prisma generate
npm run seed

# 4. Run development server
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

---
*Developed by Areeba Noor • Hosted on [Vercel](https://youth-insight-portal-areeba-gn9x.vercel.app)*
