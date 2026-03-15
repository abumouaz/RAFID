# Deploy RAFID (Option 1)

## 1) Backend on Render (PostgreSQL)

1. Create a Render Web Service and connect your GitHub repo.
2. Build command: `pnpm build`
3. Start command: `pnpm start`
4. Add environment variables:
   - `DATABASE_URL=<your-render-postgres-connection-url>`
   - `JWT_SECRET=your-secret`
5. Deploy.
6. Confirm health: `https://<render-url>/api/health` returns JSON.

## 2) Frontend on Vercel

1. Create a Vercel project and connect your repo.
2. Set project root to `client/`.
3. Set build command: `npm install && npm run build`.
4. Set output directory: `dist`.
5. Add environment variable:
   - `VITE_API_BASE_URL=https://<render-url>/api`
6. Deploy.
7. Your single public app URL is `https://<your-vercel-app>.vercel.app`.

## 3) Test

- Open deployed frontend URL.
- Click Enter Platform.
- Login with seeded user: `buyer@rafid.com` / `password` (or register new).
- Create request/listing and run Smart Matching.

## 4) Quick local run after config

- `npm run api` (backend)
- `npm run dev` (frontend)

---

**Note:** If deploying both as one app later (single host), serve built frontend from backend and use one URL.
