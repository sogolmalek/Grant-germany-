# ⛨ Shield — Rug Score Everywhere

> Chrome extension that scores every Solana token for rug risk. Powered by RugCheck + Alchemy RPC + x402.

## Architecture

```
Chrome Extension ──→ Shield API ──→ RugCheck API (free)
    (user)              (you)    ──→ Alchemy RPC (Solana)
                         │
                    Payment verification
                    USDC → your wallet
```

## Deploy Backend (5 min)

### Option A: Render (free tier)
1. Push `backend/` to GitHub
2. Go to render.com → New Web Service → connect repo
3. Build: `npm install` / Start: `node server.js`
4. Done — you get a URL like `https://shield-api.onrender.com`

### Option B: Railway
1. `cd backend && railway deploy`

### Option C: Fly.io
1. `cd backend && fly launch`

## Update Extension
After deploying backend, update `SHIELD_API` in `extension/src/content.js`:
```js
const SHIELD_API = 'https://your-shield-api-url.onrender.com';
```

## Load Extension
1. Open `chrome://extensions`
2. Enable Developer Mode
3. Load Unpacked → select `extension/` folder

## Revenue
- $0.01 USDC per scan → goes to: A59AVvijPfVC62vxpWqHevgc5FEaQ6bEEmdvSdMYDebs
- Free tier: 10 scans/day for 3 days
- After: requires Phantom wallet + USDC payment

## License
MIT
