# OctaLoom's LinkedIn Bestie 💜

🇮🇱 [עברית](README.he.md)

**A Claude Code skill that turns a brain dump into LinkedIn posts in the writer's own voice.**

Works in Hebrew and English. No dependencies, no API keys, no setup beyond dropping a folder in place.

Built by [OctaLoom](https://octaloom.com). Free to use, fork and adapt.

---

## What it actually does

Most "write me a LinkedIn post" prompts produce the same post. Same rhythm, same three-word sentences, same "it's not X, it's Y", same closing question nobody answers. Readers recognise it in about two seconds and scroll.

This skill fixes that in three places:

**1. It refuses to write before it knows who is talking.**
Six questions about the voice owner, then three strategic questions about the idea itself. The answers to those three are what separate a post from filler, and skipping them is why most AI content reads interchangeable.

**2. It runs a voice gate on every draft.**
A growing list of the patterns that make writing read machine-generated: staccato rhythm, filler triads ("fast, simple, elegant"), "it's not X, it's Y", "not because X, but because Y", "and that's exactly why", sentences opening on a negation, em dashes, invented metrics. Every hit sends the draft back for a rewrite. The rhythm section on its own catches the tell that most writers never learn to hear in their own drafts.

The gate runs in both languages and each one has its own list, because the tells differ. English gives itself away on vocabulary ("delve", "leverage", "unlock"). Hebrew gives itself away on sentence order.

**3. It writes Hebrew as Hebrew.**
`references/hebrew.md` exists because Hebrew produced by translating English thinking is obvious to any Israeli reader, and the give-away is sentence order and rhythm rather than vocabulary. Gender consistency, gershayim, digits, how much English belongs inside a Hebrew sentence, which openers sound spoken.

It also runs the **Circulation Loop**: one raw idea becomes three posts that do different jobs. Curiosity to stop the scroll, Authority to prove you can do the thing, Vulnerability to make you worth trusting. Publishing only one of the three is the most common reason a good writer's feed goes flat.

---

## Install

Claude Code reads skills from `~/.claude/skills/`.

```bash
git clone https://github.com/octaloom-bit/linkedin-bestie.git \
  ~/.claude/skills/octaloom-linkedin-bestie
```

The folder name matters and the repo name does not. Claude Code reads the skill's identity from the `name:` field in `SKILL.md`, so clone into a directory called `octaloom-linkedin-bestie` as above.

Restart Claude Code. Then either:

- Type `/octaloom-linkedin-bestie`
- Or just say "write me a LinkedIn post about…" (or ״תכתבי לי פוסט ללינקדאין על…״) and it triggers on its own.

Project-scoped install works too: `.claude/skills/` inside a repo, if you want it available only for one client's folder.

---

## What's in the box

```
SKILL.md                    the protocol. STEP 0 through STEP 7
references/
  voice-gate.md             AI tells (universal) + the voice owner block
  hooks.md                  11 hook formulas, re-hook patterns, how to build a hook bank
  frameworks.md             8 body frameworks, post anatomy, content mix per voice owner type
  hebrew.md                 Hebrew that doesn't read translated
  formatting.md             line rules, CTA table, pre-publish checklist
  examples.md               skeletons + 3 worked examples with full analysis
```

Files load on demand rather than all at once, so a quick post doesn't drag the whole method into context.

---

## Making it yours

Three files carry everything specific to one voice owner. Edit those and leave the rest:

| File | What to change |
|---|---|
| `references/voice-gate.md`, Layer 2 | The voice owner block. This is the part that changes the output most. Fill it from their real posts, never from how they describe their own writing. |
| `references/examples.md` | Swap the fictional worked examples for the voice owner's three best posts, and write the analysis under each. |
| `references/frameworks.md` | Set the weekly Curiosity / Authority / Vulnerability split for their positioning. |

Everything else is method and travels between people unchanged.

---

## Where it stops

**It will not publish.** The skill hands back a draft and stops there, and you decide whether it goes up. There is no LinkedIn integration in this repo and there deliberately never will be.

**It will not invent your numbers.** If a post needs a metric you have not supplied, it ships `[missing number, verify]` in the draft (or `[מספר חסר, לאמת]` in Hebrew) and flags it in the delivery notes. An invented but plausible figure is the failure nobody catches, right up until someone asks about it in the comments.

---

## The numbers in this repo

Every platform figure in `formatting.md` and every content-mix percentage in `frameworks.md` is tagged `[rule of thumb]`, meaning it works in practice and nobody measured it on your audience. They come from the LinkedIn creator community and they change without notice.

After 20 posts your own data beats all of them. `hooks.md` has the template for logging it.

---

## Credits

Nothing here was invented from scratch. Two bodies of work sit underneath it.

**The LinkedIn method** is built on what **[Lara Acosta](https://www.linkedin.com/in/laraacostar)** has been teaching publicly about personal branding, and on the content work coming out of **[Kleo](https://kleo.so)**. The hook formulas, the re-hook, the five-layer post anatomy and most of the framework set trace back there. If you write on LinkedIn and you follow one person for it, follow Lara.

**If you write in Hebrew, go install [hebrew-writer](https://github.com/baldiga/hebrew-writer) by Amir Baldiga.** It is the first Hebrew-native writing skill for Claude Code and it goes deeper on Hebrew prose than `references/hebrew.md` here ever will: 55+ pattern detection, Israeli voice injection, voice cloning.

Earlier versions of this skill handed every Hebrew sentence straight to it, and the Hebrew thinking in this repo came out of working with it. The two install side by side and they do different jobs. This one plans the post and grades the voice. That one writes Hebrew that fools Israelis.

---

## License

MIT. Use it commercially, fork it, ship it to clients. Attribution appreciated and not required.

---

Built while running LinkedIn programs for Israeli B2B founders at [OctaLoom](https://octaloom.com).
If the skill is useful and you want the strategy behind it, that's what we do.
