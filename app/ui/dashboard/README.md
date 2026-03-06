# Next.js Dashboard App

A modern dashboard application built with **Next.js (App Router)**, **Tailwind CSS**, and **PostgreSQL**, deployed seamlessly with **Vercel**. This project demonstrates server-side rendering, client-side navigation, and database integration.

---

## Features

* Dashboard with multiple pages: Home, Customers, Invoices
* Nested layouts and shared navigation
* Client-side routing with `<Link>` for smooth navigation
* PostgreSQL database integration via Vercel
* Database seeding and query handling
* Responsive design with Tailwind CSS
* Deployment-ready for Vercel with GitHub integration

---

## Getting Started

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd <repo-folder>
```

### 2. Install Dependencies

```bash
pnpm install
# or
npm install
```

### 3. Configure Environment Variables

1. Create a PostgreSQL database via [Vercel Storage](https://vercel.com/marketplace?category=storage) (Neon, Supabase, or your preferred provider)
2. Copy the `.env.example` to `.env`:

```bash
cp .env.example .env
```

3. Paste your database credentials from Vercel into `.env`
4. Ensure `.env` is included in `.gitignore` to keep secrets safe

### 4. Seed the Database

Start the development server:

```bash
pnpm run dev
```

Then seed the database in your browser:

```
http://localhost:3000/seed
```

You should see:

```
Database seeded successfully
```

### 5. Run the App

```bash
pnpm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view your dashboard.

---

## Project Structure

```
/app
  ├─ /dashboard
  │    ├─ layout.tsx       # Dashboard layout with shared navigation
  │    ├─ page.tsx         # Dashboard home
  │    ├─ /customers
  │    │    └─ page.tsx    # Customers page
  │    └─ /invoices
  │         └─ page.tsx    # Invoices page
  ├─ /ui
  │    └─ /dashboard
  │         └─ sidenav.tsx # Sidebar component
  ├─ /query
  │    └─ route.ts         # Example SQL query route
  └─ page.tsx              # Root home page
```

---

## Database

* **PostgreSQL** for relational data
* Seeded via `placeholder-data.ts` and SQL scripts
* Queries executed via Next.js route handlers
* Example SQL:

```sql
SELECT invoices.amount, customers.name
FROM invoices
JOIN customers ON invoices.customer_id = customers.id
WHERE invoices.amount = 666;
```

---

## Deployment

1. Push your repository to **GitHub**
2. Connect your GitHub repo in [Vercel](https://vercel.com/new)
3. Deploy the project with automatic preview URLs for pull requests
4. Environment variables are automatically managed via Vercel secrets

---

## Tech Stack

* **Next.js 16+ (App Router)**
* **React 18+**
* **Tailwind CSS**
* **PostgreSQL** (via Vercel Marketplace: Neon or Supabase)
* **Vercel** (hosting and deployment)
* **pnpm** (package manager)

---
