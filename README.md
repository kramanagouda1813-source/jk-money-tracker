# 💰 JK Money Tracker

Personal finance dashboard with Google Sheet backend — enter transactions, view charts, track debts. All in one place.

![JK Logo](logo.png)

---

## 🚀 Setup Guide (One-time, ~15 minutes)

### Step 1 — Create your Google Sheet

1. Go to [sheets.google.com](https://sheets.google.com) → Create a new blank spreadsheet
2. Name it **JK Money Tracker**
3. Click **Extensions → Apps Script**

---

### Step 2 — Run the Sheet Setup Script

1. In Apps Script, delete any existing code
2. Copy the entire contents of **`setup_sheet.gs`** and paste it
3. Click **Save** (💾)
4. Click **Run** → select function `setupJKMoneyTracker`
5. Allow permissions when asked
6. ✅ Your sheet now has 4 tabs: Entries, Monthly Summary, Category Summary, Debt Tracker

---

### Step 3 — Deploy the Web App

1. In Apps Script, click **+ New file** → Script
2. Name it `web_app`
3. Copy the entire contents of **`web_app.gs`** and paste it
4. Click **Save**
5. Click **Deploy → New Deployment**
6. Click the gear icon ⚙️ → Select **Web App**
7. Set:
   - **Execute as:** Me
   - **Who has access:** Anyone
8. Click **Deploy**
9. Copy the **Web App URL** (looks like `https://script.google.com/macros/s/XXXXX/exec`)

> ⚠️ Every time you edit `web_app.gs`, you must create a **New Deployment** to apply changes.

---

### Step 4 — Connect the Dashboard

**Option A — GitHub Pages (recommended, permanent URL):**

1. Fork this repository on GitHub
2. Upload your **logo.png** to the repo root
3. Open `index.html` → find this line near the top of the `<script>` section:
   ```
   const LOGO_URL = 'https://raw.githubusercontent.com/YOUR_USERNAME/jk-money-tracker/main/logo.png';
   ```
   Replace `YOUR_USERNAME` with your GitHub username
4. Go to **Settings → Pages → Source: main branch → / (root)**
5. Your dashboard is live at: `https://YOUR_USERNAME.github.io/jk-money-tracker`

**Option B — Use directly from your computer:**
1. Open `index.html` in any browser
2. Paste your Web App URL in the setup banner at the top

---

### Step 5 — First-time Dashboard Setup

1. Open your dashboard URL
2. You'll see a yellow setup banner at the top
3. Paste your **Web App URL** from Step 3
4. Click **Save**
5. ✅ Your data loads automatically

---

## 📱 Add to Phone Home Screen

**Android (Chrome):**
Open dashboard URL → tap ⋮ menu → "Add to Home Screen"

**iPhone (Safari):**
Open dashboard URL → tap Share → "Add to Home Screen"

Your dashboard now opens like an app — no browser bar.

---

## 📖 How to Use

### Adding a Transaction
1. Tap **＋** (bottom right on phone) or **+ Add Entry** (desktop)
2. Fill in:
   - **Date** — auto-filled as today, change if needed
   - **Category** — choose from dropdown (Personal or Business)
   - **Amount** — type the number
   - **Type** — tap Income or Expense
   - **Mode** — tap Cash, UPI, or Online
   - **Description** — optional, but useful (e.g. "10 can Areca – Shikaripura")
3. Tap **Save Entry**
4. Dashboard refreshes automatically

### Adding a Loan / Debt
1. Tap **🏦** button or go to Debt Tracker tab → **+ Add Loan**
2. Fill principal, interest rate, EMI, outstanding balance
3. Leave **Lender** blank for now — add names later directly in the Google Sheet
4. Set status: Active / Paid / Overdue
5. Tap **Save Loan**

### Viewing Data
- **Dashboard tab** — KPI cards, charts, category breakdown
- **Transactions tab** — full list, filterable by month, with delete option
- **Debt Tracker tab** — all loans with total outstanding

### Filtering by Month
Click any month tab at the top to filter all charts and tables to that month. Click **All** to see everything.

---

## 📊 Google Sheet Tabs

| Tab | Purpose |
|---|---|
| **Entries** | Your daily transaction log — color-coded (green = income, red = expense) |
| **Monthly Summary** | Auto-calculated totals per month with charts |
| **Category Summary** | Breakdown by category with % of total expenses |
| **Debt Tracker** | All loans, EMIs, outstanding balances |

---

## 🗂️ Category Reference

| Category | Group |
|---|---|
| Food | 🟢 Personal |
| Diesel / Fuel | 🟢 Personal |
| Rent (Room) | 🟢 Personal |
| Home | 🟢 Personal |
| Medical | 🟢 Personal |
| Luxury | 🟢 Personal |
| Car Maintenance | 🟢 Personal |
| With Friends | 🟢 Personal |
| Investment | 🟢 Personal |
| Others | 🟢 Personal |
| Marketing | 🔵 Business |
| Logistics | 🔵 Business |
| Compliance | 🔵 Business |
| Office Expenses | 🔵 Business |
| Office Rent | 🔵 Business |
| Godown Rent | 🔵 Business |
| Salary | 🔵 Business |
| Networking | 🔵 Business |
| Growth | 🔵 Business |

---

## 🔄 Refreshing Data

The dashboard loads fresh data from your Sheet every time you:
- Open the dashboard
- Tap **↻ Refresh** button
- Save a new entry (auto-refreshes)

---

## ⚠️ Troubleshooting

| Problem | Solution |
|---|---|
| "Could not load data" | Check Web App URL is correct. Re-deploy web_app.gs as a new deployment |
| Data not updating after entry | Tap ↻ Refresh. Note: Apps Script can take 5–10 seconds |
| Charts not showing | Make sure you have at least one entry in the Sheet |
| Setup banner keeps showing | Paste the full Web App URL starting with `https://script.google.com` |
| Deleted entry still shows | Tap Refresh — deletion takes a moment to sync |

---

## 📁 Files

```
jk-money-tracker/
├── index.html        ← Main dashboard (open this in browser)
├── setup_sheet.gs    ← Run once to set up Google Sheet
├── web_app.gs        ← Deploy as Web App in Apps Script
├── logo.png          ← Upload your JK logo here
└── README.md         ← This guide
```

---

## 🔒 Privacy

- All data stays in **your** Google Sheet in **your** Google Drive
- The Web App only reads/writes to your own Sheet
- No third-party servers involved
- GitHub Pages only serves the HTML/JS — no data passes through GitHub

---

Built for personal use · JK Money Tracker · 2025–2026
