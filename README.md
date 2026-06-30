# 🏆 Wednesday Wins — Team Recognition Site

A simple website that shows shoutouts from our Wednesday team meetings. Each month gets its own page, and the whole thing lives on GitHub Pages, so it updates automatically whenever someone pushes a change from VS Code.

---

## 📁 How the files are organized

- One HTML file per month: `march.html`, `april.html`, `may.html`, and so on.
- Each file is fully self contained. All the styling and code needed for that month lives inside that one file, so you don't need to touch anything else to update a month.
- **The one exception is `index.html`.** This file is always the current month.

So right now, `index.html` and `june.html` are basically the same content, because June is the current month.

**When July starts:**
1. `index.html` gets renamed to `june.html`, so June becomes a proper archive page.
2. A brand new `index.html` gets created for July.
3. The navigation bar gets updated across **every** existing file to add a July button.

That's why the site always shows the latest month by default on the homepage, while older months stay browsable.

> ⚠️ Step 3 matters: if you skip updating the nav bar on the old files, people browsing an old month won't be able to jump to the new one.

---

## 🧩 What's on each page

Every monthly page follows the same structure, just with different content:

| Section | What it is |
|---|---|
| **Header** | Month name + quick links to jump to each week |
| **Stats bar** | 3 numbers: weeks covered, unique people recognised, ACE winner count |
| **Week sections** | One per week, alternating background colours, holding the shoutout cards |
| **Charts** | 3 charts at the bottom: top mentions, themes, shoutouts per week |

### Card types you'll see inside a week

- **Individual card** — standard shoutout for one person
- **Team card** — wide card, full row, celebrates the whole team instead of one person
- **ACE card** — dark, larger special card for the monthly ACE award winner. **Always placed in week one**, even if the actual announcement happened later in the month — that's just the convention
- **Farewell card** — used occasionally, for when someone is leaving the team

### About the charts

The 3 charts (Chart.js) at the bottom are **not automatic**. The numbers are typed in manually near the bottom of the file. So:

1. Add a new card
2. Update the numbers in the chart section too, or the charts won't match what's written above them

---

## ✏️ How to add a new shoutout

1. Open the month's HTML file and find the week section you want to add to.
2. Copy an existing card block — the chunk starting at `<div class="card">` and ending at the matching closing tag.
3. Paste it where you want the new card.
4. Change the name, role description, and write-up text.
5. Reuse one of the existing colours (e.g. `var(--teal)`) for the card accent — they're already defined at the top of the file, no need to invent new ones.

**Writing style for the card text:**
- Write a short overview of what happened, don't copy the meeting transcript word for word.
- Only use quotation marks for an actual quote someone said out loud, not for general descriptions.

---

## ⚠️ A few things worth knowing

- **Roberto Denaro** and **Roberto Carbonell** are two different people on the team — double check which one a shoutout is actually about.
- **Don't delete anything** from a file unless it's been clearly agreed first. If something looks outdated or wrong, flag it instead of removing it.
- After pushing a change, the site can take a moment to update, and your browser might show an old cached version. A hard refresh fixes that:
  - Mac: `Cmd + Shift + R`

---

## 🛠️ Tools used

- **VS Code** — editing the files
- **GitHub / GitHub Pages** — storing and publishing the site
- **Chart.js** — powers the 3 charts at the bottom of each page (loaded via a link in the file, nothing to install)
