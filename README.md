# Build Your First Chatbot — One HTML File, No API Keys

Learn **how to build a chatbot** by owning one: [`chatbot.html`](chatbot.html) is a complete, working chatbot in a single file. No installs, no accounts, no API keys, works offline. Open it, chat with it, then edit its "brain" — because the whole brain is a list you can read.

Made by [Korra Academy](https://korra.academy/) — the team behind **[Korra.Bot](https://korra.bot/)**, live courses in practical AI skills.

## Try it (60 seconds)

1. Download [`chatbot.html`](chatbot.html) (Code → Download ZIP, or clone).
2. Double-click it — it opens in your browser.
3. Say hello. Ask it about Korra. Ask it something it doesn't know.

## How it works (the honest version)

This is a **rule-based chatbot**: it looks for keywords in your message and picks a matching reply from its `BRAIN` array. That's how chatbots worked for ~50 years, from ELIZA (1966) to most website "assistants" today — and understanding this makes modern AI *less* magical and more learnable:

- **Rule-based bot (this one):** `if message contains "price" → say the price line`. Predictable, private, tiny.
- **LLM chatbot (ChatGPT, Claude):** a neural network predicts the next word using patterns learned from massive text. Flexible, but needs a server and can be confidently wrong.

Build the first one and the second one stops being a mystery box.

## Teach it something (your first edit)

Open `chatbot.html` in any text editor and find `BRAIN`. Each entry is:

```js
{ keywords: ["homework", "study"],
  replies: ["Little and often beats cramming — 25 minutes, then a break."] }
```

Add your own entry, save, refresh the browser. You just programmed a chatbot. Ideas: make it answer FAQs for your club or business, give it a personality, add an easter egg for your friends.

## Teach it this: a two-rule quiz (worked example)

A rules bot can't calculate, but it *can* quiz you — one rule asks the question, another recognises the answer. Add these two entries to `BRAIN`:

```js
{ keywords: ["quiz me", "quiz", "test me"],
  replies: ["Quiz time! Capital of France? (Type your answer.)"] },

{ keywords: ["paris"],
  replies: ["Correct! 🎉 Now open the file and add a second question yourself.",
            "Yes — Paris. You just saw how a 'conversation' can be two unconnected rules."] },
```

Save, refresh, type `quiz me`, then answer. Two things you just learned by doing:

1. **Order matters.** The bot uses the *first* rule whose keyword appears in your message (look at the `for` loop in `reply()`), so put specific rules above general ones. If you had a rule for the single keyword `"quiz"` above the `"quiz me"` one, the longer phrase would never win — it would never even be checked.
2. **Keywords are substrings.** `"paris"` also matches inside "com**paris**on", so the bot will shout "Correct!" at odd moments. That false-positive problem is the core weakness of keyword matching — and one reason LLMs, which read whole sentences, took over.

The bot never actually knows a quiz is running — there's no state connecting the two rules. If you want it to only accept "paris" *after* asking the question, you need memory. The `userName` variable in the file is exactly that pattern; try adding a `quizAsked` variable the same way.

## Level up

1. **More patterns** — add 10 entries covering a topic you know.
2. **Memory** — the file shows how the bot remembers your name; extend the idea (favourite subject? last topic?).
3. **Connect a real LLM** — the final section of the file explains what changes when you swap the `BRAIN` lookup for an API call to a model like Claude, and why that needs a server so your API key never sits in a public page. That step is exactly what we teach live at [korra.bot](https://korra.bot/).

## FAQ

**Is this AI?**
It's classic symbolic AI (rules), not machine learning. Words like "AI" cover both; knowing the difference puts you ahead of most people using them.

**Why no API key or internet?**
So it runs anywhere, costs nothing, and 100% of its behaviour is readable in the file. First bots should be fully understandable.

**Can I use this for my website?**
Yes, MIT licence. For real customer support you'll outgrow rules quickly — but a rules bot answering your top 10 FAQs is a legitimate v1 (pair with our [ai-for-small-business-guide](https://github.com/korra-academy/ai-for-small-business-guide)).

**What should I learn next?**
JavaScript basics via [vibe-coding-starter-prompts](https://github.com/korra-academy/vibe-coding-starter-prompts), then how LLM APIs work.

---

### About Korra Academy

[Korra Academy](https://korra.academy/) runs live online tutoring across eight doors: [Kids](https://korra.kids/), [Study](https://korra.study/), [Career](https://korra.career/), [Business](https://korra.business/), [Tutor](https://korra.one/), [Training](https://korra.training/), [Bot](https://korra.bot/) and [Codes](https://korra.codes/). Want to build bots with a live instructor? Start at [korra.bot](https://korra.bot/). MIT licensed.
