# 🚀 Youth Insight Portal — Live Deployment Guide (Website Ko Live Krne Ka Mukammal Tareeqa)

Yeh guide Roman Urdu aur English me wazeh karti hai ke **Youth Insight Portal** live kyun nahi ho raha tha, isme kya technical masle the jo fix kar diye gaye hain, aur ab isko **Vercel** ya **Render** par 2 minute me kaise live karna hai.

---

## 🔍 Pehle Website Live Kyun Nahi Ho Rahi Thi? (Root Cause Analysis)

Aapki website **Next.js 14 (App Router) + Prisma + SQLite Database (`dev.db`) + Server Actions (`'use server'`)** par bani hai. Yeh ek **Full-Stack Dynamic Web Application** hai (sirf static HTML page nahi hai).

### ❌ Masla 1: Netlify Drop ya GitHub Pages Par Chalane Ki Koshish
- Agar aapne is folder ko **Netlify Drop** (`app.netlify.com/drop`) par drag-and-drop kiya ya **GitHub Pages** par enable kiya, to ye **kabhi live nahi hoga**.
- **Wajah:** Netlify Drop aur GitHub Pages sirf static HTML/CSS files host karte hain. Unke paas Node.js backend server aur database nahi hota. Is liye wahan 404 ya "Deploy Failed" ka error aata hai.

### ❌ Masla 2: Vercel Par Build Script Me `prisma generate` Missing Tha
- `package.json` me build command sirf `"build": "next build"` thi.
- Jab Vercel ya cloud hosting code ko build karti thi, to Prisma Client generate nahi hota tha aur build crash ho jati thi:
  `PrismaClientInitializationError: Query engine library cannot be found`.
- **Fix:** Humne `package.json` ko update karke `"build": "prisma generate && next build"` aur `"postinstall": "prisma generate"` add kar diya hai.

### ❌ Masla 3: SQLite Database (`dev.db`) Tracing Missing Thi
- Next.js serverless functions by default `.db` files ko cloud bundle me copy nahi kartay.
- **Fix:** Humne `next.config.mjs` me `outputFileTracingIncludes: { '/**': ['./prisma/dev.db'] }` configure kar diya hai taake cloud par database file saath jaye.

---

## 🌐 Ab Website Ko Live Kaise Karein? (2 Sab Se Behtareen Tareeqay)

---

### 🟢 Tareeqa 1: Vercel Par Live Karein (Sab Se Tez & Free — 2 Minutes)

Next.js ko Vercel company ne hi banaya hai, is liye Vercel par ye sab se tez aur behtareen chalti hai:

1. Apne browser me **[vercel.com](https://vercel.com)** par jayein aur **GitHub** se Login / Sign up karein.
2. Dashboard par **"Add New..."** > **"Project"** par click karein.
3. Apna GitHub repository **`AreebaNoor216/youth-insight-portal-areeba`** select karein aur **"Import"** dabayein.
4. **Environment Variables** wale section ko expand karein aur ye 2 variables add karein:
   - **Key:** `DATABASE_URL` | **Value:** `file:./dev.db`
   - **Key:** `NEXTAUTH_SECRET` | **Value:** `youth-insight-secure-secret-key-2026-super-token`
5. **"Deploy"** button par click karein.
6. 1 se 2 minute me aapki website **100% LIVE** ho jayegi aur aapko free live link mil jayega (maslan `https://youth-insight-portal-areeba.vercel.app`)!

---

### 🟢 Tareeqa 2: Render.com Par Live Karein (Full Persistent Database — Free)

Render.com par Next.js real Node.js server ki tarah chalta hai jahan SQLite database me naya data (reports, login, events) permanent save rehta hai:

1. **[render.com](https://render.com)** open karein aur GitHub se login karein.
2. **"New +"** > **"Web Service"** par click karein.
3. Apna repository **`youth-insight-portal-areeba`** connect karein.
4. Settings me ye daalein:
   - **Name:** `youth-insight-portal`
   - **Region:** Frankfurt ya Singapore
   - **Branch:** `main`
   - **Runtime:** `Node`
   - **Build Command:** `npm install && npx prisma generate && npm run build`
   - **Start Command:** `npm start`
   - **Instance Type:** `Free`
5. **Environment Variables** me add karein:
   - `DATABASE_URL`: `file:./dev.db`
   - `NEXTAUTH_SECRET`: `youth-insight-secure-secret-key-2026-super-token`
   - `NODE_ENV`: `production`
6. **"Create Web Service"** par click karein. Aapki website live ho jayegi!

---

## 💻 Local PC Par Run Krne Ka Tareeqa

Agar aap apne laptop par test karna chahte hain:
```bash
npm run dev
```
Aur browser me **`http://localhost:3000`** open karein.

---

### 🔐 Demo Login Credentials:
- **Central Admin:** `admin@youthinsight.org` / `admin123`
- **Haripur Chapter President:** `haripur.president@youthinsight.org` / `chapter123`
- **NUST Chapter President:** `nust.president@youthinsight.org` / `chapter123`
