# Step-by-Step: Building a Twine Story

**Time needed:** 45–60 minutes for a basic story | **No downloads required**

---

## What is Twine?

Twine is a tool for writing interactive stories that branch — like a "Choose Your Own Adventure" book, but built in your browser and exportable as a webpage. Every time a reader makes a choice, they follow a different path through your text.

You write in **passages** (individual screens of text) connected by **links** (the choices you give the reader).

---

## Step 1: Open Twine

1. Go to [twinery.org](https://twinery.org)
2. Click **"Use it online"** — no account, no download needed
3. You will see the Twine story library (empty at first)

---

## Step 2: Create a New Story

1. Click **"+ New"** (top right)
2. Give your story a name — anything works
3. You will land in the **story map** — a canvas where you connect passages

---

## Step 3: Edit Your First Passage

1. Double-click the **"Untitled Passage"** box on the canvas
2. This is your **starting passage** — the first thing readers see
3. Give it a title (top field) and write your opening text

**Example:**
```
You wake up in a library. The shelves reach up into darkness.
There is a book open on the table in front of you.

[[Pick up the book]]
[[Walk toward the exit]]
```

The text in `[[double brackets]]` becomes a clickable link **and** automatically creates a new passage with that name.

---

## Step 4: Fill In Your Passages

1. Click **"<- Back"** to return to the story map
2. You will see new passage boxes appeared — one for each link you wrote
3. Double-click each one to add its text and more links

**Keep branching:**
```
You pick up the book. The pages are blank — but as you watch, words appear.

[[Read the words]]
[[Put the book down]]
[[Run]]
```

---

## Step 5: Create Endings

Passages with **no links** are endings. Write at least 2 different endings so readers feel their choices mattered.

```
You make it out. The library door closes behind you with a sound like a period at the end of a sentence.

[End]
```

*(You don't need to write `[End]` — a passage with no `[[links]]` is automatically an ending.)*

---

## Step 6: Play-Test Your Story

1. Click **"Play"** (top right of the story map)
2. A new tab opens with your story running
3. Click through all your paths — check that every link goes somewhere

---

## Step 7: Export as HTML

When you are ready to submit:

1. In the story map, click the **story name** at the bottom of the screen
2. Select **"Publish to File"**
3. A `.html` file downloads to your computer
4. Upload this file to your GitHub Classroom repo (drag and drop in the web interface)

> The exported `.html` file runs in any browser — your instructor can open it to experience your story.

---

## Useful Syntax Reference (Harlowe format — the default)

| Goal | Syntax | Example |
|------|--------|---------|
| Basic link | `[[Passage Name]]` | `[[Go upstairs]]` |
| Link with custom label | `[[label->Passage Name]]` | `[[Open it->Door Passage]]` |
| Set a variable | `(set: $varname to value)` | `(set: $hasKey to true)` |
| Conditional text | `(if: condition)[text]` | `(if: $hasKey)[The door unlocks.]` |
| Show variable value | `(print: $varname)` | `(print: $playerName)` |

Variables let you track what the reader has done — useful if you want a choice made early to affect something that happens later.

---

## Tips

- **Short passages work better than long ones.** Give readers a choice before they have to scroll.
- **Dead ends are fine** — not every path needs to be long. Some of the most effective interactive fiction has very short branches.
- **You can always go back.** Twine auto-saves in your browser. Your story is there when you return.
- **Stuck?** The [Twine Cookbook](https://twinery.org/cookbook/) has examples for almost every common pattern.
