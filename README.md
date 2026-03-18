# Mute Manager 🌥️

**A Bluesky tool to see everyone you've muted — convert them to blocks, or clear them all.**

Made by Durandal

an [ICZE4R](https://bsky.app/profile/iczer.one) joint • [→ Open the tool](https://icze4r.github.io/mute-manager/ambivalence.html)

---

## What it does

Bluesky's app doesn't give you a great view of your mute list, and offers no bulk actions. Mute Manager fixes that:

1. Logs in with your app password
2. Pulls your complete mute list directly from Bluesky's API
3. Cross-references your follows and existing blocks
4. Lets you filter, select, and either:
   - **Block selected accounts** — optionally unmuting them at the same time (since muting someone you've blocked is redundant)
   - **Unmute All** — clear your entire mute list in one shot, no blocks created

Everything runs **entirely in your browser**. No server, no data collection, no tracking. No ClearSky required — mutes are fetched straight from Bluesky's own API.

---

## How to use it

### Online (recommended)

Just open the tool: **[https://icze4r.github.io/mute-manager/](https://icze4r.github.io/mute-manager/)**

### Local

Download `index.html` and open it in any browser. Unlike the BlockBack tool, this one has no CORS issues — everything goes directly to Bluesky's API.

---

## Setup

**Step 1 — Get an App Password**

Go to [bsky.app/settings/app-passwords](https://bsky.app/settings/app-passwords) and create one. Use this instead of your main password. You can revoke it any time from the same page.

**Step 2 — Enter your handle and app password**

The tool authenticates directly with Bluesky. Your credentials never leave your browser.

**Step 3 — Review your mutes**

The tool fetches your full mute list and shows each account with their handle, DID, and badges indicating if you also follow them or have already blocked them.

**Step 4 — Choose your action**

*To nuke your whole mute list:*
Hit **☁ Unmute All** at the top. Confirms first, then clears everyone one at a time with a small delay.

*To convert mutes to blocks:*
Use the filters to skip people you follow or already block. Select individual accounts or use the bulk selectors. Toggle **Also unmute when blocking** if you want them cleaned off the mute list at the same time. Hit **Block Selected**.

---

## Filters

| Toggle | What it does |
|---|---|
| Skip people I follow | Hides anyone you currently follow from selection |
| Skip already-blocked | Hides accounts you've already blocked |
| Also unmute when blocking | When blocking, also removes them from your mute list |

---

## Notes on rate limits

- The tool adds a 300ms delay between block operations and a 200ms delay between unmute operations.
- Bluesky enforces write rate limits. If you're processing a very large list, pace yourself — wait a few minutes between large batches if you hit errors mid-run.
- Unmute All runs slightly faster since unmuting is lighter than blocking.

---

## Privacy & security

- **Your credentials** go directly to `bsky.social` — nowhere else.
- **No third-party services** are used. Unlike the BlockBack tool, this one doesn't need ClearSky at all.
- **Nothing is stored** — no localStorage, no cookies, no external analytics.
- The entire tool is a single self-contained HTML file. You can read every line of it.

---

## Running on GitHub Pages

1. Fork or clone this repo
2. Rename `bluesky-unmute.html` to `index.html`
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch** → `main` → `/ (root)`
5. Save — live within about a minute at `https://yourusername.github.io/mute-manager/`

---

## Related

- **[Spite — Bluesky BlockBack Tool](https://github.com/icze4r/blockback)** — find accounts blocking you and block them back

---

## Credits

Built with the [Bluesky AT Protocol API](https://docs.bsky.app) — `getMutes`, `unmuteActor`, `getBlocks`, `createRecord`, `getFollows`.

---

## License

MIT — do whatever you want with it.
