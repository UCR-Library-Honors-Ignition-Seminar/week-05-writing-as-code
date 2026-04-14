# Week 5: Writing as Code / Interactive Fiction

**Instructor:** Jing

---

## Learning Objectives

- Understand how text and code share the same underlying logic
- Build a branching narrative using Twine
- Generate procedural text using Tracery grammars
- Analyze a text corpus with Voyant Tools

---

## Introduction: When Writing Becomes Code

Before graphical programs existed, people were using text as code. ELIZA (1966) was a chatbot that simulated a therapist by pattern-matching phrases. Zork (1977) was an adventure game running entirely on text commands. Twine is a direct descendant — except you're the author.

When you write a Twine story, you're writing rules: *if the player goes left, show this text; if they have the key, unlock this door.* The boundary between author and programmer starts to blur.

---

## Session 1 (Day 1): Twine & Historic Bots

### Twine — Branching Narrative
Browser-based, no account needed: [twinery.org](https://twinery.org) > "Use it online"

**Key syntax:**
- `[[link text]]` — creates a link to a new passage
- `[[link text|passage name]]` — links to a named passage

**Starter example (paste into a passage):**
```
You wake up in a strange library. The shelves go up forever.

[[Open the nearest book]]
[[Walk toward the exit]]
[[Call out for help]]
```

**Explore:** [Electronic Literature Collection](https://collection.eliterature.org) | [Hyperrhiz](http://hyperrhiz.io/archive.html)

---

## Session 2 (Day 2): Tracery & Voyant

### Tracery — Generative Text Grammar
Tracery generates different text every time based on rules you define.

**Basic syntax:**
```json
{
  "origin": ["The #adj# #animal# #verb# through the #place#."],
  "adj": ["quick", "mysterious", "ancient", "glitching"],
  "animal": ["fox", "server", "archivist"],
  "verb": ["wandered", "compiled", "sang"],
  "place": ["library stacks", "terminal window", "void"]
}
```

Try it at: [tracery.io](http://tracery.io)

**In-class activity:** Write a Tracery grammar that generates a short poem or character description.

### Voyant Tools — Computational Text Analysis
1. Go to [voyant-tools.org](https://voyant-tools.org)
2. Paste in any text (a novel, song lyrics, your own writing)
3. Screenshot one surprising result

---

## Resources

- Twine: [twinery.org](https://twinery.org) | Docs: [twinery.org/cookbook](https://twinery.org/cookbook)
- Tracery: [tracery.io](http://tracery.io)
- Voyant Tools: [voyant-tools.org](https://voyant-tools.org)
- Electronic Literature Collection: [collection.eliterature.org](https://collection.eliterature.org)

## Project & Assignment

See [ASSIGNMENT.md](ASSIGNMENT.md) for full requirements.
