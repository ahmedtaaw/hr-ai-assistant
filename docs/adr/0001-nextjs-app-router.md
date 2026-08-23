# 0001: Next.js App Router

Decision: Use Next.js with the App Router (--app flag), TypeScript, Tailwind, src-dir structure.

Because: The project needs streaming AI chat responses — App Router's Route Handlers and Server Components have first-class support for streaming, which is harder to wire cleanly in the older Pages Router. TypeScript is a required qualification for the target role, not optional. Tailwind gives fast, utility-based RTL support (rtl: variants) without a separate CSS-in-JS setup.

Alternative considered: Vite + React Router — faster local dev server, but no built-in streaming/SSR story, and this project is explicitly practicing the Next.js skill set from the job description.