# Chandrakant Chodankar — Developer Portfolio

[![React](https://img.shields.io/badge/React-18.3-61DAFB?style=flat&logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?style=flat&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-13.4-black?style=flat&logo=framer&logoColor=white)](https://www.framer.com/motion/)
[![Supabase](https://img.shields.io/badge/Supabase-Database_%26_Auth-3ECF8E?style=flat&logo=supabase&logoColor=white)](https://supabase.com/)
[![Vercel](https://img.shields.io/badge/Deployed_on-Vercel-000000?style=flat&logo=vercel&logoColor=white)](https://vercel.com/)

A modern, responsive personal developer portfolio showcasing frontend and full-stack web applications, deep learning projects, and technical credentials. Built with a bespoke design system celebrating Goan architectural elements, smooth animations, and full accessibility support.

---

## ✨ Features

- **Distinctive Visual Identity**: Goan-inspired aesthetic featuring azulejo tile geometric circuit patterns, arched door frames, a warm laterite color palette, and a custom SVG cashew apple icon.
- **Light & Dark Themes**: Synchronous light/dark theme switcher powered by React Context, persisted in `localStorage` with fallback to system preferences (`prefers-color-scheme`).
- **Code-Split SPA Routing**: 10 routes managed via React Router v7 with dynamic `React.lazy()` imports and `<Suspense>` fallback loaders for minimal initial bundle sizes.
- **Micro-Interactions & Motion**: Scroll-triggered section reveals (`whileInView`), an interactive scroll trace progress indicator, animated page transitions, and a 30s infinite tech-stack marquee.
- **Full-Stack Contact Form**:
  - Direct PostgreSQL insertions into Supabase with Row Level Security (RLS).
  - Built-in spam honeypot and client-side character validation.
  - Automated transactional notification emails via a Supabase Deno Edge Function backed by the Resend API.
- **Protected Admin Dashboard (`/admin`)**: Master-detail inbox to review, update status (`new`, `read`, `replied`, `archived`), and manage contact messages with Supabase Email/Password authentication.
- **Comprehensive Case Studies**: Dedicated project detail pages with problem statements, architectural approaches, key features, challenge deep-dives, and GitHub/demo links.
- **Accessibility & Performance First**: Fluid `clamp()` typography, `prefers-reduced-motion` compliance across all CSS/JS animations, ARIA labeling, and skip-to-content links.

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: React 18 with TypeScript
- **Bundler & Tooling**: Vite 5, PostCSS, ESLint 9
- **Styling**: Tailwind CSS 3.4, `tailwindcss-animate`, HSL CSS Custom Properties
- **Animations**: Framer Motion 13
- **Routing**: React Router DOM v7
- **Icons**: Lucide React
- **UI Primitives**: Radix UI Accordion

### Backend & Cloud Services
- **Database & Auth**: Supabase (PostgreSQL with RLS policies)
- **Serverless**: Supabase Edge Functions (Deno runtime)
- **Email Service**: Resend API
- **Hosting & CI/CD**: Vercel (Single Page Application configured via `vercel.json`)

---

## 📂 Project Structure

```text
portfolio-main/
├── public/                     # Static assets (favicons, resume PDF, cover images)
├── src/
│   ├── components/
│   │   ├── layout/             # Layout components (Header, Footer, Layout, Section, ScrollTrace)
│   │   ├── ui/                 # Accessible UI components (Accordion)
│   │   ├── ContactForm.tsx     # Contact form with validation & Supabase integration
│   │   └── decorative.tsx      # Goan-themed SVG patterns, Monogram, and ArchFrame
│   ├── hooks/                  # Custom React hooks
│   ├── lib/
│   │   ├── content.ts          # Centralized data store (Projects, Experience, Skills, Site Info)
│   │   ├── supabase.ts         # Supabase client initialization
│   │   ├── theme.tsx           # Dark/Light theme provider & hook
│   │   └── utils.ts            # Class merging utility (clsx + tailwind-merge)
│   ├── pages/                  # 10 Route views (Home, About, Projects, Resume, Contact, Admin, etc.)
│   ├── App.tsx                 # Lazy-loaded route definitions & layout wrapper
│   ├── index.css               # Global typography, color tokens, and utility classes
│   └── main.tsx                # React DOM entry point
├── supabase/
│   ├── functions/
│   │   └── send-contact-email/ # Deno Edge Function sending emails via Resend
│   └── migrations/             # SQL migrations for contact_messages schema and RLS
├── vercel.json                 # SPA rewrite configuration for Vercel deployment
├── tailwind.config.js          # Extended Tailwind theme, fonts, and keyframes
├── vite.config.ts              # Vite configuration & path alias resolution (@/*)
└── package.json                # Dependencies and npm scripts
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (version 18.x or higher)
- npm or pnpm
- A free [Supabase](https://supabase.com/) account (optional, for contact form and admin dashboard)
- A free [Resend](https://resend.com/) account (optional, for email delivery)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ChandrakantChodankar/portfolio.git
   cd portfolio
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   Create a `.env` file in the root directory:
   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_PUBLISHABLE_KEY=your_supabase_anon_publishable_key
   VITE_SUPABASE_ANON_KEY=your_supabase_anon_publishable_key
   ```

4. **Start the local development server:**
   ```bash
   npm run dev
   ```
   Open `http://localhost:5173` in your browser.

---

## 📜 Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts the Vite development server with Hot Module Replacement (HMR). |
| `npm run build` | Runs TypeScript compilation (`tsc -b`) and bundles for production with Vite. |
| `npm run preview` | Locally previews the production build from the `dist/` directory. |
| `npm run lint` | Analyzes code for errors and formatting issues with ESLint. |
| `npm run typecheck` | Validates TypeScript types across the project without emitting output files. |

---

## 🌐 Deployment on Vercel

This project includes a pre-configured `vercel.json` ensuring seamless client-side routing on Vercel:

1. Push your repository to **GitHub**.
2. Go to [Vercel](https://chandrakantchodankar.vercel.app/) and click **Add New... → Project**.
3. Select your repository and configure:
   - **Framework Preset**: `Vite`
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
4. Under **Environment Variables**, add:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_PUBLISHABLE_KEY`
   - `VITE_SUPABASE_ANON_KEY`
5. Click **Deploy**.

---

## 📬 Contact & Connect

**Chandrakant Chodankar**  
*Entry-Level Software Developer · Goa, India*

- **LinkedIn**: [chandrakant-chodankar-b15344247](https://www.linkedin.com/in/chandrakant-chodankar-b15344247/)
- **GitHub**: [@ChandrakantChodankar](https://github.com/ChandrakantChodankar)
- **Email**: [chandrakantchodankar06@gmail.com](mailto:chandrakantchodankar06@gmail.com)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
