# Trading widgets — GitHub Pages setup

Four standalone HTML files. No build step, no dependencies, no network calls.
Hosting them at a public URL lets Notion render them live and always expanded,
instead of as a file card you have to click open.

## Files

| File | Where it goes in Notion |
|---|---|
| `session-clocks.html` | top of the Trading Journal page |
| `risk-management.html` | Before you trade |
| `position-size.html` | Before you trade |
| `equity-curve.html` | Review |

## Setup, about ten minutes, once

1. Create a free account at github.com if you don't have one.
2. Click **New repository**. Name it `trading-widgets`. Set it to **Public**
   (GitHub Pages needs Public on the free plan). Do not add a README —
   this file already is one.
3. On the empty repo screen click **uploading an existing file**.
   Drag in all four `.html` files and this `README.md`. Click **Commit changes**.
4. Go to **Settings → Pages** in that repo.
   Under *Build and deployment → Source* choose **Deploy from a branch**.
   Branch: `main`, folder: `/ (root)`. Click **Save**.
5. Wait one to two minutes. The page will show your address:
   `https://YOURNAME.github.io/trading-widgets/`
6. Check each widget loads:
   - `https://YOURNAME.github.io/trading-widgets/session-clocks.html`
   - `https://YOURNAME.github.io/trading-widgets/risk-management.html`
   - `https://YOURNAME.github.io/trading-widgets/position-size.html`
   - `https://YOURNAME.github.io/trading-widgets/equity-curve.html`

## Putting them into Notion

On the Trading Journal page, type `/embed`, press Enter, paste one of the URLs
above, and click **Embed link**. Drag the bottom edge to set the height.
Suggested heights: clocks about 200px, risk about 900px, position size about
700px, equity curve about 900px.

Then delete the old file-attachment embeds so nothing is duplicated.

## Changing anything later

Edit the file in GitHub (open it, click the pencil, commit). The change is live
in about a minute — Notion picks it up on refresh, no re-embedding needed.

## What these widgets do not do

They cannot read your Notion databases. They run in a sandboxed frame with no
access to the Notion API, and putting an API token inside a public file would
expose it to anyone. Every number is typed or pasted in by hand. That is a
limitation of the approach, not a bug.

## Verify before trading real size

`position-size.html` ships with pip values that are correct for USD-quoted
pairs and approximate for JPY, CHF and CAD pairs, gold, silver and indices.
Confirm the real value for each instrument in your own platform before you
size a live position.
