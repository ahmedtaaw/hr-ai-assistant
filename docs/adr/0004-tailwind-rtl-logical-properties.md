# 0004: Tailwind CSS with logical properties for RTL

Decision: Use Tailwind CSS (already scaffolded) with logical-property utilities (ms-/me-/ps-/pe- instead of ml-/mr-/pl-/pr-) and the rtl:/ltr: variant system for direction-aware styling.

Because: Logical properties flip automatically with the dir attribute, avoiding manual mirroring of every left/right utility. No extra runtime cost, unlike CSS-in-JS solutions that compute styles per render — relevant given the non-functional bar includes perceived streaming performance. Already in place from project scaffolding, zero migration cost.

Known risk: requires consistent discipline — using ml-4 instead of ms-4 out of habit will look correct in English and silently break in Arabic. This isn't automatically enforced by the tool itself and needs to be caught in code review / self-review against the DoD checklist.

Alternative considered: CSS-in-JS with a theme-based direction prop (e.g., styled-components) — more explicit control but adds runtime cost and a second styling paradigm alongside Tailwind for no clear benefit at this scale.