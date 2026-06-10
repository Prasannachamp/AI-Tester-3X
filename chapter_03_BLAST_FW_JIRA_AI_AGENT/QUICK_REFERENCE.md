# 🚀 Quick Reference Guide

## File Location
```
chapter_03_BLAST_FW_JIRA_AI_AGENT/test-strategy-generator.html
```

## 30-Second Setup

### Step 1: Get Credentials
| Service | How to Get | Format |
|---------|-----------|--------|
| **JIRA Base URL** | From JIRA dashboard | `https://workspace.atlassian.net` |
| **JIRA Email** | Your JIRA login | `you@company.com` |
| **JIRA Token** | https://id.atlassian.com/manage-profile/security/api-tokens | `ATATT...` |
| **Groq API Key** | https://console.groq.com/keys | `gsk_...` |

### Step 2: Open HTML File
```
Double-click test-strategy-generator.html
OR
Right-click → Open with → Browser
```

### Step 3: Enter Credentials
```
⚙️ Configuration
├─ JIRA Base URL: paste
├─ JIRA Email: paste
├─ JIRA Token: paste
└─ Groq API Key: paste
```

### Step 4: Generate
```
📋 Select Issue: KAN-1 (or your issue key)
🤖 Generate Strategy: Click button
```

### Step 5: Download
```
📥 Export as JSON: Save to computer
```

---

## Common Commands

| Want to... | Do this |
|-----------|---------|
| **Get JIRA token** | Go to https://id.atlassian.com/manage-profile/security/api-tokens |
| **Get Groq key** | Go to https://console.groq.com/keys |
| **Find JIRA URL** | It's `https://your-workspace.atlassian.net` |
| **Load your issues** | Click "🔍 Fetch Issues" button |
| **Generate strategy** | Select issue → Click "🤖 Generate" → Wait 10-30s |
| **Download JSON** | Click "📥 Export as JSON" |
| **Copy to clipboard** | Click "📋 Copy to Clipboard" |
| **Clear credentials** | Settings → Clear LocalStorage (browser settings) |

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Enter` | Submit any form |
| `Tab` | Move between fields |
| `Ctrl+A` | Select all (for copy) |
| `Ctrl+C` | Copy selected text |

---

## Error Messages & Fixes

```
❌ "JIRA API error: 401"
→ Check email & token
→ Go to https://id.atlassian.com/manage-profile/security/api-tokens

❌ "JIRA API error: 403"
→ Your account lacks permissions
→ Ask JIRA admin for access

❌ "Groq API error: 401"
→ Invalid API key
→ Go to https://console.groq.com/keys to regenerate

❌ "Groq API error: 429"
→ Rate limited (too many requests)
→ Wait 60 seconds, then retry

❌ "Failed to fetch issues"
→ Check JIRA project key (default: KAN)
→ Verify base URL is correct

❌ "White/blank screen"
→ Clear browser cache (Ctrl+Shift+Delete)
→ Hard refresh (Ctrl+F5)
→ Try in different browser
```

---

## File Locations

```
.../chapter_03_BLAST_FW_JIRA_AI_AGENT/

📄 test-strategy-generator.html .......... Main app (download & open this)
📄 JIRA_API_SOP.md ...................... How to set up JIRA auth
📄 GROQ_PROMPT_SOP.md ................... How to use Groq API
📄 README_LIGHTWEIGHT.md ................ Full user guide
📄 README.md ............................ Original project docs
📄 B.L.A.S.T.md ......................... Framework spec
📄 QUICK_REFERENCE.md ................... This file
```

---

## Browser Compatibility

| Browser | Status |
|---------|--------|
| **Chrome** | ✅ Fully supported |
| **Firefox** | ✅ Fully supported |
| **Safari** | ✅ Fully supported |
| **Edge** | ✅ Fully supported |
| **Mobile browsers** | ✅ Responsive |

---

## Data Flow

```
1. You enter JIRA config
   ↓
2. App fetches issue from JIRA
   (JIRA API: GET /rest/api/3/issue/KAN-1)
   ↓
3. App sends issue to Groq AI
   (Groq API: POST /openai/v1/chat/completions)
   ↓
4. Groq generates test strategy JSON
   ↓
5. App displays & exports result
   (You download as JSON file)
```

---

## Credentials Security

🔒 **Where credentials are stored:**
- ✅ In browser localStorage only
- ❌ NOT on any server
- ❌ NOT in cookies
- ❌ NOT in files

🔒 **What to do:**
- ✅ Use API tokens, not passwords
- ✅ Clear browser cache on shared computers
- ✅ Close browser tab when done
- ✅ Generate new API token if compromised

---

## API Rate Limits

| Service | Limit | Retry After |
|---------|-------|-------------|
| **JIRA** | 100 req/minute | 1 minute |
| **Groq** | 30 req/minute (free) | 60 seconds |

---

## FAQ

**Q: Do I need to install anything?**  
A: No! Just open the HTML file. No npm, no build tools needed.

**Q: Is my data saved?**  
A: Only generated strategies are saved (when you export). Credentials stay in browser memory.

**Q: Can I use my JIRA password?**  
A: No! Always use an API token from https://id.atlassian.com/manage-profile/security/api-tokens

**Q: How long does generation take?**  
A: 10-30 seconds (depends on Groq server load).

**Q: Can I run this offline?**  
A: The UI works offline, but API calls need internet.

**Q: How do I delete my credentials?**  
A: Clear browser cache → Settings → Clear browsing data → LocalStorage.

**Q: What issue types are supported?**  
A: Any JIRA issue (Story, Epic, Bug, Task, etc.).

**Q: Can I generate multiple strategies?**  
A: Yes! Select different issues and click "Generate" multiple times.

**Q: Can I share generated strategies?**  
A: Yes! Export as JSON and share the file.

---

## Contact & Support

- **JIRA Help:** https://support.atlassian.com
- **Groq Docs:** https://console.groq.com/docs
- **Framework:** https://github.com/Prasannachamp/AI-Tester-3X

---

**Version:** 1.0  
**Last Updated:** 2026-06-10  
**Status:** ✅ Ready to Use
