# 📖 JIRA API Integration SOP

## Objective
Fetch JIRA issue details securely using JIRA Cloud REST API v3 with Basic Authentication.

---

## Prerequisites
- JIRA Cloud instance with admin access
- API token generated from JIRA account
- Email address associated with JIRA account

---

## Step 1: Generate JIRA API Token

1. Go to **Atlassian Account Settings** → https://id.atlassian.com/manage-profile/security/api-tokens
2. Click **Create API Token**
3. Label it (e.g., "Test Strategy Generator")
4. **Copy and save** the token securely

---

## Step 2: Get Your JIRA Base URL

- Format: `https://{your-workspace}.atlassian.net`
- Example: `https://my-company.atlassian.net`

---

## Step 3: Authenticate with Basic Auth

```javascript
const auth = btoa(`${email}:${apiToken}`);
const headers = {
    'Authorization': `Basic ${auth}`,
    'Accept': 'application/json',
};
```

---

## Step 4: Fetch Issue Details

### List Issues (with JQL filter)
```
GET /rest/api/3/search?jql=project=KAN&maxResults=50
```

### Get Specific Issue
```
GET /rest/api/3/issue/{issueKey}
```

### Response Format
```json
{
  "key": "KAN-1",
  "fields": {
    "summary": "Feature title",
    "description": {
      "content": [
        {
          "content": [
            {
              "text": "Detailed description..."
            }
          ]
        }
      ]
    }
  }
}
```

---

## Error Handling

| Status | Meaning | Action |
|--------|---------|--------|
| 200 | Success | Process response |
| 401 | Invalid token/email | Verify credentials |
| 403 | No permission | Check account permissions |
| 404 | Issue not found | Verify issue key exists |
| 429 | Rate limited | Wait before retrying |

---

## Security Notes
⚠️ **Browser-only implementation:** API token is stored in browser memory only (localStorage). It's NOT persisted to disk or servers.

⚠️ **Recommendation:** For production, use a backend proxy to hide API credentials.

---

## References
- [JIRA Cloud REST API Documentation](https://developer.atlassian.com/cloud/jira/rest/v3)
- [API Token Generation Guide](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)
