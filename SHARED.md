# Leonidas Hub — shared content contract (app ↔ website)

**Rule:** Share *data and brand*, not React Native UI. Website adapts layout for desktop; copy and feeds stay identical.

## Sources of truth

| What | Where | Used by |
|------|--------|---------|
| Brand colors / type / radii | `brand/tokens.json` (+ generated `tokens.css`) | Website now; Expo theme should import/sync the same JSON |
| Marketing copy / feature blurbs | `brand/tokens.json` → `copy` + `features` | Landing + (later) store text |
| News feed | `https://strxightflushapps.github.io/news/news.json` (repo `StrxightFlushApps/news`) | App + Website |
| Privacy (app / stores) | `https://strxightflushapps.github.io/privacy/` | App + Play + App Store until post-review cutover |
| Privacy (website) | `/privacy.html` on leonidashub.io | Website only (mirror) |
| Map data | `map.gtadb.org` | App (web map optional later) |
| Wiki / Community / Lex | App bundle / Replit for now | Not on website until extracted to JSON |

## How to ship a new idea

1. If it’s **content** (news, feature text, colors, links): change the shared source above → both surfaces update (news/site immediately; app on next fetch or next build for bundled tokens).
2. If it’s **interaction** (map pulse, Lex chat, offline wiki): build in the app first; only port to the website if a browser UX is worth it, reading the same JSON when possible.
3. After every privacy-relevant app change: update **both** privacy mirrors (GitHub Pages + `privacy.html`).

## Out of scope for v1 website

- Full wiki browser
- Interactive Leonida map
- Lex chat
- Community posts
- Account / ads (later)
