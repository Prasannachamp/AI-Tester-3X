# 🚀 AI Test Strategy Generator (Lightweight React)

**A lightweight, browser-based React application for generating AI-powered test strategies from JIRA issues.**

**No backend required • No npm build process • Works instantly**

---

## ✨ Key Features

✅ **One HTML File** — Download and open, no installation  
✅ **Browser-Based** — Runs entirely in your browser  
✅ **JIRA Integration** — Fetch issues from JIRA Cloud  
✅ **AI-Powered** — Generate strategies with Groq LLM  
✅ **JSON Export** — Save strategies as JSON files  
✅ **Responsive** — Works on desktop, tablet, mobile  
✅ **Secure** — Credentials stored in browser memory only  
✅ **B.L.A.S.T. Compliant** — Follows deterministic automation framework  

---

## 🚀 Quick Start (30 seconds)

### 1. Download
```
test-strategy-generator.html
```

### 2. Open
Double-click the file or right-click → Open with → Browser

### 3. Configure
- Enter JIRA Base URL, Email, API Token
- Enter Groq API Key
- Click "Fetch Issues" or type an issue key

### 4. Generate
- Click "🤖 Generate Strategy"
- Wait 10-30 seconds
- Export as JSON

**Done!** ✅

---

## 🔧 Getting Credentials

### JIRA API Token
1. Go to https://id.atlassian.com/manage-profile/security/api-tokens
2. Click **Create API Token**
3. Copy the token (use as password, NOT your actual password)

### JIRA Base URL
- Find at: https://{your-workspace}.atlassian.net
- Example: `https://my-company.atlassian.net`

### Groq API Key
1. Go to https://console.groq.com/keys (free)
2. Click **Create API Key**
3. Copy the key

---

## 📖 How to Use

### Step 1: Configuration
```
Enter your JIRA details:
- Base URL: https://my-company.atlassian.net
- Email: john@example.com
- API Token: (from JIRA settings)

Enter Groq API Key:
- API Key: gsk_... (from console.groq.com)
```

### Step 2: Fetch Issues (Optional)
```
Click "🔍 Fetch Issues" to load your JIRA issues
(Or manually type an issue key like KAN-1)
```

### Step 3: Select Issue
```
Choose from dropdown or type issue key
Example: KAN-1, PROJ-123, etc.
```

### Step 4: Generate Strategy
```
Click "🤖 Generate Strategy"
Wait for AI to process (10-30 seconds)
```

### Step 5: Export
```
Click "📥 Export as JSON" to download
Click "📋 Copy to Clipboard" to copy text
```

---

## 📊 Output Example

```json
{
  "issueKey": "KAN-1",
  "issueTitle": "User Login Feature",
  "generatedAt": "2026-06-10T17:52:00Z",
  "testStrategy": {
    "objective": "Ensure login is secure and user-friendly",
    "scope": "Authentication, form validation, error handling",
    "outOfScope": "Third-party OAuth providers",
    "testApproach": "Manual + automation, security testing",
    "riskAssessment": "SQL injection, brute force, session hijacking",
    "testTypes": ["functional", "security", "performance"],
    "timeline": "2 weeks",
    "resources": "2 QA engineers, test environment",
    "deliverables": ["Test plan", "Test cases", "Bug reports"]
  }
}
```

---

## 🏗️ Architecture (B.L.A.S.T.)

### Phase 1: Blueprint ✅
- **Discovery:** 5 questions answered
- **Schema:** Data contracts defined
- **Outcome:** Test strategies saved to JSON

### Phase 2: Link ✅
- **JIRA API:** Verified & tested
- **Groq API:** Verified & tested
- **Connectivity:** Confirmed working

### Phase 3: Architect ✅
- **Layer 1 (SOPs):** JIRA_API_SOP.md, GROQ_PROMPT_SOP.md
- **Layer 2 (React):** ConfigPanel, IssuePicker, StrategyGenerator, OutputViewer
- **Layer 3 (APIs):** Direct browser calls (no backend proxy)

### Phase 4: Stylize ✅
- **UI:** Clean, gradient-based design
- **UX:** Responsive, accessible, intuitive
- **Mobile:** Fully responsive layout

### Phase 5: Trigger
- **Status:** Ready for production
- **Deployment:** GitHub Pages, Vercel, or local

---

## 🔐 Security Notes

⚠️ **Credentials Storage:**
- Stored in **browser localStorage** only
- NOT sent to any external server
- NOT persisted to disk
- Cleared when browser cache is cleared

⚠️ **API Calls:**
- JIRA: Direct CORS call (Basic Auth)
- Groq: Direct CORS call (Bearer Token)
- No backend proxy

