# NBTI Innovator Intake Form

Intake form for the **NBTI / NextGen Innovation Challenge 2026** closing session ("Funding Readiness Pathway"), delivered by Valerie Wilcox, Innovation Liaison Officer — PhoennixAI × UKALD.

Collects each innovator's readiness stage and support needs after the session, replacing 150 unstructured follow-up emails with a single routed pipeline.

**Live form:** _add Vercel URL here after deploy_

---

## What it does

A single-page, three-step form (no backend, no database):

1. **About You** — name, email, project/company name
2. **Readiness Ladder** — Idea / Validated / MVP-Traction / Investor-Ready
3. **Support Needed** — pitch support, investor intro, grant guidance + free-text notes

Submissions are delivered by email via [FormSubmit.co](https://formsubmit.co) — free, no account, no server.

| Recipient | Role |
|---|---|
| `valerie@phoennixai.com` | Primary (in the fetch URL) |
| `eloyiadah@ukald.com` | CC (`_cc` field in `formData`) |

Respondents automatically receive a confirmation email (`_autoresponse`), and submissions arrive formatted as a table (`_template: 'table'`).

---

## Deploy (Vercel)

1. Ensure the form file is named `index.html` at the repo root
2. Import the repo at [vercel.com](https://vercel.com) → **Add New Project** → deploy (no build settings needed — it's a static file)
3. Copy the production URL into the distribution documents

## ⚠️ Before the session — activation is mandatory

FormSubmit requires a **one-time activation** per recipient address:

1. Deploy, then submit one test entry yourself
2. FormSubmit emails an activation link to **valerie@phoennixai.com** — it must be clicked
3. Submit a **second** test entry and confirm it arrives in both inboxes

Until the activation link is clicked, submissions vanish silently — the form will show "Submitted!" while nothing is delivered. Do not skip the second test.

## Changing recipients

Both addresses live in `index.html`:

- Primary: the `fetch('https://formsubmit.co/ajax/...')` URL
- CC: the `_cc` value in the `formData` object

Changing the primary address restarts the activation requirement for the new address.

---

## Stack

- Single self-contained HTML file — inline CSS/JS, base64-embedded NBTI + UKALD logos, Inter via Google Fonts
- No framework, no build step, no dependencies
- FormSubmit.co AJAX endpoint for delivery

---

Prepared by PhoennixAI for the NextGen Innovation Challenge 2026 · July 2026
