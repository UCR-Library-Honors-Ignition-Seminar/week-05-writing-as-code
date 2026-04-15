# Week 5: Writing as Code / Code as Writing

**Instructor:** Jing | **Weeks 5–8 format:** Critical/Creative Reflection

---

## Learning Objectives

- Understand how text and code share the same underlying logic
- Build a branching narrative using Twine
- Generate procedural text using Tracery grammars
- Read computational text critically — as a writer and as a user

---

## Background: When Writing Became Code

Long before graphical interfaces, writers and programmers were doing the same thing: writing rules that generated experiences.

**ELIZA (1966)** — Joseph Weizenbaum's program simulated a therapist by pattern-matching words in your sentences and reflecting them back. It had no understanding — only rules. Yet people formed emotional attachments to it. [Read more about ELIZA](https://github.com/oren/eliza-bot).

**Zork (1977)** — a text adventure where you typed commands (`go north`, `take lamp`) and the computer responded with prose. No graphics. Entirely text. It sold hundreds of thousands of copies. [Read more about Zork](https://github.com/MITDDC/zork).

**Twine** is an open-source tool for telling interactive and non-linear stories, similar to the storytelling experience by Zork and other interactive fiction games. And **Tracery** is a tool for writing *rules that generate text*, the same underlying idea as ELIZA, but for poetry, character descriptions, and bot voices.

---

## Session 1 (Day 1): Interactive Fiction with Twine

### Experience first

Before building, read one short piece of interactive fiction:

- [9:05](https://adamcadre.ac/if/905.html) by Adam Cadre — takes about 3 minutes; pay attention to how your assumptions about the story shift
- [Shade](https://www.eblong.com/zarf/zweb/shade/) by Andrew Plotkin — a surreal piece about a room that changes as you explore it
- Browse the [Infocom Games](https://github.com/historicalsource/) for more interactive fictions

**As you read, notice:** What choices does the author give you? What choices are hidden? When does the text feel like a story and when does it feel like a system?

### Build in Twine

See **[INSTRUCTIONS-TWINE.md](INSTRUCTIONS-TWINE.md)** for a full step-by-step guide.

**Quick reference — key Twine syntax (Harlowe format):**

| What you want | Syntax |
|--------------|--------|
| Link to a new passage | `[[Go left]]` |
| Link with custom label | `[[Open the door->Hallway]]` |
| Store a variable | `(set: $hasKey to true)` |
| Show text conditionally | `(if: $hasKey)[The door opens.]` |

**In-class activity:** Build a 3-passage/room story with at least 2 decision points and 2 different endings. It can be absurd, poetic, or purely functional — the goal is to feel what it means to write branching rules. You can start by drawing the storyline on a piece of paper or write all the story in paragraphs before translating into a game experience in Twine.

---

## Session 2 (Day 2): Generative Text with Tracery

### Experience first

Generative text is text written by a system following rules you define. Look at these examples:

- [Taroko Gorge Remixes](https://collection.eliterature.org/3/collection-taroko.html) — generative poems that run forever; refresh to see it change
- [Sea of Poe](https://seaofpo.vispo.com/) — kinetic and generative poetry
- [Tracery](https://github.com/galaxykate/tracery) – a story-grammar generation library for javascript
- Kate Compton's [Tracery tutorial](https://tracery.io/archival/crystalcodepalace/tracerytut.html) — shows how grammars/code produce text
  
**As you read, notice:** What stays the same across outputs? What varies? What would you have to change in the rules to make the output feel completely different?

### Build with Tracery

See **[INSTRUCTIONS-TRACERY.md](INSTRUCTIONS-TRACERY.md)** for a full step-by-step guide.

**Quick reference — Tracery syntax:**

```json
{
  "origin": ["The #adj# #noun# #verb# through the #place#."],
  "adj":    ["slow", "luminous", "broken", "recursive"],
  "noun":   ["archive", "signal", "voice", "corridor"],
  "verb":   ["drifts", "compiles", "surfaces", "echoes"],
  "place":  ["reading room", "terminal", "network", "silence"]
}
```

`#symbol#` pulls a random item from that list every time it runs. Combine symbols inside other symbols to build complexity.

**In-class activity:** Write a Tracery grammar that generates at least 3 types of output — try a character description, a place, and a short event. Run it 10+ times and screenshot outputs you find surprising.

### Voyant Tools — Optional Exploration

[Voyant Tools](https://voyant-tools.org) is a browser-based text analysis tool. Paste in any text (a novel chapter, song lyrics, your own writing) and it produces word frequency maps, collocations, and trend graphs.

It is not required for the project this week, but it is a useful lens: what does a computational reading of a text reveal that a human reading misses?

---

## Resources

### Tools
- [Twine](https://twinery.org) — use online, no account needed; click "Use in your Browser"
- [Twine Cookbook](https://twinery.org/cookbook/) — official reference with examples by format (Harlowe, Chapbook, SugarCube)
- [Tracery Editor and Visualizer](http://tracery.io/editor/) — paste your grammar and see it run
- [Kate Compton's Tracery Tutorial](https://tracery.io/archival/crystalcodepalace/tracerytut.html) — the creator's own walkthrough

### Further Reading
- *Twine Game Design* — [Allison Parrish's Twine guide](https://catn.decontextualize.com/twine/) (easy to follow tutorial)
- Zoe Quinn, *Depression Quest* — [play it free](http://www.depressionquest.com/); a Twine game about mental health
- [More Tracery Tutorial](https://www.andrewzigler.com/blog/sculpting-generative-text-with-tracery/)

---

## Assignment

See [ASSIGNMENT.md](ASSIGNMENT.md) for full requirements, options, and the reflection prompt.
