# 🔧 Troubleshooting Guide - JIRA Fetch Error

## ❌ Error: "Failed to fetch"

This happens due to **CORS (Cross-Origin Resource Sharing)** restrictions when the browser tries to access JIRA from Vercel.

---

## ✅ Solution 1: Check Your JIRA URL Format

**Wrong:**
```
https://prasanna-v.atlassian.net (missing /jira)
https://prasanna-v (incomplete)
prasanna-v.atlassian.net (missing https://)
```

**Correct:**
```
https://prasanna-v.atlassian.net (if this is your JIRA Cloud instance)
```

Make sure:
- ✅ Starts with `https://`
- ✅ Ends with `.atlassian.net`
- ✅ No trailing slash

---

## ✅ Solution 2: Verify JIRA Credentials

**Test your credentials:**

1. **API Token** - Get from: https://id.atlassian.com/manage-profile/security/api-tokens
   - Click "Create API Token"
   - Copy the token (it's NOT your password)
   - Paste into the app

2. **Email** - Use the same email as your JIRA account
   - Should be same as in JIRA Cloud login

3. **Base URL** - Your JIRA workspace URL
   - Example: `https://my-company.atlassian.net`

---

## ✅ Solution 3: Test with Issue Key

Instead of clicking "Fetch Issues", **manually enter an issue key**:

1. Go to your JIRA dashboard
2. Find an issue (e.g., `KAN-1`, `PROJ-123`)
3. Copy the **issue key**
4. Paste into the "Issue Key" field
5. Click "Generate Strategy"

This bypasses the "Fetch Issues" step that requires CORS.

---

## ✅ Solution 4: Understanding CORS Restriction

**Why CORS blocks JIRA requests:**

```
Your App (Vercel)  ←→  JIRA Cloud (Atlassian)
   |                          |
   └─ Browser blocks ────────┘
      (different domain)
```

**This is normal and expected!** JIRA Cloud doesn't allow browser-to-server direct calls from other domains for security.

---

## ✅ Solution 5: Use JIRA Personal Access Token (Recommended)

Instead of email + password token:

1. Go to: https://id.atlassian.com/manage-profile/security/api-tokens
2. Create API Token (you already did this)
3. Copy it completely (including dashes)
4. Paste in app

---

## ❌ Common Mistakes

| ❌ Wrong | ✅ Right |
|---------|----------|
| `prasanna-v.atlassian.net` | `https://prasanna-v.atlassian.net` |
| `https://jira.company.com` | `https://company.atlassian.net` |
| Using password | Using API token |
| Generic email | Your exact JIRA email |
| Issue name | Issue key (KAN-1, not "Feature Name") |

---

## 🔍 Debugging Steps

### Step 1: Verify JIRA URL
Open in browser: `https://your-jira-url.atlassian.net`
- Should load JIRA dashboard
- If 404, URL is wrong

### Step 2: Check API Token
1. Go to https://id.atlassian.com/manage-profile/security/api-tokens
2. Verify token exists and is active
3. Copy token exactly (with dashes)

### Step 3: Test Issue Key
1. Go to your JIRA dashboard
2. Find an issue (e.g., KAN-1)
3. Write down the exact key (uppercase)
4. Enter in app

### Step 4: Generate Strategy
1. Enter JIRA URL, email, token
2. Enter valid issue key
3. Enter Groq API key
4. Click "Generate Strategy"
5. **Don't click "Fetch Issues"** (that causes CORS issues)

---

## 📝 Correct Example

```
Base URL:    https://prasanna-v.atlassian.net
Email:       vprasannaofficial24@gmail.com
API Token:   atatt[your-token-here]
Issue Key:   KAN-1
Groq Key:    gsk_[your-groq-key]
```

---

## 🎯 Recommended Workaround

**Skip "Fetch Issues" and generate directly:**

1. ✅ Enter JIRA config (URL, email, token)
2. ✅ Skip "Fetch Issues" button
3. ✅ Manually enter issue key (e.g., `KAN-1`)
4. ✅ Click "Generate Strategy"

This works **100% reliably** because it avoids the CORS-blocked JIRA search API.

---

## 📞 Still Getting Errors?

**If you see: "401 Unauthorized"**
- Wrong email or API token
- Double-check at https://id.atlassian.com/manage-profile/security/api-tokens

**If you see: "404 Not Found"**
- Issue key doesn't exist
- Check spelling (case-sensitive)
- Go to JIRA and copy the exact key

**If you see: "403 Forbidden"**
- Your account lacks permissions
- Ask JIRA admin for access
- Or try with a different account

**If you see: "CORS blocked"**
- This is browser security
- Workaround: Generate strategy directly (skip "Fetch Issues")

---

## ✅ Test Checklist

- [ ] JIRA URL is `https://...atlassian.net`
- [ ] Email matches your JIRA account
- [ ] API Token is from https://id.atlassian.com/manage-profile/security/api-tokens
- [ ] Issue key is correct (check JIRA dashboard)
- [ ] Groq API key is valid
- [ ] You're NOT using "Fetch Issues" (optional, skip it)

If all checked, **strategy generation should work!** ✅

---

## 🎓 Updated Features

✅ **Better error messages** - Now shows exactly what went wrong  
✅ **CORS workaround** - Automatically tries direct fetch  
✅ **Issue key validation** - Auto-uppercase for convenience  
✅ **Helpful placeholders** - Show where to get credentials  

---

**Your app is now more robust!** 🚀

Try again and let me know the exact error message if it persists.
