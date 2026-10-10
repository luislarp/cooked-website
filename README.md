# COOKED ($COOKED) website

A fast, simple website. No frameworks, no dependencies. Everything lives in **`index.html`**.
The mascot is drawn inside the page, so there are no image files to lose.

## What is in this folder

| File | What it is |
|------|------------|
| `index.html` | The whole website |
| `package.json` | Tells Vercel how to build (`npm run build`) |
| `vercel.json` | Vercel settings (publishes the `dist` folder) |
| `scripts/build.js` | Copies the site into `dist` |
| `scripts/serve.js` | Optional local preview |
| `.gitignore` | Keeps junk and secrets out of GitHub |

## Deploy with GitHub + Vercel (no coding needed)

### Step 1 — Put the files on GitHub
1. Create a free account at https://github.com and log in.
2. Click **+** (top right) → **New repository**. Name it `cooked-website`, choose **Public** or **Private**, click **Create repository**.
3. On the new page click **uploading an existing file**.
4. Unzip `cooked-website.zip`. Open the `cooked-site` folder and drag **everything inside it** (`index.html`, `package.json`, `vercel.json`, `.gitignore`, `README.md` and the `scripts` folder) into the GitHub page.
   - `index.html` must be at the top level of the repository, not inside another folder.
   - If your file explorer hides `.gitignore`, that is fine — the site works without it.
5. Click **Commit changes**.

### Step 2 — Publish with Vercel
1. Go to https://vercel.com and choose **Sign Up → Continue with GitHub**.
2. Click **Add New… → Project**, find `cooked-website`, click **Import**.
3. Leave every setting as it is (Vercel reads `vercel.json`). Click **Deploy**.
4. After about a minute you get a live link like `cooked-website.vercel.app`.

### Optional — your own domain
In Vercel: **Project → Settings → Domains** and follow the steps.

## Launch day: enabling the contract address and buy buttons
1. On GitHub open `index.html` and click the pencil icon (**Edit**).
2. Press Ctrl+F (Cmd+F on Mac) and search for `const CONFIG`.
3. Change these lines:
   - `launched: true`
   - `contract: 'THE_REAL_CONTRACT_ADDRESS'`
   - `chain: 'Solana'` (only if the contract confirms it)
   - `tokenUrl: 'https://pump.fun/...'` (the official coin link)
4. Click **Commit changes**. Vercel republishes automatically within a minute.

The buy buttons stay hidden until `launched` is `true` **and** `tokenUrl` is a valid `https://` link.
If the launch date or time changes, also update `launchDate` and the text "October 15th" in the launch section.

## Run it on your computer (optional)
Needs Node.js 18 or newer.
```
npm run build
npm start
```
Then open http://localhost:3000.

## Notes
- No API keys, passwords or secrets are used. Never put any into this project.
- Fonts load from Google Fonts. If they are blocked, the site falls back to system fonts.
- This is a meme-coin community project. Crypto is risky and the site makes no promises of returns.
