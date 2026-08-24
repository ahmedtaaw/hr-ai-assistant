# Project Context & Requirements

## Who
HR department members will use this system to chat with an AI assistant,
including asking about company documents (mocked — no real upload/retrieval yet).
Users speak Arabic and English. This is an internal-only tool — no internet
access, runs offline in-browser on the company intranet. Used on desktop
(Chrome, Firefox, Edge) and company tablets — not phones.

## MVP (build this month)
1. Login (mocked)
2. Dashboard
3. Chat with streaming responses — including mocked document-reference
   answers (e.g., "Based on the Employee Handbook, section 4.2...")
4. RTL/Arabic + English toggle

## Should-have (only if MVP lands early)
- Chat list
- Chat history
- Theme switcher + high contrast

## Cut (not this iteration)
- Real document upload / RAG retrieval
- User profile screen

## Non-functional bar
- Accessibility
- Perceived performance during streaming
- Basic auth security (mocked, but structured like the real thing)
- Usable on tablet viewport — no dedicated mobile layout needed

## Constraints
- 1 month, solo build
- No real backend — everything mocked

## Failure conditions
(if any of these happen, the project failed regardless of what else works)
- Doesn't run correctly in Chrome, Firefox, or Edge
- RTL/Arabic support is broken or bolted-on late
- Login doesn't work
- Chat doesn't work