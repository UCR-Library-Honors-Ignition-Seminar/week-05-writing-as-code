# Step-by-Step: Writing a Tracery Grammar

**Time needed:** 30–45 minutes | **No downloads required**

---

## What is Tracery?

Tracery is a tool for writing **generative text** — text that a system produces by following rules you define. Every time it runs, it picks randomly from your word lists and combines them according to your grammar.

You write the rules. The system writes the text. Every output is different.

It was created by Kate Compton and used to power thousands of Twitter bots, generative poetry systems, and game dialogue engines.

---

## Step 1: Open the Editor

Go to [tracery.io/editor](http://tracery.io/editor/) — no account needed.

You will see a text editor on the left and a generated output on the right. The editor starts with a sample grammar. Click **"Generate"** a few times to see how it produces different outputs from the same rules.

---

## Step 2: Understand the Structure

A Tracery grammar is a JSON object — a set of named lists:

```json
{
  "origin": ["The #adj# #noun# #verb# in the #place#."],
  "adj":    ["quiet", "fractured", "luminous"],
  "noun":   ["archive", "signal", "corridor"],
  "verb":   ["drifts", "echoes", "waits"],
  "place":  ["reading room", "terminal", "distance"]
}
```

**How it works:**
- `"origin"` is always the starting point — Tracery runs this first
- `#symbol#` means "pick a random item from the list named `symbol`"
- Tracery replaces every `#symbol#` with a random choice from that list

So `"The #adj# #noun# #verb# in the #place#."` might produce:

> *The fractured corridor echoes in the reading room.*

or

> *The luminous signal drifts in the distance.*

Every time you click Generate, you get a new combination.

---

## Step 3: Write Your Own Grammar

Clear the editor and start fresh. Pick a concept — a character, a place, an event, a feeling — and build rules around it.

**Example: A character generator**
```json
{
  "origin":      ["#name# is a #adj# #role# who #habit#."],
  "name":        ["Mira", "Theo", "Sable", "Oren"],
  "adj":         ["cautious", "restless", "methodical", "impulsive"],
  "role":        ["archivist", "navigator", "signal operator", "translator"],
  "habit":       ["never finishes sentences", "collects small stones", "speaks only in questions", "draws maps of places that do not exist"]
}
```

**Example: A place generator**
```json
{
  "origin":      ["You enter a #size# room. The walls are #material#. It smells like #smell#. In the corner: #detail#."],
  "size":        ["narrow", "vast", "perfectly square", "circular"],
  "material":    ["bare concrete", "old wood", "glass", "something soft"],
  "smell":       ["cedar", "machine oil", "rain", "nothing at all"],
  "detail":      ["a chair with one leg missing", "a pile of identical envelopes", "a mirror facing the wall", "a plant that should be dead"]
}
```

---

## Step 4: Nest Symbols Inside Symbols

You can use a `#symbol#` inside another symbol's list. This creates more complex, layered outputs.

```json
{
  "origin":   ["#scene#"],
  "scene":    ["#character# #action# near the #landmark#."],
  "character":["the #adj# #noun#"],
  "adj":      ["silver", "unnamed", "slow"],
  "noun":     ["figure", "machine", "voice"],
  "action":   ["waits", "flickers", "reads aloud"],
  "landmark": ["#landmark_adj# #landmark_noun#"],
  "landmark_adj": ["collapsed", "half-built", "forgotten"],
  "landmark_noun":["tower", "station", "archive"]
}
```

---

## Step 5: Generate and Screenshot

1. Click **"Generate"** at least 10 times
2. Screenshot outputs that surprise you, feel wrong, or feel unexpectedly right
3. Those moments of surprise are your data — use them in your reflection

---

## Step 6: Save Your Grammar

Tracery does not auto-save. When you are happy with your grammar:

1. Select all the text in the editor (Ctrl+A / Cmd+A)
2. Copy it
3. Open a new file in a text editor (or directly on GitHub) and paste it
4. Save as `grammar.json`
5. Upload to your GitHub Classroom repo

---

## Common Errors

| Problem | Cause | Fix |
|---------|-------|-----|
| Nothing generates | Syntax error in JSON | Check for missing commas, unclosed `"` or `[` |
| `#symbol#` appears literally | Symbol name is misspelled | Make sure the name in `#name#` exactly matches a key in your JSON |
| Output is too repetitive | Lists are too short | Add more items to each list — aim for 5–8 per symbol |
| Output is nonsensical | Grammar structure too loose | Read outputs aloud — if nothing makes sense, tighten your sentence structure in `"origin"` |

---

## Going Further

- Add **multiple origin options** — put more than one sentence in your `"origin"` list and Tracery will pick between different sentence structures
- Try **recursive symbols** — a symbol that references itself can create endlessly varied output (but be careful: deep recursion can crash the generator)
- Kate Compton's original [Tracery tutorial](http://www.crystalcodepalace.com/traceryTut.html) covers advanced features like push/pop (saving a variable mid-generation) and modifiers (capitalizing words automatically)
