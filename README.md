# Link-Building QA Skill (`/lbqa`)

A Claude Code skill that helps a human **fact-check a finished link-building write-up (WU)** and its **infographic assets** against the **Production Card (PC)** — where the campaign's source data lives — and the client's **CM doc** (style guide).

The human does the actual cross-checking; the skill is a **lookup-and-comment tool**. It locates data in the PC, quotes it back verbatim, flags mismatches, and drafts paste-ready comments for the data journalist. It never states a PC value from memory and never guesses — that's the whole point, since it exists to catch AI mistakes, not add new ones.

This skill is **self-contained** — everything it needs is inside the `lbqa/` folder. There's nothing else to install and no internet connection required to run it.

> **Note:** this is a separate skill from `/writeup`. They used to live together, but they're now split so each can be shared on its own with the person who uses it.

**You'll need the Claude Code app to use it.** If you don't have Claude Code yet, install it first (search "Claude Code," see [claude.com/claude-code](https://claude.com/claude-code), or ask whoever set up your team's access).

---

## What's in this repo

```
link-building-lbqa-skill/
├── README.md              ← you are here
└── lbqa/                   ← THE SKILL (this is the folder you install)
    ├── SKILL.md
    └── reference/
        ├── comment-formats.md          ← paste-ready comment templates
        ├── 1-pc-qa-checklist.md        ← qualifier-to-number bands + math rules
        └── 5-fractl-style-and-voice.md ← Fractl AP-style, sourcing, voice
```

---

## Install it

You have two options. Either works.

### Option 1 — install so `/lbqa` is always available (recommended)

Put the inner **`lbqa`** folder into your Claude Code skills folder so the end result is `~/.claude/skills/lbqa/SKILL.md`.

**With git (easiest to update later):**
```bash
git clone https://github.com/lilyseitz-fractl/link-building-lbqa-skill.git
cp -R link-building-lbqa-skill/lbqa ~/.claude/skills/lbqa
```

**Or download without git:** on the [repo page](https://github.com/lilyseitz-fractl/link-building-lbqa-skill), click the green **Code** button → **Download ZIP**, unzip it, and copy the inner `lbqa` folder into `~/.claude/skills/`.

Then **restart Claude Code** and type `/lbqa` (or "QA this write-up against the PC") to run it.

**To update later:** `cd` into your clone, run `git pull`, then re-copy the `lbqa` folder into `~/.claude/skills/`.

### Option 2 — open this repo in Claude Code and run it from here

1. Clone or download the repo (see above).
2. In the Claude Code app, use **Open Folder** / **Open Project** and choose the `link-building-lbqa-skill` folder.
3. Type: **"Follow the steps in `lbqa/SKILL.md` to QA this write-up."**

---

## How to use it

**1. Get your three inputs ready — each saved as an HTML file.**
In Google Docs: **File → Download → Web Page (.html, zipped)**, then unzip. HTML matters because the comments and links embed in the file (the PC's comments often hold the real source data and instructions).

| Input | What it is |
|-------|-----------|
| **PC** | The Production Card — where the campaign's source data lives. |
| **WU** | The finished write-up you're checking. |
| **CM doc** | The client's style guide. |

For infographic checks, also have the **asset image files** on hand (the actual `.png`/`.jpg` files from the client asset folder, not just screenshots).

**2. Start the skill.** Type `/lbqa` and point it at your files. It runs an **opening pass automatically** and reports a short summary in three buckets:

- **CM-doc check** — heading case, banned words, required boilerplate, percentage formatting, meta length, alt text, etc.
- **WU vs PC (first pass)** — number mismatches, unsupported qualifiers, stats in the wrong section.
- **Spelling & grammar** — real mechanical errors only.

Ask for the full detail when you want it — each item comes with the exact text, the rule or PC value, and a paste-ready comment.

**3. Look up claims as you read (Step 2).** Hit a claim you can't find in the PC? Paste it and ask *"where is this in the PC?"* The skill searches the whole PC — tables, chart labels, alt text, key takeaways, methodology, embedded comments — and hands back the **verbatim string to Ctrl-F**, or tells you it's genuinely not there and drafts a comment for the DJ.

**4. QA the assets (Step 3).** Send the finished infographic files. The skill reads every element (titles, callouts, labels, source lines), checks each against the PC's data — **including the DJ's asset images embedded in the PC itself** — and against the CM doc, then hands back a list of comments to leave on each asset, labeled by its real filename.

Throughout, it quotes the real PC text so you can confirm every catch yourself — and it flags uncertainty instead of guessing.

---

## The one rule that matters most

The human cross-checks by hand *specifically because AI makes verification mistakes.* So the skill is built to:

1. **Never state a PC value from memory** — it re-reads and quotes verbatim, every time.
2. **Never guess** — ambiguous or multiple matches get shown to you to decide.
3. **Treat "not in the PC" as a real search result** — only after looking across the whole PC (including embedded asset images), and it tells you where it looked.

---

## Keeping it in sync with `/writeup`

`reference/1-pc-qa-checklist.md` (the qualifier bands and math rules) and `reference/5-fractl-style-and-voice.md` are **copies** of the same files in the `/writeup` skill. They're duplicated on purpose so this skill stands alone. If those rules ever change in `/writeup`, update the copies here too.
