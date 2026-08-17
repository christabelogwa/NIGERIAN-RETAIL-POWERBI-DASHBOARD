# Nigerian Multi-Branch Retail — Power BI Dashboard

An end-to-end Power BI project built from a real Nigerian multi-branch retail dataset, combining **GoFrugal POS** (sales & inventory) and **Zoho Books** (accounting) exports into a single four-page executive dashboard.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-8B7FD6?style=flat)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=flat)

---

## 📌 Project Overview

A 4-store Nigerian retailer tracked sales through GoFrugal POS and accounting through Zoho Books — two systems that never talked to each other. Leadership had no single view of revenue, stock health, or cash owed and owing.

This project builds one Power BI workbook that lets management move from a high-level number down to the exact store, product, customer, or vendor behind it, without opening either source system.

**Business questions answered:**
- Which stores and categories drive revenue, and where is margin strongest?
- Where is stock tied up, and which products are at risk of going stale?
- How much is owed to the business, and how fast is it being collected?
- How much does the business owe, and what's coming due?

---

## 🗂️ Data Sources

| Source | System | Data |
|---|---|---|
| Sales & Inventory | GoFrugal POS | Store-level transactions, stock/inventory ledger |
| Accounting | Zoho Books | Customer invoices & receipts, vendor bills & payments |

Data covers 4 stores (Store_01–Store_04) across multiple product categories, with a reporting window running through mid-2026.

---

## 🛠️ Tools & Process

- **Power Query** — cleaned and shaped raw exports: standardized IDs, fixed data types and currency fields, removed duplicates, flagged (not silently deleted) data-quality issues like negative stock
- **Power BI Desktop** — data model, DAX measures, and the full 4-page report build
- **DAX** — custom measures for revenue, return rate, gross margin %, weeks-of-supply, cash collected/paid, and aging buckets
- **Data model** — star-schema pattern: Sales, Inventory, AR and AP fact tables linked to shared Store, Product, Customer/Vendor and Date dimensions, so every page filters consistently

---

## 📊 Dashboard Pages

### 1. Sales Overview
Weekly revenue, units, returns and margin by store.
- **1.26bn** total revenue · **850.49K** units sold · **431.22K** returns · **419.68M** gross margin
- Revenue by store, revenue by category, sales trend, average gross margin % by store, full store performance table


### 2. Inventory Snapshot
Stock value, dead-stock risk and margin opportunity.
- **3.96bn** retail value · **1.42M** stock quantity · **1.89bn** stock cost · **2.07bn** margin opportunity
- Stock value by category and store, slowest-moving products by weekly supply, negative-stock data quality flag (275 rows)

### 3. Customer & Accounts Receivable
Invoicing, collection and aging.
- **3.78bn** invoiced · **89.8%** collected via bank transfer
- Invoice status breakdown, cash collection trend, top 10 customers by revenue, payment receivable aging


### 4. Vendor & Accounts Payable
Billing, payment and aging.
- **2.70bn** billed · **379.10M** outstanding · **2.81bn** cash paid out
- Top vendors by outstanding balance, cash payment trend, bill status breakdown, accounts payable aging

---

## 🔎 Key Insights

- **Store_04** leads on revenue, units and margin %, but also accounts for **59% of all returns** chain-wide — a store-specific process issue worth auditing, not a chain-wide product problem.
- **275 SKUs** show negative stock (−123,313 units / −₦123.48M cost value), pointing to a POS/inventory sync gap that a monthly reconciliation would catch.
- One product line (Vaseline) shows a weeks-of-supply figure far above every other SKU — a clear dead-stock/markdown candidate.
- Both the AR collection trend and AP payment trend drop sharply in the same month (August), suggesting a shared data cut-off rather than two independent cash events.
- **89.8%** of customer receipts arrive via bank transfer, reflecting the shift toward digital payment rails in Nigerian retail.

Full write-up with recommendations: see [`presentation/`](./presentation).

---

## 📁 Repo Structure

```
├── README.md
├── dashboard/
│   └── retail-dashboard.pbix          # Power BI source file
├── screenshots/
│   ├── 01-sales-overview.png
│   ├── 02-inventory-snapshot.png
│   ├── 03-accounts-receivable.png
│   └── 04-accounts-payable.png
└── presentation/
    └── Nigerian Retail Power BI Dashboard - Presentation.pptx
```

---

## 👤 Author

**Ogwa Nkemnasom** — Data Analyst
📧 christabelogwa1@gmail.com
