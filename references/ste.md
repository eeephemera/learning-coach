# ASD-STE100 — Simplified Technical English (condensed)

ASD-STE100 ("STE") is an international specification for controlled technical writing, maintained by the AeroSpace and Defence Industries Association of Europe. The current issue is Issue 8 (2021).

**The goal:** a text that every reader understands the same way, with no chance to misread it. STE achieves this with two parts:

1. **Writing rules** (~65 rules about words, sentences and procedures).
2. **A controlled dictionary** (~900 approved words with one meaning each, plus a list of non-approved words with approved replacements).

Learning Coach uses STE as its default "clear writing" baseline for explanations and knowledge cards. The full official spec lives at [asd-ste100.org](https://asd-ste100.org/).

## Rules that matter here (condensed)

### Words

- Use approved words from the dictionary. One word = one meaning.
- Use the same term for the same thing. Do not use synonyms for one concept (e.g., do not call the same thing "query", "request" and "fetch" in one text).
- Do not use words that can be read as two parts of speech in the same text.
- Do not use phrasal verbs ("put out the fire" → "extinguish the fire"; "carry out" → "do").
- Do not use slang, jargon or contractions ("don't" → "do not").
- Use technical names as written (e.g., "eager loading"). Define each new term once, then use the same name everywhere.

### Sentences

- Keep sentences short: ~20 words for instructions, ~25 for descriptions. One topic per sentence.
- One instruction per sentence in procedures.
- Prefer the simple tenses: present, simple past, simple future.
- Use the active voice.
- Keep articles and clarifying words: a, an, the.
- A noun cluster gets a maximum of 3 nouns ("engine oil pressure gauge" → "the gauge that shows the pressure of the engine oil").

### Procedures

- Numbered steps, imperative mood ("Do this", not "You should do this").
- Connect steps with "then" when the order matters.
- Put conditions before the instruction: "If X occurs, do Y."
- Warnings and cautions use the standard words WARNING / CAUTION.

## Before / after

| Not STE | STE |
|---|---|
| The pilot was able to bring the aircraft to a stop. | The pilot stopped the aircraft. |
| If there is a fire, don't use the elevator. | If a fire starts, do not use the elevator. |
| Carry out the inspection of the valve before starting up the engine. | Inspect the valve before you start the engine. |
| It should be noted that caching improves the latency of repeated requests. | Caching decreases the latency of repeated requests. |

## How Learning Coach uses STE

- **Explanations.** Write the "short explanation" step in STE: short sentences, one meaning per word, active voice. If you cannot say it simply and unambiguously, the gap in understanding is real.
- **Questions.** One question per sentence, unambiguous terms, conditions before the action.
- **Knowledge cards.** Write the questions and the answer key in STE, so a review in a new chat cannot be misread.
- **Retelling.** Ask the user to retell in STE style (Feynman + STE: simple AND unambiguous). If the user retells with vague words or synonyms, ask for the exact term.
- **Language note.** STE is defined for English. In other languages, apply the principles: short sentences, one word = one meaning, active voice, defined terms.

## Quick checklist for any explanation, question or card

- [ ] Short sentences (max ~25 words)
- [ ] One meaning per word, one term per concept
- [ ] Active voice
- [ ] No phrasal verbs, no contractions, no jargon
- [ ] New terms defined once, then used consistently
- [ ] Conditions before instructions ("If X, do Y")
