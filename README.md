# Clash of Critters — Card Tracker

A web tool for tracking your card collection in **Clash of Critters**. No install, no account, no server — works in any modern browser on desktop or mobile.

🚀 **[➜ Open Card Tracker](https://ajgonbas.github.io/coc-card-trader/)**

🔗 **Repository:** https://github.com/Ajgonbas/coc-card-trader

---

## How to use

Visit the link above — no download needed. Everything runs locally in your browser; nothing is sent to any server.

If you prefer to run it offline, download `index.html` from this repository and open it directly in any browser.

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

On desktop, click the header to collapse or expand a page. On mobile, pages are navigated one at a time using the arrow buttons or by swiping left/right.

### Export report

Click **Export report** to open the report panel. It only shows sections that have data — empty sections are omitted. There are three tabs:

| Tab | Contents |
|---|---|
| **To trade** | Normal cards where you have ×2 or more, grouped by rarity. Shows how many copies are tradeable. |
| **Golden (event)** | Same as above but for golden-marked cards — only tradeable during special events. |
| **Need** | All cards currently set to `Missing`, grouped by rarity. |

Options at the bottom of the panel:
- **Hide card names** checkbox — strips names from the output, leaving only card numbers.
- **Copy to clipboard** — copies the report as plain text, ready to paste into Discord or anywhere else.
- **Save as file** — downloads the report as a `.txt` file.

### Compare trade

Click **Compare trade** to open the trade comparison tool. This lets you find possible card swaps with another player without sharing your full album data.

**How it works:**

1. Open the panel — your **share string** is automatically generated from your current album state. It's a short hex code encoding which cards you own, how many copies, their rarity, and whether they're golden.
2. Copy your share string and send it to the person you want to trade with (Discord, chat, etc.).
3. Ask them to do the same and send their string back to you.
4. Paste their string into the **"Paste their string"** field and click **Compare**.

**What it shows:**

By default the tool finds **reciprocal trades** — cards where you have a spare they need *and* they have a spare you need, matched at the **same rarity** (2★ for 2★, 3★ for 3★, etc.). Golden cards are matched separately and only pair with other golden cards.

```
★★★  You give: #42 Cindermunk  ⇄  You get: #17 Sparkrow
```

Tick **Show one-sided surpluses** to also see:
- Cards you have spare that they need, even without a matching return swap.
- Cards they have spare that you need, even without a matching return swap.

Cards already part of a reciprocal trade are excluded from the one-sided list so nothing appears twice.

> The share string is just a local snapshot — nothing is sent to any server.

### Saving and loading

- The tracker **auto-saves to browser localStorage** on every change — closing and reopening the tab restores your data automatically.
- **Save JSON** downloads a portable backup file you can move between devices.
- **Import JSON** loads a previously saved file and restores your full album state.
- **Clear all** wipes everything — both the in-page state and localStorage. A confirmation dialog appears before anything is deleted. Save a JSON backup first if needed.

---

## File structure

The entire tool is a single self-contained HTML file (`index.html`) with no external dependencies and no build step.

---

## Credits

Built by **Kusanagi**.  
Discord: `kusanagi2k`

Issues, suggestions, or trade requests? Find me on Discord.
