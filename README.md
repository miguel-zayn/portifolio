# Irakoze Patrick — Developer Portfolio

Modern responsive portfolio for Irakoze Patrick, built with React + Vite, Node.js/Express and Supabase PostgreSQL.

## Stack
- Frontend: React, Vite, custom responsive CSS, Lucide icons
- Backend: Node.js, Express, Helmet, CORS and rate limiting
- Database: Supabase PostgreSQL
- Admin: private project manager at `/admin`

**Database note:** Supabase uses PostgreSQL, not MySQL. This project uses Supabase PostgreSQL. The portfolio may display projects built with MySQL, but Supabase itself is PostgreSQL.

## Features
- About, skills, project showcase and contact sections
- Project list loaded from Supabase
- Contact form saves enquiries in Supabase
- Add, edit and delete projects from the admin page
- Admin API key stays on the backend
- Responsive mobile and desktop layout

## Setup
1. Install Node.js 18+ and create a Supabase project at https://supabase.com.
2. In Supabase Dashboard → SQL Editor, run `database/schema.sql`.
3. Copy `server/.env.example` to `server/.env`.
4. Add your Supabase Project URL, the **service_role** key, and a long random `ADMIN_API_KEY`.
5. Install and run from the root:

```bash
npm install
npm run install
npm run dev
```

Frontend: http://localhost:5173  
API: http://localhost:5000  
Project manager: http://localhost:5173/admin

Optional `client/.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

Never put the Supabase service-role key in a `VITE_*` variable or commit your `.env` file.

## Managing projects
Open `/admin`, enter the backend `ADMIN_API_KEY`, then add, edit or delete projects. The public portfolio reads the project list from Supabase.

## API
- `GET /api/health`
- `GET /api/projects`
- `POST /api/projects` (admin key required)
- `PUT /api/projects/:id` (admin key required)
- `DELETE /api/projects/:id` (admin key required)
- `POST /api/contact`

## Deployment
Deploy the React client to Vercel or Netlify and the Express server to Render or Railway. Set the production `VITE_API_URL`, backend `CLIENT_ORIGIN`, and Supabase environment variables in the respective hosting dashboards. Run the SQL schema once before publishing.

## Contact
Irakoze Patrick · Rwanda  
Email: patrickdavin07@gmail.com  
Phone: +250 790 644 668  
GitHub: https://github.com/miguel-zayn
