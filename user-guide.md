---
layout: default
title: User guide
permalink: /user-guide/
description: How to add PulseDB charts and KPI cards to Confluence pages.
---

# User guide

<p class="lede">Everything needed to add a PulseDB chart to a Confluence page, in about a minute.</p>

## 1. Add a chart to a page

1. Open a Confluence page and click **Edit**.
2. Type `/PulseDB` and press **Enter**. The PulseDB settings panel opens.
3. Fill in the settings (below) and click **Save**.
4. Publish the page. The chart appears for everyone who can view the page.

To change a chart later, edit the page, click the chart, and click the pencil icon.

## 2. Settings, step by step

### Database
Choose a database from the list. The list shows the databases you can see, newest first.

If a database isn't listed, open it in Confluence, copy the link from the browser's address bar, paste it into **Or paste a database link or ID**, and click **Use link**.

### Chart
Pick one of six visuals:

| Visual | Best for |
|---|---|
| KPI summary card | One headline number, such as total budget or open items |
| Bar chart | Comparing groups, such as spend by department |
| Horizontal bar chart | Comparing groups with long names |
| Donut chart / Pie chart | Showing each group's share of the whole |
| Line chart | Trends over time, such as items due per month |

Add an optional **Title**. Without one, PulseDB writes a title from your settings.

### Group by (not used by KPI cards)
Choose the column that makes the bars or slices. PulseDB offers only the columns it can group:

- **Choice (select) columns:** one group per choice. A row with several choices counts once in each.
- **Person columns:** one group per person, shown by name.
- **Text columns:** one group per distinct value (capital letters don't matter).
- **Checkbox columns:** "Yes" and "No".
- **Date columns:** choose **Group dates by** day, week (starting Monday), month, quarter, or year.

Rows with an empty value appear as **(Empty)**.

### Calculation
- **Count of rows:** how many rows are in each group.
- **Sum, Average, Minimum, Maximum:** choose a **Number column** to measure. Empty cells are skipped.

### Filter (optional)
Show only the rows that match one rule, such as *Status is Approved*, *Amount is greater than 20000*, *Due Date is on or after 2026-01-01*, or *Blocked is checked*. Text comparisons ignore capital letters. Dates use the format `YYYY-MM-DD`.

### Number format
Add a symbol **Before** (such as `$`) or **After** (such as `%`), and choose **Decimal places**. When you pick a number column that already has a currency or percent format in Confluence, PulseDB fills this in for you.

## 3. Reading a chart

Under every chart, a line shows:

- the **source database** (click to open it),
- how many **rows** were used, and how many matched the filter,
- the **time** the chart was loaded,
- a **Refresh** button that reloads the data without reloading the page.

Two small labels may appear:

- **Top 11 + Other:** the chart had more than 12 groups. The 11 largest are shown and the rest are combined into "Other", so the chart stays readable. Line charts over dates always show every period.
- **First 2,000 rows:** the database has more than 2,000 rows. PulseDB reads the first 2,000 to keep pages fast.

## 4. Good to know

- **Always live.** Charts read the database each time the page is viewed. Edits to the database appear on the next view or Refresh.
- **Permissions.** Each reader sees a chart built from the data *they* can access. Readers without access to the source database see a short note instead.
- **Line charts over dates** leave out rows without a date, and show periods with no rows as zero (for counts and totals).
- **Supported column types:** text, number, choice (select), date, checkbox, and person. Other column types (links, attachments, Jira issues, and so on) can't be charted yet and aren't offered in the settings.

## 5. Troubleshooting

| What you see | What to do |
|---|---|
| "Set up your PulseDB chart" | The chart has no settings yet. Edit the page, click the chart, and click the pencil icon. |
| "You can't view the source data" | Ask the database owner for access, then click Refresh. |
| "Source database not found" | The database was deleted, moved, or restricted. Edit the chart and choose another database. |
| "This chart needs attention" | A column used by the chart was renamed or deleted. Edit the chart and pick the column again. |
| "PulseDB license needed" | A Confluence admin can start a free trial or subscribe in Confluence administration under **Apps**. |
| A database is missing from the list | Paste the database link instead (see **Database** above). |

Still stuck? [Contact support]({{ '/support/' | relative_url }}).
