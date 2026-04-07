# I.S.K Capital — Official Website

> **Navigate Markets with Precision.**  
> Capital markets education and investor onboarding for East Africa.

---

## 🌍 About I.S.K Capital

**I.S.K Capital** is a Kampala, Uganda-based financial education and market access firm. We turn complete beginners into confident, informed investors on the **Uganda Securities Exchange (USE)** and **Nairobi Securities Exchange (NSE)** — and beyond.

We operate at the crossroads of financial literacy and real market access: teaching the theory, then walking clients directly to their first trade through our network of accredited broker partners.

📍 **Headquarters:** Kampala, Uganda  
📧 **Email:** i.s.k.capital07@gmail.com  
📞 **WhatsApp:** +256770668626  
🌐 **Live Site:** [your-github-username.github.io/isk-capital](https://your-github-username.github.io/isk-capital)

---

## 📄 Website Overview

This repository contains the complete source code for the I.S.K Capital public-facing website — a **3-page static site** built with pure HTML, CSS, and JavaScript. No frameworks, no dependencies, no build step. Open `index.html` and it works.

### Pages

| Page | Purpose |
|---|---|
| **Home** | Brand intro, market ticker, services overview, broker partners, social proof |
| **Education Hub** | Course tiers ($0–$65), full 8-module curriculum, seminar types, 30-min call booking form |
| **About & Institutional** | Company story, values, institutional services, contact form |

---

## 💼 Services Covered

### Retail Investor Education
Structured courses starting at **USD $15** covering:
- Capital markets overview (USE & NSE context)
- Market stakeholders — regulators, brokers, custodians
- Stock market terminology
- Stocks, bonds, ETFs, REITs & derivatives
- Technical and fundamental analysis
- CSD account (USE) and CDSC account (NSE) setup
- Key investment tips and portfolio construction

### CSD / CDSC Account Facilitation
Guided onboarding to the Central Securities Depository (Uganda) and Central Depository & Settlement Corporation (Kenya) through ISK Capital's partner broker network.

### Institutional & Corporate Services
- Corporate financial literacy seminars
- School and university financial education programmes
- Hedge fund and asset manager advisory
- NGO and development institution programmes

### Free 30-Minute Discovery Call
Personalised session with an ISK Capital analyst — no obligation, no sales pressure.

---

## 🏦 Broker Partner Network

| Partner | Market |
|---|---|
| Dyer & Blair Investment Bank Uganda | USE |
| Crested Capital | USE |
| SBG Securities | USE / NSE |
| Chipper Cash | East Africa |
| UAP Old Mutual | Uganda |

---

## 📈 Markets Covered

- 🇺🇬 Uganda Securities Exchange (USE) — Primary
- 🇰🇪 Nairobi Securities Exchange (NSE) — Primary
- 🌍 Pan-African markets (JSE, DSE, GSE) — Secondary
- 🇪🇺 European markets — On demand

---

## 💰 Course Pricing Tiers

| Tier | Price | Key Inclusions |
|---|---|---|
| Market Starter | Free | Newsletter, Module 1 preview, glossary |
| Foundation | $15 | All 8 modules, PDF guides, community access |
| Analyst Track | $35 | Foundation + technical/fundamental analysis, live Q&A |
| Market Ready | $65 | All above + 1-on-1 session, broker intro, CSD setup guide |
| Institutional | Custom | Seminars, school programmes, hedge fund advisory |

---

## 🛠️ Tech Stack

```
HTML5         — Structure and content
CSS3          — Styling, animations, responsive layout (no framework)
Vanilla JS    — Page navigation, form handling, scroll animations
Google Fonts  — Barlow Condensed + Barlow + DM Serif Display
Google Sheets — Lead capture via Apps Script webhook (form submissions)
GitHub Pages  — Hosting
```

No npm. No build tools. No dependencies. Just files.

---

## 🚀 Deployment (GitHub Pages)

### 1. Clone the repository
```bash
git clone https://github.com/your-username/isk-capital.git
cd isk-capital
```

### 2. Open locally
```bash
# Just open index.html in your browser — no server needed
open index.html
```

### 3. Deploy to GitHub Pages
```
1. Push to your GitHub repository
2. Go to Settings → Pages
3. Set Source to: main branch / root (/)
4. Your site will be live at: https://your-username.github.io/isk-capital
```

---

## 📊 Google Sheets Integration (Lead Capture)

All booking and contact forms submit data to a **Google Sheets spreadsheet** via a Google Apps Script webhook. To activate:

### Step 1 — Create the Apps Script
1. Open [script.google.com](https://script.google.com)
2. Create a new project
3. Paste the following:

```javascript
function doPost(e) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const data  = JSON.parse(e.postData.contents);
  
  sheet.appendRow([
    data.timestamp,
    data.form,
    data.name,
    data.email || '',
    data.phone || '',
    data.contact || '',
    data.goal || '',
    data.interest || '',
    data.time || '',
    data.type || '',
    data.org || '',
    data.message || '',
    data.notes || ''
  ]);

  return ContentService
    .createTextOutput(JSON.stringify({ status: 'ok' }))
    .setMimeType(ContentService.MimeType.JSON);
}
```

### Step 2 — Deploy as Web App
```
Deploy → New Deployment → Web App
Execute as: Me
Who has access: Anyone
→ Copy the Web App URL
```

### Step 3 — Paste into index.html
```javascript
// In index.html, find this line and replace with your URL:
const SHEET_URL = 'YOUR_GOOGLE_APPS_SCRIPT_URL_HERE';
```

### Data Captured Per Submission

| Field | Forms |
|---|---|
| Timestamp | All |
| Form type | All |
| Name | All |
| Email | Call booking, Contact |
| Phone / WhatsApp | Call booking, Hero |
| Interest / Goal | Hero, Call booking |
| Preferred call time | Call booking |
| Enquiry type | Contact |
| Organisation | Contact |
| Message / Notes | Contact, Call booking |

---

## 📁 File Structure

```
isk-capital/
│
├── index.html          # Complete 3-page website (self-contained)
├── logo.png            # ISK Capital logo (also embedded as base64)
├── README.md           # This file
└── .gitignore          # (optional)
```

> **Note:** The logo and banner images are embedded as base64 directly inside `index.html` for maximum portability — the site works as a single file with zero external dependencies.

---

## ✏️ Customisation Guide

### Update Contact Details
Search `index.html` for:
```
+256770668626          ← phone / WhatsApp number
i.s.k.capital07@gmail.com  ← email address
```
Replace with current details.

### Update Course Prices
Search for `$15`, `$35`, `$65` and update the figures and feature lists in the **Education Hub** section.

### Update Market Ticker
Find the `.marquee-track` div and edit the ticker items with live or current figures.

### Add/Remove Broker Partners
Find the `.partners-grid` div in Page 1 and add or remove `.partner-pill` elements.

---

## 📞 Contact & Enquiries

| Channel | Details |
|---|---|
| 📧 Email | i.s.k.capital07@gmail.com |
| 💬 WhatsApp | +256770668626 |
| 📍 Location | Kampala, Uganda |
| 🕐 Hours | Mon–Sat, 8:00 AM – 8:00 PM (EAT / GMT+3) |

---

## 📜 License

© 2024 I.S.K Capital. All rights reserved.  
This repository is the proprietary website of I.S.K Capital, Kampala, Uganda.  
Unauthorised copying, redistribution, or commercial use of this code is prohibited.

---

<div align="center">
  <strong>I.S.K Capital</strong> · Kampala, Uganda<br>
  <em>Navigate Markets with Precision.</em>
</div>
