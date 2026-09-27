# Apple Notes Clone

A pixel-style **clone of the Apple Notes app UI**, generated with [v0](https://v0.app) and built on Next.js. It recreates the classic macOS/iOS Notes layout — sidebar with folders, a sortable note list, and a clean editor pane — running entirely in the browser.

> This is a UI/UX clone for demonstration and design-reference purposes. It is not affiliated with Apple.

## Features

- Sidebar with folders (Notes, Recently Deleted) and note counts
- Note list with title preview, date, and folder grouping
- Editor pane: view/edit note title and body
- Create new note, delete note, search across titles + content
- Responsive layout: sidebar collapses on mobile with back navigation
- Dark/light theming via `next-themes`

## Data & persistence

- Notes live in React state, seeded with sample data (shopping list, meeting notes, ideas, books, travel plans).
- **Nothing persists across reloads** — this is a front-end demo. To add persistence, wire `localStorage` (or a backend) into `components/notes-app.tsx`.

## Tech stack

- **Next.js 15.2.4** (App Router, single client component)
- **React 19**
- **Tailwind CSS 3.4** + tailwindcss-animate
- **shadcn/ui** (Radix primitives, cva, clsx, tailwind-merge)
- **Lucide icons**
- TypeScript

## Quick start

Requires Node.js 18+.

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Build & static export

Fully client-side (no API routes, no server actions) → static export:

```bash
npm run build          # writes static files to ./out
```

Serve `./out` with any static host (Cloudflare Pages, Netlify, GitHub Pages, `npx serve out`).

## Project structure

```
apple-notes-clone/
├── app/
│   ├── layout.tsx        # Root layout (fonts, metadata)
│   ├── page.tsx          # Renders <NotesApp />
│   └── globals.css
├── components/
│   ├── notes-app.tsx     # The entire app: folders, list, editor, search
│   └── theme-provider.tsx
├── components.json
├── lib/utils.ts          # cn() helper
├── public/               # Placeholder images (unused by the app)
├── styles/globals.css    # Legacy duplicate of app/globals.css
├── next.config.mjs       # images.unoptimized, output: 'export'
├── tailwind.config.ts
└── postcss.config.mjs
```

## Environment variables

None. No backend, no API keys.

## Roadmap ideas

- `localStorage` persistence
- Rich text (bold/italic/lists), pinning, attachments
- Real folder CRUD and iCloud-style sync

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
