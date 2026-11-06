# Adapting to the field

The core protocol stays the same: attempt → recall → review → gaps → card → apply → spaced reviews. What changes is **the question types**, **what counts as knowledge**, and **how to apply it**.

## Code and software development

**What to consolidate:** ideas and mechanisms (how async, an index or a cache works), architectural decisions and trade-offs, patterns, bug causes and how to find them, key library APIs — at the level of "what it can do and when you need it", not exact signatures.

**Don't consolidate:** exact syntax, flags, parameter names — those take seconds to look up.

**Question types:**
- **Explain the snippet:** "what does this piece do and why is it written this way?" (show 5–15 lines from the chat).
- **Predict behavior:** "what will this print / what happens if…?"
- **Why this and not that:** "why X instead of Y? What would Y have cost?"
- **Bug post-mortem:** "what caused the error? What signs would help you spot it next time?"
- **Write it yourself:** a small piece from scratch without looking at the chat (a function, a query, a config) — 5–20 lines, no more.
- **Transfer:** "what changes if the data grows 100×, requests arrive in parallel, or we switch databases?"

**Application:** use the pattern or approach in your own code within 24 hours; retype the key piece by hand instead of copy-pasting; find a place in your project where this technique would improve the code.

**Reviewing the user's code:** check logic and understanding, not style. A minor syntax slip with the right idea counts as "correct", with a short fix.

## Research

**What to consolidate:** main conclusions, what they rest on and how strongly, the research method, limitations, links to what the user knew before, open questions.

**Question types:**
- **The main conclusion in 2–3 sentences** in your own words (Feynman).
- **Evidence:** "what is this conclusion based on? How reliable — experiment, review, opinion?"
- **Fact or interpretation:** "what's established here, and what's someone's reading of it?"
- **Limitations:** "where might this conclusion not hold?"
- **Connections:** "how does this relate to <what the user knew / another source>?"
- **Transfer:** "how would you apply this to your task / project?"

**Application:** use the conclusion in your own work, writing or decision; explain it to a colleague; sketch a map of how the concepts connect.

## Languages (foreign languages, and programming languages as languages)

**Key:** production beats recognition. Not "what does this word mean" but "say / write it yourself".
**Questions:** translate from your native language, build a phrase in a new context, fix the error in a sentence.
**Application:** use the new words and constructions in a real message or conversation within 24 hours.
**Reviews:** Anki flashcards work especially well here.

## Business processes, systems, tools (CRM, integrations, automation)

**What to consolidate:** the sequence of steps and **why each step exists**, edge cases, where it usually breaks, how to verify it works.
**Questions:** "rebuild the process step by step", "what happens if step N is skipped?", "a client says <problem> — where do you look for the cause?", "explain this to a client in plain words".
**Application:** run the process yourself on a real task; explain it to a client or colleague.

## Math, algorithms, theory

**Key:** solve a **new** problem on the same principle, not the same problem again.
**Questions:** "why is this step valid?", "when will this method fail?", a problem with changed conditions, derive the key formula in your own words.
**Application:** solve 1–2 problems of a new kind; explain the idea without formulas.

## Decisions and reasoning (strategy, choices, plans)

**What to consolidate:** the criteria behind the decision, the alternatives considered and why they were dropped, the risks.
**Questions:** "what were the options and why this one?", "under what condition would you change your mind?", "what's the main risk and how will you track it?"
**Application:** use the same criteria in the next similar decision.
