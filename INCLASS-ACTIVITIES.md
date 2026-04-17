# In-Class Activities: Writing as Code

---

## Session 1 Activities — Twine

### Part 1: Play and Observe (~15 min)

Play **one** of the following before opening Twine:

- [9:05](https://adamcadre.ac/if/905.html) by Adam Cadre — takes about 3 minutes; notice how your assumptions about what is happening shift as you read
- [Shade](https://www.eblong.com/zarf/zweb/shade/) by Andrew Plotkin — a surreal piece about a room that changes as you explore it

As you play, notice:
- What choices does the author give you? What choices are hidden or unavailable?
- When does the text feel like a story and when does it feel like a system?
- Is there a moment where you realize the author anticipated exactly what you would try?

**Discuss as a class:**
- In a linear story, the author controls what happens. In interactive fiction, the player makes choices — but the author still wrote all the options. Who is really in control?
- Did the piece you played feel like it changed based on your choices, or did it feel inevitable?
- What would be lost if this were a regular short story?

---

### Part 2: Build a Small Branching Story (~25 min)

Open [Twine](https://twinery.org) — click "Use in your Browser," then "New" to start a story.

**Before you touch the tool:** sketch on paper first. Draw two or three boxes connected by arrows — one starting situation, two different paths, two different places to end up. The story can be simple, strange, or abstract. It does not need to be a traditional narrative.

Some starting points if you are stuck:
- A room with two doors — what is behind each one?
- A conversation where the tone changes depending on what you say first
- A journey where the destination is the same no matter which path you take — but the experience of arriving is different

**Minimum to aim for:**
- [ ] 3 passages connected with `[[links]]`
- [ ] At least 2 decision points where the reader makes a choice
- [ ] 2 different endings

See [INSTRUCTIONS-TWINE.md](INSTRUCTIONS-TWINE.md) for syntax help. If you get stuck on the tool, focus on writing the text first — you can always connect the passages once the words exist.

---

### Part 3: Discussion (~10 min)

If you would like to share your story with the class, you are welcome to — just open it and let someone else click through it.

Whether or not you share, discuss as a class:

- What was the hardest writing decision you made — not technical, but narrative? What did you choose to give the reader, and what did you withhold?
- Did writing in branches change the way you thought about the story? Did it make you think differently about cause and effect, or about what a "choice" actually means?
- Twine forces you to commit: every path has to go somewhere. Did that constraint change what you wrote?

---

## Session 2 Activities — Tracery

### Part 1: Read a Generative Text (~10 min)

Open [Taroko Gorge Remixes](https://collection.eliterature.org/3/collection-taroko.html) and read one version for two minutes. Then click refresh several times.

In your notes, write down:
- One line that surprised you
- One line that felt flat or random
- What stays the same across outputs? What varies?

**Discuss as a class:**
- Is there a voice in this text — a style, a point of view — or does it feel like noise?
- A human author wrote the rules that produced these lines. Is that person still the author of the output? Are you, as the reader, part of the authorship?
- What would you have to change in the rules to make the output feel completely different?

---

### Part 2: Write a Small Grammar (~25 min)

Open the [grammar.html template](INSTRUCTIONS-TRACERY.md) from the Tracery instructions and build a grammar that generates one type of sentence — a character description, a place, a small event — whatever interests you.

**Start as small as possible:**
- One `"origin"` sentence with 2–3 `#symbols#`
- 3–4 words in each symbol list
- Run it 10 times before adding anything

Once the basic sentence works, try one of these:
- Add a second symbol that references another symbol: `"#adj# #noun#"` inside a list
- Write two different `"origin"` templates and put both in the list — now the sentence structure itself varies
- Make the words in one list come from a specific place: all from one book, one era, one mood

See [INSTRUCTIONS-TRACERY.md](INSTRUCTIONS-TRACERY.md) for the full template and setup steps.

---

### Part 3: Discussion (~15 min)

If you would like to show an output from your grammar, share a screenshot or read a line aloud — whatever feels comfortable.

Discuss as a class:

- Did your grammar ever produce something that surprised you — something you did not intend but that felt right?
- What does that surprise tell you about authorship? Can a system have a sensibility, or does it only reflect the choices you made when writing the rules?
- Tracery grammars are deterministic — every output follows rules you wrote. ELIZA worked the same way. Yet people felt that ELIZA understood them. Why do we read intention and meaning into rule-based outputs?
- Where do you think the line is between a tool that generates text and a tool that writes?
