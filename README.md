# 📊 Sales Dashboard – Power BI

An interactive Power BI dashboard built on the **Financial Sample** dataset (700 rows, 16 columns) to analyse sales, units sold and profit margin across segments, countries, products and time.

![Dashboard Preview](Screenshot%202026-11-20%20220352.png)

---

## 📁 Repository Structure

```
├── Financial Sample.xlsx                  # Source dataset
├── dashboardsafa4.pbix                    # Power BI report file
├── Screenshot 2026-11-20 220352.png       # Dashboard preview
└── README.md
```

---

## 🎯 Objective
Build a clean, interactive report that answers:
- How much are we selling, and how profitable is it?
- Which segments, countries and products drive sales and profit?
- How do sales behave month by month and year over year?

---

## 🛠️ Tools Used
- Microsoft Power BI Desktop (Power Query, DAX, Bookmarks, Buttons)
- Microsoft Excel (source data)

---

## 1️⃣ Importing & Preprocessing the Dataset
1. Imported `Financial Sample.xlsx` using **Get Data → Excel Workbook**.
2. Cleaned in **Power Query**:
   - Trimmed extra spaces from column names (e.g. `" Sales"`, `"Units Sold "`).
   - Set correct data types (Date → Date, Sales/Profit/Units → Decimal, Year/Month Number → Whole number).
   - `Discount Band` contained the text **"None"**, which got read as null (53 rows) – replaced with `"None"` so it is treated as a valid category.
   - Checked for duplicates (0 found) and fixed formatting issues.
   - Removed unused columns and kept the important ones.
3. Created a **Profit Margin %** measure:
   ```DAX
   Profit Margin % = DIVIDE(SUM(Financial_Sample[Profit]), SUM(Financial_Sample[Sales]))
   ```

---

## 2️⃣ Visuals Used (7+)
| # | Visual | Purpose |
|---|--------|---------|
| 1 | Card – Sum of Sales | Total revenue (₹119M) |
| 2 | Card – Sum of Units Sold | Total volume (1.1M) |
| 3 | Card – Profit Margin % | Overall profitability (14%) |
| 4 | Line chart – Sales by Month | Trend, 2013 vs 2014 |
| 5 | Donut chart – Sales by Segment | Share of each segment |
| 6 | Bar chart – Units Sold by Product | Product volume ranking |
| 7 | Column chart – Sales by Country | Country comparison |
| 8 | Line & clustered column – Sales and Profit Margin % by Product | Sales vs margin per product |
| 9 | Slicers – Year, Segment, Country | Filtering |

---

## 3️⃣ Buttons, Bookmarks & Images
- **Bookmarks + Buttons:** `2013` and `2014` buttons filter the report to that year; the **Reset** button restores the default view.
- **Images:** Dashboard logo/icon in the header and a themed background image to match the green dark theme.

---

## 4️⃣ Report Organisation
- Clear title: **"Sales Dashboard"** with a divider line.
- Consistent **green-on-dark** colour theme throughout.
- KPI cards on top, filters on the right, charts arranged in a tidy grid below.
- Every visual has a title, and the layout is aligned for easy reading.

---

## 5️⃣ 💡 Insightful Analysis

### Headline numbers
| Metric | Value |
|---|---|
| Total Sales | ₹118.7M |
| Units Sold | 1.13M |
| Total Profit | ₹16.9M |
| Profit Margin | 14.2% |

### Key insights
**By Segment**
- **Government** is the biggest segment (**44.2%** of sales) and also very profitable (**21.7%** margin).
- **Small Business** contributes **35.7%** of sales but with a lower margin (**9.8%**).
- **Enterprise** brings **16.5%** of sales but has a **negative margin (-3.1%)**, so it is actually losing money. Pricing/discount strategy needs a review here.
- **Channel Partners** and **Midmarket** are tiny in sales (~1.5% and ~2%) but have very high margins (**73%** and **28%**) – good growth opportunity.

**By Product**
- **Paseo** is the clear leader: highest sales (₹33M, **27.8%**) and highest units sold (**338K**, almost double any other product).
- **Amarilla** has the **best profit margin (15.9%)** even though its sales are mid-range.
- **Velo** has the **lowest margin (12.6%)**, and **Carretera** has the lowest sales and units.

**By Country**
- Sales are spread almost evenly across all 5 countries (17–21% each), so there is no over-dependence on one market.
- **USA** has the highest sales (₹25.0M) but the **lowest margin (12.0%)**.
- **Germany