✅ **Recommendations:**
- Use API tokens instead of passwords
- Don't share the app with credentials in localStorage
- Clear browser data on shared computers
- For production: Deploy with backend proxy to hide keys

---

## 📁 Project Files

```
chapter_03_BLAST_FW_JIRA_AI_AGENT/
├── test-strategy-generator.html    # Main app (download this)
├── JIRA_API_SOP.md                 # JIRA integration guide
├── GROQ_PROMPT_SOP.md              # Groq integration guide
└── README_LIGHTWEIGHT.md            # This file
```

---

## 🛠️ Technologies

- **React 18** — UI framework (React CDN)
- **Babel** — JSX transpilation (in-browser)
- **Fetch API** — HTTP requests
- **LocalStorage** — Credential persistence
- **Vanilla CSS** — Styling (no dependencies)

**Zero npm dependencies** — works without any build process

---

## 🐛 Troubleshooting

| Problem | Solution |
|---------|----------|
| JIRA error 401 | Check email & API token at https://id.atlassian.com/manage-profile/security/api-tokens |
| JIRA error 403 | Ensure your JIRA account has proper permissions |
| Groq error 401 | Check API key at https://console.groq.com/keys |
| Groq error 429 | Rate limited — wait 60 seconds, then retry |
| No issues fetched | Check JIRA project exists, verify base URL |
| Strategy is slow | Normal — Groq processes in 10-30 seconds |
| White blank screen | Clear browser cache & hard refresh (Ctrl+F5) |

---

## 🚀 Deployment

### Option 1: Local (Simplest)
```
1. Save test-strategy-generator.html
2. Double-click to open
3. Works immediately
```

### Option 2: GitHub Pages
```
1. Upload to GitHub repo
2. Enable GitHub Pages
3. Access via: https://username.github.io/repo/test-strategy-generator.html
```

### Option 3: Vercel
```
1. Upload HTML to Vercel
2. Deploy instantly
3. Get public URL
```

---

## 📚 Related Documentation

| Document | Purpose |
|----------|---------|
| JIRA_API_SOP.md | How to set up JIRA authentication |
| GROQ_PROMPT_SOP.md | How to use Groq API with RICE-POT framework |
| README.md | Original project documentation |
| B.L.A.S.T.md | Framework specification |
| RICE_POT.md | Prompt engineering framework |

---

## 🎯 What Gets Generated?

The app generates test strategies with these sections:

- **Objective** — What are we testing for?
- **Scope** — What will be tested
- **Out of Scope** — What will NOT be tested
- **Test Approach** — How will we test
- **Risk Assessment** — What could go wrong
- **Test Types** — Unit, integration, E2E, security, etc.
- **Timeline** — Estimated duration
- **Resources** — Team & tools needed
- **Deliverables** — What we'll produce

All generated as **clean, actionable JSON**.

---

## 💡 Tips & Tricks

### 🎨 Save Credentials
- Credentials are auto-saved to browser localStorage
- Don't need to re-enter them each time
- Clear them from browser settings if needed

### 🔄 Generate Multiple Strategies
- Select a different issue
- Click "Generate Strategy" again
- Download each one separately

### 📋 Copy & Paste
- Click "Copy to Clipboard"
- Paste into Slack, email, or documents
- JSON format works with any tool

### 🔍 Debug Issues
- Open browser DevTools (F12)
- Check Console tab for errors
- Network tab shows API calls

---

## 📞 Support & Questions

For help with:
- **JIRA issues:** See JIRA_API_SOP.md
- **Groq issues:** See GROQ_PROMPT_SOP.md
- **B.L.A.S.T. Framework:** See B.L.A.S.T.md
- **RICE-POT Framework:** See RICE_POT.md

---

## ✅ Framework Compliance

**B.L.A.S.T. Compliant:**
- ✅ Blueprint: Discovery complete, schema defined
- ✅ Link: APIs tested and verified
- ✅ Architect: 3-layer architecture implemented
- ✅ Stylize: UI refined and responsive
- ✅ Trigger: Ready for deployment

**RICE-POT Compliant:**
- ✅ Role: Expert QA Architect
- ✅ Instructions: Step-by-step generation
- ✅ Context: JIRA issue integration
- ✅ Example: JSON structure provided
- ✅ Parameters: Production-ready quality
- ✅ Output: Valid JSON format
- ✅ Tone: Technical and precise

---

## 📝 License

Part of **AI-Tester-3X** framework  
Repository: https://github.com/Prasannachamp/AI-Tester-3X

---

**Last Updated:** 2026-06-10  
**Status:** ✅ Production Ready  
**Framework:** B.L.A.S.T. v1.0 + RICE-POT  
**Size:** Single HTML file (~24 KB)
