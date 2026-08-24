# 0005: Mock AI streaming via real ReadableStream

Decision: Implement mocked AI chat responses using a genuine Next.js Route Handler (/app/api/chat/route.ts) that returns a real streaming Response, dripping tokens server-side with a delay. Frontend consumes it via fetch + response.body.getReader(), not a client-only fake.

Because: The target job description explicitly lists "handling streaming tokens and long-running tasks" as a core responsibility. Faking text appearance client-side (e.g. setInterval over a canned string) would let me describe the concept in an interview but not demonstrate working code that actually consumes a stream, handles backpressure, or supports cancel-on-unmount. The real Route Handler approach costs roughly 1-2 extra hours over the fake, which is an acceptable trade against the 1-month constraint.

Alternative considered: Client-only fake streaming (setInterval word-reveal) — simpler and zero backend code, but doesn't transfer to real API integration skill and isn't defensible as "streaming experience" if asked to explain the implementation.