# 🤖 Groq API Integration SOP

## Objective
Generate comprehensive test strategies using Groq's Mixtral 8x7B or Llama 2 70B models via OpenAI-compatible API.

---

## Prerequisites
- Groq API account (free tier available)
- API key from https://console.groq.com
- Understanding of test strategy frameworks (B.L.A.S.T., RICE-POT)

---

## Step 1: Get Groq API Key

1. Visit **https://console.groq.com/keys**
2. Click **Create API Key**
3. Copy and save securely

---

## Step 2: API Endpoint

```
https://api.groq.com/openai/v1/chat/completions
```

---

## Step 3: Authentication

```javascript
const headers = {
    'Authorization': `Bearer ${API_KEY}`,
    'Content-Type': 'application/json',
};
```

---

## Step 4: Request Format (OpenAI Compatible)

```javascript
{
    "model": "mixtral-8x7b-32768",  // or "llama-2-70b-chat"
    "messages": [
        {
            "role": "user",
            "content": "Your prompt here..."
        }
    ],
    "temperature": 0.7,
    "max_tokens": 2000
}
```

---

## Step 5: Test Strategy Generation Prompt (RICE-POT)

### Role
**Expert QA Test Strategy Architect**

### Instructions
- Generate comprehensive test strategy JSON
- Include objective, scope, risk assessment, test types
- Base output on JIRA issue description
- Return ONLY valid JSON (no markdown, no explanations)

### Context
- JIRA Issue Key, Title, Description
- Project scope and acceptance criteria
- Available testing resources

### Example
```json
{
    "objective": "Ensure e-commerce checkout flow is reliable and secure",
    "scope": "Payment gateway integration, form validation, order creation",
    "outOfScope": "Third-party payment provider testing",
    "testTypes": ["functional", "security", "performance"],
    "timeline": "2 weeks"
}
```

### Parameters
- **Accuracy:** Must align with JIRA issue context
- **Quality:** Production-ready documentation
- **Format:** Valid JSON only

### Output
**JSON file with test strategy structure (no code, no comments)**

### Tone
Technical, precise, actionable

---

## Sample Request

```bash
curl -X POST https://api.groq.com/openai/v1/chat/completions \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "mixtral-8x7b-32768",
    "messages": [
      {
        "role": "user",
        "content": "Generate a test strategy for a login page feature..."
      }
    ],
    "temperature": 0.7,
    "max_tokens": 2000
  }'
```

---

## Response Format

```json
{
    "choices": [
        {
            "message": {
                "content": "{...test strategy JSON...}"
            }
        }
    ]
}
```

---

## Available Models

| Model | Context | Speed | Cost |
|-------|---------|-------|------|
| **mixtral-8x7b-32768** | 32K tokens | Fast ⚡ | Cheap 💰 |
| **llama-2-70b-chat** | 4K tokens | Medium ⚡⚡ | Medium 💰💰 |

---

## Error Handling

| Status | Meaning | Action |
|--------|---------|--------|
| 200 | Success | Parse response |
| 400 | Bad request | Check JSON format |
| 401 | Invalid token | Verify API key |
| 429 | Rate limited | Wait 60 seconds, retry |
| 500 | Server error | Try again later |

---

## Rate Limits (Free Tier)

- **Requests per minute:** 30
- **Tokens per minute:** 6,000
- **Concurrent requests:** 1

---

## Temperature Parameter Guide

- **0.0** = Deterministic (same output every time)
- **0.5** = Balanced
- **0.7** = Recommended for creative test strategies
- **1.0** = Maximum randomness

---

## Token Calculation

Average test strategy response: **500-1500 tokens**

```
Tokens = Prompt length + Response length
Cost = Tokens / 1,000,000 * Price per 1M tokens
```

---

## References
- [Groq Console](https://console.groq.com)
- [Groq API Docs](https://console.groq.com/docs)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference/chat/create)
