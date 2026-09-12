# AI Empowerment Now

Practical AI systems for non-technical founders and business owners.
Built by **Tam Walsh** · [youtube.com/@AiEmpowermentNow](https://www.youtube.com/@AiEmpowermentNow)

---

# Install in 30 seconds

Open Claude. Paste these two lines, one at a time.

```
/plugin marketplace add AIEmpowermentNow/aioptimist
```

```
/plugin install ai-marketing-team@aioptimist
```

That's it. Now type:

```
/marketing-team
```

**On a paid Claude account, that's everything you need.** No downloads, no zip files, no setup.

---

## What you just installed

### AI Marketing Team

Give it one product or service. Forty-five minutes later you have five things, and you keep all of them.

| The hire | Minutes | What you get |
|---|---|---|
| **The Designer** | 10 | Your Design System. Colors, type, and social templates already built in your brand. |
| **The Strategist** | 8 | Your positioning. The exact buyer, the problem in her words, and the one line that makes someone pick you. |
| **The Scout** | 7 | Your White Space Map. What's crowded, what's contested, and the lane nobody's standing in. |
| **The Copywriter** | 8 | Your Hooks Database. Two dozen opening lines written for your product, scored and sorted. You pick one. |
| **The Producer** | 8 | Your campaign. On-brand posts, captions, and a Sizzle Reel from the hook you chose. |

Each one writes a file to a folder called `marketing-team/`. That folder is the point. It's what makes this repeatable instead of a one-time conversation.

---

## The three commands

| Command | What it does |
|---|---|
| `/marketing-team` | Start, or pick up where you left off |
| `/next` | Move to the next hire |
| `/where-am-i` | Lost? This catches you up and restarts you |

**If you get stuck at any point, type `/where-am-i`.** It reads what you've already built and puts you back on track.

---

## What you need

- A paid Claude account
- One product or service you want to sell. Not your whole business. One thing.
- Forty-five minutes

**Optional, for the video only:** a Magnific account. Without it you still get the complete shot list and every prompt, which you can film on your phone or run through any tool you already have.

---

## Doing it again tomorrow

Open Claude. Say **build my marketing team**. Point it at a different product.

It already knows your brand, so the second run takes about twenty minutes.

---

## Troubleshooting

**"It says the marketplace wasn't found."**
Check the spelling of the first command. It's one line, no spaces inside the repo name.

**"The command doesn't do anything."**
Refresh your browser and try `/marketing-team` again.

**"I don't have a product to use."**
Type `use the demo brand`. You'll run the whole system on a sample product, see how it works, and redo it with yours later.

**"My video won't generate."**
Expected if you don't have Magnific credits, and it's fine. You still have the full shot list. That's the valuable part.

---

## For developers

Standard Claude plugin marketplace. The plugin lives in `plugins/ai-marketing-team/`.

- `skills/` — six skills: the orchestrator plus five specialists
- `data/viral-patterns.md` — pre-analyzed short-form outlier research across nine business lanes. Refresh instructions are at the bottom of that file.
- `data/hook-craft.md` — the Four Corners hook framework
- `data/voice.md` — the voice every skill writes in
- `data/video-provider.md` — change one line to swap video engines
- `data/demo-brand.md` — the sample brand, plus ready-made rescue files

---

MIT licensed. Use it, fork it, teach it.
