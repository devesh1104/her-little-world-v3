This folder contains a minimal scaffold for a React / Next.js app where the provided Carousel component is placed.

It is NOT a full app yet. Follow the steps below to create a working Next.js + TypeScript + Tailwind + shadcn project and copy these files into it.

Recommended setup (run from the repository root):

1) Create a Next.js app with TypeScript
   npx create-next-app@latest react-app --ts --use-npm

2) Change into the app and install Tailwind
   cd react-app
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init -p

   // then follow the Tailwind setup: add the content paths in tailwind.config.js
   module.exports = {
     content: ["./pages/**/*.{ts,tsx}", "./app/**/*.{ts,tsx}", "./components/**/*.{ts,tsx}", "../**/*.{html,js}"],
     theme: { extend: {} },
     plugins: [],
   }

3) Install dependencies required by the component
   npm install motion class-variance-authority
   // also install peer deps: react, react-dom (already provided by create-next-app)

4) Copy the files from ../react-app/components and ../react-app/lib into the new app's /components and /lib folders. Ensure you place UI components under /components/ui (this is the shadcn default).

5) Install shadcn UI (optional but recommended for consistent structure)
   npx shadcn-ui@latest init
   // follow prompts to create /components/ui and theme files

6) Run the dev server
   npm run dev

Default component paths
- Components: /components/ui
- Utilities: /lib/utils.ts

Why /components/ui matters
- shadcn and many examples expect a consistent location for shared UI primitives. Keeping components in /components/ui makes imports predictable (e.g. import { Badge } from "@/components/ui/badge") and helps the shadcn CLI place generated components correctly.

Notes
- The carousel component expects the 'motion' package (Motion One React bindings). If you prefer framer-motion, the API differs and the component must be adapted.
- The cn utility uses a tiny join helper here; you can replace it with classnames or tailwind-merge if desired.

If you want, I can run the create-next-app and install dependencies here (it will take time). Reply if you'd like me to proceed with the full scaffold now.