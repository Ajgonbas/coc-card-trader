# Clash of Critters — Card Tracker

A web tool for tracking your card collection in **Clash of Critters**. No install, no account, no server — works in any modern browser on desktop or mobile.

🚀 **[➜ Open Card Tracker](https://ajgonbas.github.io/coc-card-trader/)**

🔗 **Repository:** https://github.com/Ajgonbas/coc-card-trader

---

## How to use

Visit the link above — no download needed. Everything runs locally in your browser; nothing is sent to any server.

If you prefer to run it offline, download `index.html` from this repository and open it directly in any browser.

### First visit

If you open the tracker with a completely empty album (no cards marked `Have` and no rarities set), a small prompt appears suggesting you load the initial configuration. You can dismiss it with **Not now** and configure everything manually, or click **Load initial config** to fetch the pre-filled defaults right away.

The same prompt also appears (with different wording) any time you toggle a card's status while it has no rarity set, since that card won't show up correctly in the trade report otherwise.

### Pre-populated starting config

A `initial_config.json` file is included in the repository with set names, card rarities, and rewards already filled in. Download it and use **Load Album** to load it — most of the album will be pre-populated. Cards with names shown as `?????` are ones that hadn't been identified yet.

If you know any missing card names or have golden card info, feel free to reach out (contact at the bottom).

---

## Features

### Card entry

The album is split into **15 pages of 9 cards each** (135 total), matching the in-game layout. For each card you can set:

- **Name** — optional, editable inline on the card tile.
- **Rarity** — click the stars (1★ to 5★). Click the same star again to clear. **A card needs a rarity assigned to be included in the trade report or compare tool** — cards with no stars are treated as not yet configured. If you toggle a card's status while it has no rarity set, a prompt appears suggesting you load the initial config to fill in the missing data.
- **Golden** — click the ✦ icon to mark a card as golden. Golden cards can only be traded during special events and appear in a separate section of the report when enabled.
- **Status** — click the button to toggle between:
  - `Missing` — default state. The card will appear in the **Need** section of the report. The copies counter is disabled.
  - `Have` — you own this card. The copies counter becomes active and starts at ×1.
- **Copies** — only available when status is `Have`. Reflects the in-game `×2`, `×3` display. One copy (×1) means no spare; two or more shows how many are tradeable (`copies − 1`).

### Page headers

Each page header shows:
- An editable **set name** (e.g. *Sparkrow Set*, *Cindermunk Set*).
- A **card counter** showing how many cards on that page you currently own.
- A **completion reward** — enter the amount and pick the reward type (Pinballs, Bento Boxes, Capsules, Wishboxes).

On desktop, click the header to collapse or expand a page. On mobile, pages are navigated one at a time using the arrow buttons or by swiping left/right.

### Make Card Trade

Click **Make Card Trade** to open the trade panel. It has two tabs: **Report** and **Compare Trade**.

#### Report tab

Generates a plain-text trade post you can paste straight into Discord:

```
** CoC Card Trade **

🔍 LF (Looking For):
★★★★: 63, 97, 122
★★★★★: 90, 108, 115, 116, 125, 126, 133, 134

📦 FT (For Trade):
★: 1, 3, 6, 7, 8, 10, 11, 14, 16, 19, 20, 21, 22, 23, 24
★★: 18, 25, 26, 34, 35, 42, 50, 52, 57, 58
★★★: 62, 69, 79, 87, 101, 103, 110, 118, 119
```

- **LF (Looking For)** lists every non-golden card currently set to `Missing`, grouped by rarity.
- **FT (For Trade)** lists every non-golden card where you have ×2 or more, grouped by rarity.
- **Golden FT** *(only shown when "Show Golden cards" is checked)* lists golden cards you have spares of — these can only be traded during special events.
- **Golden LF** *(only shown when "Show Golden cards" is checked)* lists golden cards you're missing — same event-only restriction applies.
- Sections with no data are omitted entirely, regardless of checkbox state.

Two checkboxes control the output:
- **Show card names** — off by default. When off, only card numbers are shown (e.g. `42`); when on, the name is appended (e.g. `42 Cindermunk`).
- **Show Golden cards** — off by default. When on, adds the two golden sections (FT and LF) below the regular ones. Golden cards never appear mixed into the regular LF/FT sections, since they follow different trading rules.

At the bottom: **Copy to clipboard** copies the report as plain text, **Save as file** downloads it as a `.txt`.

#### Compare Trade tab

Lets you find possible card swaps with another player without sharing your full album data.

**How it works:**

1. Switch to this tab — your **share string** is automatically generated from your current album state. It's a short hex code encoding which cards you own, whether you have a spare, their rarity, and whether they're golden.
2. Copy your share string and send it to the person you want to trade with (Discord, chat, etc.).
3. Ask them to do the same and send their string back to you.
4. Paste their string into the **"Paste their string"** field and click **Compare**.

By default the tool finds **reciprocal trades** — cards where you have a spare they need *and* they have a spare you need, matched at the **same rarity** (2★ for 2★, 3★ for 3★, etc.). Golden cards are matched separately and only pair with other golden cards.

Tick **Show one-sided surpluses** to also see cards you have spare that they need (or vice versa) even without a matching return swap. Cards already part of a reciprocal trade aren't repeated in the one-sided list.

> The share string is just a local snapshot — nothing is sent to any server.

### Saving and loading

- The tracker **auto-saves to browser localStorage** on every change — closing and reopening the tab restores your data automatically.
- **Save Album** downloads a portable backup file you can move between devices.
- **Load Album** loads a previously saved file and restores your full album state.
- **Load initial config** refreshes set names, card rarities, and reward info from the hosted default configuration. **Your card status (Have/Missing) and copy counts are never touched** — this only fills in or updates the metadata fields, so it's safe to run any time, e.g. after the maintainer adds newly-identified card names. A confirmation dialog explains this before proceeding. ⚠️ This only works at [ajgonbas.github.io/coc-card-trader](https://ajgonbas.github.io/coc-card-trader) — if you're running the file locally, use **Load Album** and load `initial_config.json` manually instead.
- **Clear all** wipes everything — both the in-page state and localStorage. A confirmation dialog appears before anything is deleted. Save an Album backup first if needed.

---

## File structure

The entire tool is a single self-contained HTML file (`index.html`) with no external dependencies and no build step.

---

## Credits

Built by **Kusanagi**.  
Discord: `kusanagi2k`

Issues, suggestions, or trade requests? Find me on Discord.
