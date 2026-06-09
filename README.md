# Clash of Critters — Card Tracker

A single-file, offline-friendly web tool for tracking your card collection in **Clash of Critters**. No install, no account, no server — just open the HTML file in any browser.

🔗 **Repository:** https://github.com/Ajgonbas/coc_card_album_tracker

---

## How to use

1. Download `card-album-tracker.html` from this repository.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. That's it — everything runs locally in the page.

### Starting configuration
I added a pre-population of the card album in the file `initial_config.json` just download it an import,
most set names, card stars, rewards, etc will be pre-populated. If you see card names as '?????' it's because I didn't have them yet.

Feel free to DM me names or gold cards I've missed, contact at the bottom

---

## Features

### Card entry
The album is split into **15 pages of 9 cards each** (135 total), matching the in-game layout. For each card you can set:

- **Name** — optional, editable inline on the card tile.
- **Rarity** — tap the stars (1★ to 5★). Tap the same star again to clear.
- **Golden** — tap the ✦ icon to mark a card as golden. Golden cards can only be traded during special events and appear in a separate tab on the report.
- **Status** — cycles through three states by clicking the status button:
  - `— unset` — not yet recorded.
  - `Have` — you own this card. The copies counter becomes active.
  - `Missing` — you don't have this card yet. It will appear in the **Need** section of the report.
- **Copies** — only available when status is `Have`. Matches the in-game `×2`, `×3` display. One copy means no spare; two or more shows how many are tradeable (`n−1`).

### Page headers
Each page header has:
- An editable **set name** (e.g. *Sparkrow Set*, *Cindermunk Set*).
- A **card counter** showing how many cards on that page you own.
- A **completion reward** — enter the amount and pick the reward type (Pinballs, Bento Boxes, Capsules, Wishboxes) so you know what you get for finishing the set.

Click the header to collapse or expand a page.

### Export report
Click **Export report** in the top bar to open the report panel, split into three tabs:

| Tab | Contents |
|---|---|
| **To trade** | Normal cards where you have `×2` or more, grouped by rarity. |
| **Golden (event)** | Same as above but for golden cards — only tradeable during events. |
| **Need** | Cards marked as `Missing`, grouped by rarity. |

Use **Copy as text** to paste the report anywhere (Discord, notes, etc.), or **Save JSON** to export a backup file.

### Saving and loading
- The tracker **auto-saves to browser localStorage** on every change — closing and reopening the tab restores your data.
- **Save JSON** downloads a portable `card-album.json` file you can back up or move between devices.
- **Import JSON** loads a previously saved file and merges it into the current state.
- **Clear all** wipes everything — both the in-page state and localStorage. A confirmation dialog appears before anything is deleted. Export a JSON first if you want a backup.

---

## File structure

The entire tool is a single self-contained HTML file with no external dependencies and no build step. Everything — markup, styles, and logic — lives in `card-album-tracker.html`.

---

## Credits

Built by **Kusanagi**.  
Discord: `kusanagi2k`

Issues, suggestions, or trade requests? Find me on Discord.
