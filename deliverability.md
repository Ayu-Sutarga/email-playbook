# Deliverability: Getting to the Inbox

Great copy is worthless in the spam folder. These are the habits I use for every campaign.

---

## 1. Light HTML vs heavy HTML
Most outreach tools (like Instantly) send HTML anyway, so the question isn't HTML or not. It's **how heavy**.

| ✅ Light (inbox-friendly) | ⚠️ Heavy (risky for cold email) |
|---|---|
| Paragraphs, line breaks, simple lists | Big hero images and banners |
| One link | Many links, or every item clickable |
| Looks like a person typed it | Looks like a designed promotion |
| Mostly text | Mostly images and code |

**Rule of thumb:** cold email → light. Newsletter to people who opted in → a little heavier is fine, but keep one main call to action.

## 2. Spintax
Sending identical text to hundreds of people looks automated. Spintax varies the wording per recipient:

```
{{RANDOM|Hi|Hello|Dear}} {{firstName}},
I {{RANDOM|thought|was thinking that}} you might want to see...
```

Use it on greetings, transitions and sign-offs. Keep the **core message** the same so your results are still comparable.

## 3. Preheader text
The grey preview line next to the subject in the inbox. If you don't set it, inboxes grab random text (sometimes "View in browser").

```html
<div style="display:none;max-height:0px;overflow:hidden;">{{PREHEADER_TEXT}}</div>
```

Make it **finish the subject's thought**, not repeat it.

## 4. Links
- Link to real, working domains. Test every link before sending.
- Avoid link shorteners in cold email.
- Don't link to a link: a link to a page that redirects again adds risk.

## 5. Unsubscribe
Every newsletter needs a **working** unsubscribe link. Use your sending tool's built-in unsubscribe link or variable rather than a typed-in placeholder. A broken unsubscribe pushes people to click "Report spam" instead, which hurts your sender reputation for every future send.

## 6. UTM naming rules
UTMs tell your analytics where clicks came from. Typos split your data into fake sources.

**My convention (all lowercase, no spaces, hyphens only):**

| Parameter | Use for | Example |
|---|---|---|
| `utm_source` | The list or channel | `newsletter`, `outreach` |
| `utm_medium` | Always the type | `email` |
| `utm_campaign` | Campaign + date | `q3-newsletter-2026-10` |
| `utm_content` | Which element was clicked | `hero-image`, `main-button` |

```
https://example.com/page?utm_source=newsletter&utm_medium=email&utm_campaign=q3-newsletter-2026-10&utm_content=main-button
```

✅ `utm_medium=email` every time
❌ `mailchimp`, `mailschip`, `Email`, `e-mail`. These four "different" mediums are really one.

`utm_content` is underused. It tells you whether people click the **image** or the **button**.

## 7. Before every send
- [ ] Sent a test to myself (Gmail **and** Outlook if possible)
- [ ] Every link clicked and working
- [ ] Preheader set
- [ ] Unsubscribe works
- [ ] UTMs follow the naming rules
- [ ] Spintax renders correctly (no stray `{{` in the test)
