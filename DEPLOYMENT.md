# Deployment

This repository is a full Next.js app, not a static-only site. It uses server-side authentication, API routes, and external services, so deploy it to a Next.js host such as Vercel instead of GitHub Pages.

## Fastest Path

1. Open Vercel and import `mirzaraheel99/jobsresume`.
2. Keep the framework preset as Next.js.
3. Use `npm ci` for install and `npm run build` for build.
4. Add the environment variables from `.env.example` in the Vercel project settings.
5. Deploy the `main` branch.

## Required Environment Variables

```env
NEXT_PUBLIC_INSFORGE_URL=
NEXT_PUBLIC_INSFORGE_ANON_KEY=
NEXT_PUBLIC_POSTHOG_KEY=
NEXT_PUBLIC_POSTHOG_HOST=https://eu.i.posthog.com
OPENAI_API_KEY=
BROWSERBASE_API_KEY=
BROWSERBASE_PROJECT_ID=
ADZUNA_APP_ID=
ADZUNA_APP_KEY=
```

Do not commit real secret values to GitHub. Add them in Vercel project settings.

## GitHub Actions Deployment

The repository includes `.github/workflows/vercel-production.yml`. To use it, create these GitHub repository secrets after the Vercel project exists:

```text
VERCEL_TOKEN
VERCEL_ORG_ID
VERCEL_PROJECT_ID
```

After those secrets are set, pushes to `main` or manual `workflow_dispatch` runs will deploy production through Vercel.

## Local Start

```bash
npm ci
npm run dev
```

Then open `http://localhost:3000`.
