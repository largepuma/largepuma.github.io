# Privacy Policy for ReplyWise AI – Amazon Review Reply Assistant

*Last updated: March 14, 2026*

---

## 1. Information We Collect

- **Account information**: Email address and password (hashed with PBKDF2) when you register.
- **Amazon review content**: Text of Amazon customer reviews you choose to process. This content is sent to our servers and to Anthropic's Claude API solely to generate reply suggestions.
- **Usage data**: Number of AI replies generated per month to enforce plan quotas.

---

## 2. How We Use Your Information

- To authenticate your account and maintain your session via JWT tokens.
- To generate AI-powered reply suggestions using Anthropic Claude.
- To track and enforce monthly usage quotas.

---

## 3. Data Storage

- Your JWT tokens and reply history (last 20 entries) are stored locally in your browser via `chrome.storage.local` and never uploaded.
- Account data and usage counters are stored in our database (Cloudflare D1).
- Generated replies may be cached for up to 24 hours on Cloudflare KV to improve performance.

---

## 4. Third-Party Services

| Service | Purpose | Privacy Policy |
|---|---|---|
| Anthropic Claude API | Processes review text to generate reply suggestions | [anthropic.com/legal/privacy](https://www.anthropic.com/legal/privacy) |
| Cloudflare Workers / D1 / KV | Backend infrastructure and data storage | [cloudflare.com/privacypolicy](https://www.cloudflare.com/privacypolicy/) |

---

## 5. Data Sharing

We do not sell, rent, or share your personal data with any third parties except as described in Section 4 above.

---

## 6. Data Retention

- Account data is retained until you delete your account.
- Cached replies are automatically deleted after 24 hours.
- Local browser data (tokens, reply history) is cleared when you log out or uninstall the extension.

---

## 7. Your Rights

You may request deletion of your account and all associated data by contacting us at the email below.

---

## 8. Contact

For privacy-related questions or data deletion requests, please contact:

**[Xianghui Liu / Predicate LLC]**
**[largepuma@gmail.com]**
