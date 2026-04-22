# Step-by-Step: Writing a Tracery Grammar

**Time needed:** 30–45 minutes | **No downloads required**

---

## What is Tracery?

Tracery is a tool for writing **generative text** — text that a system produces by following rules you define. Every time it runs, it picks randomly from your word lists and combines them according to your grammar.

You write the rules. The system writes the text. Every output is different.

It was created by Kate Compton and used to power thousands of Twitter bots (in the past), generative poetry systems, and game dialogue engines.

---

## Step 1: See a Grammar in Action

Before writing your own, explore what Tracery grammars look like when they run.

Go to the [Tracery editor](http://tracery.io/editor/) and click **"Reroll"** several times — each click generates new text from the same rules. Use the dropdown at the top left to try different preloaded grammars (landscape, nightvale, poem).

> **Note:** The editor is for visualization only — it doesn't accept typed input reliably (But you can replace the words in the existing lists). You will write your own grammar as an HTML file in the next steps.

---

## Step 2: Understand the Structure

A Tracery grammar is a set of named lists. Each list holds options the system can pick from. You reference a list by wrapping its name in `#` signs:

```
"origin": ["The #adj# #noun# #verb# in the #place#."]
```

When Tracery runs this, it replaces `#adj#`, `#noun#`, etc. with a random item from each matching list:

> *The fractured corridor echoes in the reading room.*  
> *The luminous signal drifts in the distance.*

Every run produces a different combination.

---

## Step 3: Create Your Grammar File

You will write your grammar as a small HTML file. This file runs in any browser — no installation needed.

**In your GitHub Classroom repo:**

1. Click **"Add file"** → **"Create new file"**
2. Name the file `grammar.html`
3. Paste the following template and edit the word lists:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Tracery Grammar</title>
  <script src="https://unpkg.com/tracery-grammar/tracery.js"></script>
  <style>
    body { font-family: Georgia, serif; max-width: 600px; margin: 60px auto; font-size: 1.2em; }
    button { font-size: 1em; padding: 8px 20px; margin-bottom: 20px; cursor: pointer; }
    #output { line-height: 1.8; color: #222; }
  </style>
</head>
<body>
  <button onclick="generate()">Generate</button>
  <div id="output"></div>

  <script>
    var rules = {
      "origin": ["The #adj# #noun# #verb# through the #place#."],
      "adj":    ["slow", "luminous", "broken", "recursive"],
      "noun":   ["archive", "signal", "voice", "corridor"],
      "verb":   ["drifts", "compiles", "surfaces", "echoes"],
      "place":  ["reading room", "terminal", "network", "silence"]
    };

    var grammar = tracery.createGrammar(rules);

    function generate() {
      document.getElementById("output").innerText = grammar.flatten("#origin#");
    }

    // generate one on load
    generate();
  </script>
</body>
</html>
```

4. Click **"Commit changes"**

---

## Step 4: Run Your Grammar

1. Click on `grammar.html` in your repo
2. Click the **download icon** (top right, next to the pencil) to save the file to your computer
3. Open the downloaded file in your browser — double-click it or drag it into a browser window

Click **Generate** repeatedly to see different outputs.

---

## Step 5: Write Your Own Grammar

Now replace the example word lists with your own content. Pick a concept — a character, a place, an event, a mood — and build rules around it.

**Example: A character generator**
```javascript
var rules = {
  "origin":   ["#name# is a #adj# #role# who #habit#."],
  "name":     ["Mira", "Theo", "Sable", "Oren"],
  "adj":      ["cautious", "restless", "methodical", "impulsive"],
  "role":     ["archivist", "navigator", "signal operator", "translator"],
  "habit":    ["never finishes sentences", "collects small stones", "speaks only in questions", "draws maps of places that do not exist"]
};
```

**Example: A place generator**
```javascript
var rules = {
  "origin":   ["You enter a #size# room. The walls are #material#. It smells like #smell#. In the corner: #detail#."],
  "size":     ["narrow", "vast", "perfectly square", "circular"],
  "material": ["bare concrete", "old wood", "glass", "something soft"],
  "smell":    ["cedar", "machine oil", "rain", "nothing at all"],
  "detail":   ["a chair with one leg missing", "a pile of identical envelopes", "a mirror facing the wall", "a plant that should be dead"]
};
```

---

## Step 6: Nest Symbols Inside Symbols

You can use a `#symbol#` inside another symbol's list to build more complex, layered outputs:

```javascript
var rules = {
  "origin":        ["#scene#"],
  "scene":         ["#character# #action# near the #landmark#."],
  "character":     ["the #adj# #noun#"],
  "adj":           ["silver", "unnamed", "slow"],
  "noun":          ["figure", "machine", "voice"],
  "action":        ["waits", "flickers", "reads aloud"],
  "landmark":      ["#landmark_adj# #landmark_noun#"],
  "landmark_adj":  ["collapsed", "half-built", "forgotten"],
  "landmark_noun": ["tower", "station", "archive"]
};
```

---

## Step 7: Generate Multiple Outputs at Once

To see 5 outputs every time you click Generate, replace the `generate()` function with:

```javascript
function generate() {
  var results = [];
  for (var i = 0; i < 5; i++) {
    results.push(grammar.flatten("#origin#"));
  }
  document.getElementById("output").innerHTML = results.join("<br><br>");
}
```

Screenshot outputs that surprise you, feel wrong, or feel unexpectedly right — those are the moments worth writing about in your reflection.

---

## Common Errors

| Problem | Cause | Fix |
|---------|-------|-----|
| Page is blank, button does nothing | JavaScript error — likely a missing comma or quote | Check every list ends with `]` and every line inside the list ends with `,` except the last one |
| `#symbol#` appears literally in output | Symbol name is misspelled | Check that the name inside `#...#` exactly matches a key in your `rules` object |
| Output is too repetitive | Lists are too short | Add more items to each list — aim for 5–8 options per symbol |
| Output feels random/nonsensical | Grammar structure too loose | Tighten your `"origin"` sentence — the more specific the structure, the more readable the output |

---

## Going Further

- **Multiple origin options** — add more than one sentence to the `"origin"` list; Tracery will pick between different sentence structures entirely
- **Modifiers** — Tracery has built-in text modifiers: `#noun.capitalize#` capitalizes the word, `#noun.s#` pluralizes it, `#noun.a#` adds "a" or "an" automatically
- **Preview what's next** — in Week 6 you will use this same grammar inside a p5.js sketch, where the generated text can appear as animated visuals on a canvas; everything you build this week carries forward
- [Kate Compton's Tracery tutorial](https://tracery.io/archival/crystalcodepalace/tracerytut.html) covers advanced features including push/pop (reusing a value across a single generation for consistency)
