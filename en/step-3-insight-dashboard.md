# STEP 3. Interactive HTML dashboard — insight-dashboard

> If STEP 1 was a "static report", this one builds an **interactive dashboard** you can filter and click through — packaged into a single HTML file. It opens directly in the browser and needs no server.

---

## ① Create the Skill

```
Create a Skill named insight-dashboard. This Skill should take data or analysis results and generate an interactive HTML dashboard as a single file. Please follow these rules exactly.

[Technical approach]
- Load external libraries only via CDN (Chart.js etc.), and produce a single self-contained HTML file. It should open by double-clicking in a browser — no install and no server required.

[Brand colors]
- Dark color #232F3E, accent color #FF9900, white background

[Layout]
1. Top header band: Full-width dark background (#232F3E) with the dashboard title on the left (white, bold) and creation date on the right. A 4px orange (#FF9900) line below the band.
2. KPI card row: Right below the header, place 3-4 key metric cards. Each card shows a large number and a label.
3. Chart area: 2-3 charts (bar / donut / line) chosen to fit the data. Charts should be responsive (resize with the window).
4. Filters: Dropdowns or buttons at the top for segment / period / etc. Selecting them updates charts and tables in real time.
5. Detail table: A sortable table at the bottom (click header to sort). Header row on dark background (#232F3E) with white text; body rows alternate light gray.
6. Clean system font, subtle shadows and rounded corners on cards / charts, generous whitespace.

[Body language]
- Write labels and descriptions in English

[Save location]
- Save to the ./output/ folder. Create the folder if it doesn't exist. Filename format: dashboard-YYYY-MM-DD.html.

[Auto-trigger]
- Auto-apply this Skill whenever the word "dashboard" is mentioned.

Save the Skill so it can be reused.
```

---

## ② Approve permissions

If asked for permission → **Allow**.

## ③ Verify creation

If you see `insight-dashboard` in the **Agents & skills panel**, you're set.

---

## ④ Try it out

```
Build an interactive dashboard from the ./customer-usage.csv data. Show API call counts by customer, distribution by segment, and top customers, and let me filter by segment.
```

→ Double-click the generated `./output/dashboard-YYYY-MM-DD.html` and it opens directly in the browser.

<figure><img src="../images/insight-dashboard-sample.png" alt="insight-dashboard result example"><figcaption>Example dashboard opened in a browser (KPI cards · top customers bar · segment donut · filter)</figcaption></figure>

---

## ⑤ (Optional) Keep refining through chat

```
Add a "monthly trend" line chart to the dashboard you just made, and highlight only the top 5 customers.
```

---

> **Difference vs "Apps" in STEP 5-2:** Apps run inside Quick, while this one **outputs an HTML file you can share with anyone** (email attachment, SharePoint upload).

---

> **Next:** [STEP 4. Connection — connect external tools →](step-4-connection.md)
