# STEP 5. Quick's distinctive features

> A tour of Quick's four differentiating features: Scheduled Agent · Apps · Knowledge Graph · Browser.

---

## 5-1. Scheduled Agent

Create an agent that runs automatically on a schedule.

```
Create an agent that summarizes my email and reports it to me every morning at 8 AM.
```

→ Approve it and it's created and test-run immediately. The result shows up in the **Activity Feed** at the top right.

> **Note:** Requires an email Connection. (Connected in STEP 4.)

Variation:

```
Create an agent that alerts me 30 minutes before a meeting if I haven't prepared for it.
```

---

## 5-2. Apps (dashboard)

Build an app that runs inside Quick. Unlike the STEP 3 HTML dashboard, this one runs inside Quick itself.

```
Build a customer-usage dashboard app from the ./customer-usage.csv data. Let me see API call counts by customer, distribution by segment, and top customers at a glance.
```

An app with summary cards, monthly trend, and Top 10 charts is generated in the Apps screen inside Quick.

<figure><img src="../images/apps-dashboard-sample.png" alt="Apps dashboard example"><figcaption>Customer-usage dashboard running inside Amazon Quick Apps</figcaption></figure>

---

## 5-3. Knowledge Graph

Visually inspect the context Quick has accumulated (accounts, people, organizational relationships).

**1.** Open **Settings** (gear icon at bottom-left) **→ My Context → Knowledge Graph**.

**2.** Inspect the nodes and relationships.

**3.** You can also ask through chat.

```
Show me my Knowledge Graph
```

or

```
What does Quick know about [account / person]?
```

---

## 5-4. Browser (fetch from the real web)

**Setup:**

**Settings → Customization → Browser** → pick a browser (Chrome, etc.) → toggle **"Use my browser"** ON → follow the instructions to paste `chrome://inspect/#remote-debugging` and click **Enable remote debugging** → **Test Connection** → confirm "Connected".

<figure><img src="../images/quick-browser-customization.png" alt="Browser customization"><figcaption>Browser customization</figcaption></figure>

**Try it:**

```
Open the search results page for "wireless keyboard" on Coupang and give me a table of the top 5 products with name, price, and rating.
```

→ Quick actually opens the browser and reads the page. It uses your existing login and cookies.

<figure><img src="../images/browser-coupang-page.png" alt="Coupang search results page"><figcaption>Coupang "wireless keyboard" search results page that Quick opens and reads</figcaption></figure>

<figure><img src="../images/browser-coupang-summary.png" alt="Coupang top 5 products table"><figcaption>Top 5 products extracted from the page and organized into a name / price / rating table</figcaption></figure>

> **Tip:** Searches on some sites (like Naver) may fail because the site blocks scraping. If Coupang search is blocked, giving the product **URL directly** and asking "summarize this product's reviews" is more reliable.

---

> **Next:** [STEP 6. Final check →](step-6-checklist.md)
