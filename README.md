# Quill

**AI-native document chat** — upload PDFs, talk to them with streaming answers, and keep context with vector search. A full-stack SaaS demo built on Next.js, with subscriptions, auth, and type-safe APIs end to end.

## What this project shows

- **Product surface:** marketing and pricing flows, authenticated app shell, drag-and-drop uploads, PDF viewing, and a chat UI with streaming responses and optimistic updates.
- **Monetization:** Stripe checkout and webhooks for free vs. paid tiers.
- **AI pipeline:** OpenAI for completions, LangChain for orchestration, Pinecone for embeddings and retrieval over uploaded documents.
- **Engineering:** App Router, shared types between client and server via tRPC + Zod, Prisma + MySQL, and Kinde for authentication.

## Stack

| Area | Choices |
|------|---------|
| Framework | Next.js 13 (App Router), React 18, TypeScript |
| API & data | tRPC, TanStack Query, Prisma, MySQL (e.g. PlanetScale) |
| UI | Tailwind CSS, Radix / shadcn-style components |
| Auth | Kinde |
| Files | UploadThing |
| AI | OpenAI, LangChain, Vercel AI SDK (`ai`) |
| Vectors | Pinecone |
| Billing | Stripe |

## Getting started

**Prerequisites:** Node.js 18.x and pnpm (or adapt commands for your package manager).

```bash
git clone <your-repo-url>
cd quill-master
pnpm install
```

### Environment

Create a `.env` (or `.env.local`) with:

```env
# Kinde
KINDE_CLIENT_ID=
KINDE_CLIENT_SECRET=
KINDE_ISSUER_URL=
KINDE_SITE_URL=
KINDE_POST_LOGOUT_REDIRECT_URL=
KINDE_POST_LOGIN_REDIRECT_URL=

# Database (MySQL — e.g. PlanetScale)
DATABASE_URL=

# UploadThing
UPLOADTHING_SECRET=
UPLOADTHING_APP_ID=

# OpenAI
OPENAI_API_KEY=

# Stripe
STRIPE_SECRET_KEY=
STRIPE_WEBHOOK_SECRET=

# Pinecone
PINECONE_API_KEY=
```

### Database

```bash
npx prisma generate
npx prisma db push
```

### Run locally

```bash
pnpm dev
```

## Scripts

| Command | Description |
|---------|-------------|
| `pnpm dev` | Development server |
| `pnpm build` | Production build |
| `pnpm start` | Run production build |
| `pnpm lint` | ESLint |



## License

[MIT](https://choosealicense.com/licenses/mit/)

## Acknowledgments

This project is based on material from **[Joscha Neske](https://www.youtube.com/@joshtriedcoding)**’s full-stack SaaS tutorial series. I used it as a foundation and learning base for experimenting with RAG-style document chat, Stripe, and a typed Next.js architecture.