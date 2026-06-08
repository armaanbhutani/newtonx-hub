# Hub Research Copilot — Vercel Deploy

## Deploy in 5 minutes

### 1. Push to GitHub
Create a new GitHub repo (can be private) and push this folder:
```
git init
git add .
git commit -m "Hub Research Copilot"
git remote add origin https://github.com/YOUR_USERNAME/newtonx-hub.git
git push -u origin main
```

### 2. Deploy to Vercel
1. Go to https://vercel.com and sign in (free account)
2. Click **Add New → Project**
3. Import your GitHub repo
4. Click **Deploy** — no build settings needed

### 3. Add your API key
1. In Vercel dashboard → your project → **Settings → Environment Variables**
2. Add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: your Anthropic API key (from https://console.anthropic.com)
   - Environment: Production, Preview, Development (check all three)
3. Click **Save**
4. Go to **Deployments** → click the three dots on latest → **Redeploy**

Your live URL will be `https://newtonx-hub-XXXX.vercel.app`

---

## Project structure
```
newtonx-hub/
├── api/
│   └── claude.js        # Serverless proxy — keeps API key server-side
├── public/
│   └── index.html       # Full prototype
├── vercel.json          # Routing config
└── README.md
```

## How it works
- The browser calls `/api/claude` (your Vercel function)
- The function adds your API key and forwards to Anthropic
- The API key never appears in the browser or source code
- Safe to share the link publicly
