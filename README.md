# Clash of Critters — Card Tracker

A single-file, offline-friendly web tool for tracking your card collection in **Clash of Critters**. No install, no account, no server — just open the HTML file in any browser.

> ⚠️ **DESKTOP ONLY** — this tool is not optimised for mobile browsers. Use it on a desktop or laptop for the best experience.

🔗 **Repository:** https://github.com/Ajgonbas/coc_card_album_tracker

---

## How to use

1. Download `card-album-tracker.html` from this repository.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. That's it — everything runs locally in the page, nothing is sent anywhere.

### Pre-populated starting config

A `initial_config.json` file is included in the repository with set names, card rarities, and rewards already filled in. Download it and use **Import JSON** to load it — most of the album will be pre-populated. Cards with names shown as `?????` are ones that hadn't been identified yet.

If you know any missing card names or have golden card info, feel free to reach out (contact at the bottom).

---

## Features

### Card entry

The album is split into **15 pages of 9 cards each** (135 total), matching the in-game layout. For each card you can set:

- **Name** — optional, editable inline on the card tile.
- **Rarity** — click the stars (1★ to 5★). Click the same star again to clear.
- **Golden** — click the ✦ icon to mark a card as golden. Golden cards can only be traded during special events and appear in a separate tab on the export report.
- **Status** — click the button to toggle between:
  - `Missing` — default state. The card will appear in the **Need** section of the report. The copies counter is disabled.
  - `Have` — you own this card. The copies counter becomes active and starts at ×1.
- **Copies** — only available when status is `Have`. Reflects the in-game `×2`, `×3` display. One copy (×1) means no spare; two or more shows how many are tradeable (`copies − 1`).

### Page headers

Each page header shows:
- An editable **set name** (e.g. *Sparkrow Set*, *Cindermunk Set*).
- A **card counter** showing how many cards on that page you currently own.
- A **completion reward** — enter the amount and pick the reward type (Pinballs, Bento Boxes, Capsules, Wishboxes).

Click the header to collapse or expand a page.

### Export report

Click **Export report** in the top bar to open the report panel. It only shows sections that have data — empty sections are omitted. There are three tabs:

| Tab | Contents |
|---|---|
| **To trade** | Normal cards where you have ×2 or more, grouped by rarity. Shows how many copies are tradeable. |
| **Golden (event)** | Same as above but for golden-marked cards — only tradeable during special events. |
| **Need** | All cards currently set to `Missing`, grouped by rarity. |

Options at the bottom of the panel:
- **Hide card names** checkbox — strips names from the output, leaving only card numbers.
- **Copy to clipboard** — copies the report as plain text, ready to paste into Discord or anywhere else.
- **Save as file** — downloads the report as a `.txt` file.

### Saving and loading

- The tracker **auto-saves to browser localStorage** on every change — closing and reopening the tab restores your data automatically.
- **Save JSON** (top bar) downloads a portable `card-album.json` backup file.
- **Import JSON** loads a previously saved file and restores your full album state.
- **Clear all** wipes everything — both the in-page state and localStorage. A confirmation dialog appears before anything is deleted. Save a JSON backup first if you need to keep your data.

---

## File structure

The entire tool is a single self-contained HTML file with no external dependencies and no build step. Everything — markup, styles, and logic — lives in `card-album-tracker.html`.

---

## Credits

Built by **Kusanagi**.  
Discord: `kusanagi2k`

[Clash of Critters Wiki](https://clashofcritters.wiki.gg/)


Issues, suggestions, or trade requests? Find me on Discord.
