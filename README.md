# Learning Coach

A Claude skill that turns any topic or work chat into knowledge that sticks.

---

**You read it. It made sense. A week later it's gone.**

If any of these sound like you, this skill is for you:

- You read the explanation, it all clicked — and tomorrow you can't explain it yourself.
- You re-read the same chapter "just in case" and still forget it.
- You highlighted half the page and remember none of it.
- You got a great answer from Claude, trusted the chat to keep it... and the chat is the only place it lives.

That's not a bad memory. That's what plain reading does. Your brain strengthens what it *retrieves*, not what it sees. Reading feels like learning because the text looks familiar — but recognition is not recall. And with an AI it's even easier to fool yourself: Claude has the answer in front of it like a cheat sheet, so it can "know" everything it was told. You can't. You have to build the knowledge into your own memory.

Nothing new sticks just because you read it. It has to be **anchored in you**: retrieved, explained in your own words, applied, and revisited right when you're about to forget it. Otherwise it evaporates, no matter how many times you scroll up.

**Learning Coach makes Claude a coach instead of a lecturer.** You try first. You recall without scrolling up. Your mistakes get reviewed. And the questions come back at you after you've partly forgotten — exactly when coming back does the most work. What you want to remember, you actually remember.

## What it does

| Mode | When | What happens |
|---|---|---|
| **Learn a topic** | You want to learn something new | You attempt an answer, get a short explanation, then recall it in your own words |
| **Consolidate a chat** | Real work just happened in the chat | Claude picks 3–7 things worth owning (mechanisms, decisions, bug causes) and quizzes you on the ones you choose |
| **Review** | A reminder fired, or you paste a card into a new chat | Claude checks your answers against the card's key and sets a longer interval |

Learn and Consolidate sessions end with:

- **A knowledge card.** It carries its own questions and answer key, so a review works in any new chat.
- **One thing to apply** within 24 hours.
- **Review reminders** after 2–3 days and 7 days, then about 3 weeks later if your answers were confident. Claude uses your calendar connector if you have one. Otherwise, it gives you the dates and text to paste.

Questions adapt to the field: code, research, languages, business processes, math and decisions. The skill replies in your language.

**Explanations and cards follow ASD-STE100** (Simplified Technical English): short sentences, one word — one meaning, active voice. See [references/ste.md](references/ste.md).

It won't turn your work chat into a lesson. When a topic you showed interest in wraps up, Claude offers once to consolidate it. If you say no, it moves on.

## The loop

Every Learn and Consolidate session runs the same loop — the only difference is where the material comes from:

```mermaid
flowchart TD
    A["<b>Warm up</b><br/>Try to answer the question yourself,<br/>even a wrong attempt counts"] --> B["<b>Short explanation</b><br/>Core idea + one vivid example,<br/>in simple unambiguous language (STE)"]
    B --> C["<b>Active recall</b><br/>Answer 3–5 questions in your own words,<br/>without looking back"]
    C --> D["<b>Review</b><br/>What is right, what is wrong,<br/>what is missing"]
    D --> E["<b>Close the gaps</b><br/>Re-answer only what you missed"]
    E --> F["<b>Knowledge card</b><br/>+ apply it within 24 hours"]
    F --> G{"<b>Reminder</b><br/>2–3 days"}
    G -- "confident" --> H{"<b>Reminder</b><br/>7 days"}
    G -- "shaky" --> E
    H -- "confident" --> I{"<b>Reminder</b><br/>~3 weeks"}
    H -- "shaky" --> E
    I -- "confident" --> J["<b>It's yours</b>"]
    I -- "shaky" --> E
```

The interval grows while your answers stay confident; shaky answers loop back until the gaps close. Standalone versions: [docs/learning-loop.mmd](docs/learning-loop.mmd) (Mermaid source) and [docs/learning-loop.svg](docs/learning-loop.svg) (image).

## What a session looks like

An illustrative example of **Learn a topic** — one question, one loop, done in five minutes:

> **You:** Help me learn why the seasons change. I want this to stick.
>
> **Claude:** First, in your own words: why is it cold in winter and warm in summer? A guess is fine.
>
> **You:** We're closer to the Sun in summer?
>
> **Claude:** That's the usual guess — and it's wrong, which is useful to know. The Earth is actually slightly *closer* to the Sun in January. Here's the short version: seasons come from the tilt of the Earth, not from distance. The tilt makes the Sun's rays hit your hemisphere more directly in summer, and it makes the days longer. Both mean more heat.
> Now, in your own words, without scrolling up:
> 1. What causes the seasons?
> 2. Why does the tilt matter more than the distance?
> 3. When it's summer in one hemisphere, what season is it in the other?
>
> **You:** 1. The tilt of the Earth. 2. The light hits more directly. 3. Winter.
>
> **Claude:** 1 and 3 are right. 2 is half right: the angle matters, and so does day length — a tilted hemisphere gets both. Answer 2 again with both parts.
>
> **You:** The tilt makes the light hit more directly *and* makes the days longer. More sunlight in total.
>
> **Claude:** Exactly. That's the gap closed — here's your card.

The session ends with a card like this:

```
Topic: Why seasons change · created 2026-11-14
Context: my own question in a chat

Questions (answer without hints):
1. What causes the seasons?
2. Why does the tilt matter more than the distance to the Sun?
3. When it's summer in one hemisphere, what season is it in the other?

Answer key — don't look before answering:
1. The tilt of the Earth's axis.
2. The tilt changes two things at once: the sunlight hits more directly, and the days get longer. Distance changes almost nothing.
3. Winter.

Apply: explain it to someone in one minute today.
Reviews: 2026-11-17, 2026-11-21
```

## Install

### Claude Code

```bash
git clone https://github.com/eeephemera/learning-coach "$HOME/.claude/skills/learning-coach"
```

This command works in bash, zsh and PowerShell. If `~/.claude/skills` didn't exist when your session started, run `/reload-skills`.

To update:

```bash
git -C "$HOME/.claude/skills/learning-coach" pull
```

### Claude app (web and desktop)

1. Download [learning-coach.zip](https://github.com/eeephemera/learning-coach/releases/latest/download/learning-coach.zip). Don't unzip it.
2. Open **Customize > Skills**, click **+**, then choose **Create skill > Upload a skill** and pick the file.

Skills need code execution. If the upload isn't available, turn on **Code execution and file creation** (or **Create and edit files**) in **Settings > Capabilities**.

## Try it

- `Help me learn how database indexes work. I want this to stick.`
- `What did I learn from this chat? Quiz me.`
- `Let's review.` followed by your knowledge card

## Why it works

- **Recall beats rereading.** Testing improved delayed retention more than restudying ([Roediger & Karpicke, 2006](https://doi.org/10.1111/j.1467-9280.2006.01693.x)).
- **Trying first helps, even when the try fails** ([Kornell, Hays & Bjork, 2009](https://doi.org/10.1037/a0015729)).
- **Spacing beats cramming** ([Cepeda et al., 2006](https://doi.org/10.1037/0033-2909.132.3.354)).
- **Sleep supports memory consolidation** ([Rasch & Born, 2013](https://doi.org/10.1152/physrev.00032.2012)).
- **The overall ranking.** A review of ten study techniques rated practice testing and distributed practice as high utility, and rereading and highlighting as low utility ([Dunlosky et al., 2013](https://doi.org/10.1177/1529100612453266)).

The exact intervals and the 24-hour rule are practical defaults, not findings from these papers. [references/theory.md](references/theory.md) has the longer explanation that the skill gives to users.

## License

[MIT](LICENSE)
