# 🚀 Vercel Deployment Guide

## Deploy to Vercel (10 minutes)

Your AI Test Strategy Generator is ready to deploy!

### Option 1: Quick Deploy via Vercel Dashboard (Recommended)

1. **Go to Vercel:** https://vercel.com/dashboard
2. **New Project → Import Git Repository**
3. **Select:** Prasannachamp/AI-Tester-3X
4. **Project Name:** `prasanna-s-projects10`
5. **Framework Preset:** HTML
6. **Environment Variables:** (leave blank for now)
7. **Deploy → Done!** ✅

**Your app will be live at:** `https://prasanna-s-projects10.vercel.app`

---

### Option 2: Deploy via Vercel CLI

```bash
# 1. Install Vercel CLI (if not already installed)
npm install -g vercel

# 2. Navigate to project
cd "C:\Users\prasa\.vscode-shared\sharedStorage\AITesterBlueprint3x.worktrees\copilot-worktree-2026-06-10T12-01-14"

# 3. Link to Vercel project
vercel link --yes --project prasanna-s-projects10

# 4. Deploy
vercel deploy --prod
```

---

### Option 3: Automatic Deploy (GitHub Connected)

1. Push to GitHub (already done ✅)
2. Go to https://vercel.com/new
3. Import from GitHub → Prasannachamp/AI-Tester-3X
4. Set Project Name: `prasanna-s-projects10`
5. Vercel auto-deploys on every push!

---

## After Deployment

✅ Your app will be at: **https://prasanna-s-projects10.vercel.app**

### Test It:
- Open the URL in browser
- Enter JIRA credentials
- Generate a test strategy
- Export as JSON

### Share:
- Copy the Vercel URL
- Share with team
- No installation needed for others!

---

## Files Deployed

- ✅ `index.html` — Main app (27 KB)
- ✅ `vercel.json` — Configuration
- ✅ All documentation files
- ✅ Framework references (B.L.A.S.T., RICE-POT)

---

## Troubleshooting

**"Deployment Failed"**
- Check `vercel.json` is valid JSON
- Ensure `index.html` exists in root

**"Blank Page"**
- Clear browser cache (Ctrl+Shift+Delete)
- Hard refresh (Ctrl+F5)

**"JIRA/Groq API errors"**
- Normal! These are runtime errors
- Enter valid credentials in the app

---

## Environment Variables (Optional)

For production, you can pre-configure credentials in Vercel:

1. Go to Project → Settings → Environment Variables
2. Add:
   - `JIRA_BASE_URL` = Your JIRA URL
   - `JIRA_EMAIL` = Your email
   - `GROQ_API_KEY` = Your Groq key

Then the app will auto-populate these fields.

---

## Monitoring

Monitor your deployment:
- **Vercel Dashboard:** https://vercel.com/dashboard/projects
- **Analytics:** Track page views, performance
- **Logs:** See real-time API calls

---

**Ready?** Deploy now and share your AI Test Strategy Generator with the world! 🌍
