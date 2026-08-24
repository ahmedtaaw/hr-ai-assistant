# 0003: Split state management — React Query + Zustand

Decision: Use React Query for chat history and session/auth check (mocked as server state). Use Zustand for the live streaming message buffer and UI state (locale/RTL toggle, theme).

Because: Chat history and session data conceptually resemble server state (fetched, cacheable, would come from a real API later) even though they're mocked — React Query's model fits, and it directly matches a skill named in the target job description. Live streaming tokens don't fit React Query's query/cache model well and are better handled as simple, fast-updating local state. UI state (locale, theme) is pure client state with no server analog at all.

Alternative considered: Zustand-only (simpler, but no React Query signal for the job target) or React Query-only (forces awkward handling of token-by-token streaming). Redux Toolkit was also considered but rejected as unnecessary boilerplate for a 4-screen, 1-month, solo MVP — it remains a reasonable choice only if the app were meaningfully larger or multi-team.

The split — React Query for chat history/session (mocked-as-server-state), Zustand for streaming buffer + UI state (locale, theme)