# SuperStore Executive Dashboard

An interactive, single-file HTML dashboard built on the classic SuperStore retail dataset (2018–2021). Designed as a boardroom-ready report for executive review of sales, profit, and operational performance.

![status](https://img.shields.io/badge/status-active-brightgreen) ![type](https://img.shields.io/badge/type-static%20HTML-blue)

## Overview

This dashboard turns 9,994 raw order records into a fully interactive performance report, with cross-filtering across year, region, customer segment, product category, and ship mode. No build step, no server, no dependencies beyond a CDN-loaded charting library — open the file in any browser and it works.

**Key figures covered:** $2.84M total revenue · $286K total profit · 9,994 orders · 793 unique customers · FY2018–FY2021

## Features

- **KPI summary bar** — revenue, profit, margin, order count, and customer count at a glance
- **Global filters** — year, region, segment, category, and ship mode, all cross-filtering every chart simultaneously
- **11 interactive charts** — monthly sales/profit trend, category revenue share, profit margin by sub-category (color-coded by health), regional performance, segment growth by year, sales-vs-profit bubble chart, discount impact analysis, top states by revenue, ship mode breakdown, year-over-year growth, and an order-volume heatmap
- **Automated insights panel** — plain-language callouts that recalculate live as filters change
- **Zero dependencies** — single HTML file, data embedded inline, Chart.js loaded from CDN

## Tech Stack

- HTML5 / CSS3 / vanilla JavaScript
- [Chart.js](https://www.chartjs.org/) (via CDN)
- Data sourced from `SuperStore_Data.xlsx` (Excel/CSV-style retail transaction data)

## Getting Started

No installation required.

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
open SuperStore_Executive_Dashboard.html   # macOS
# or just double-click the file / drag it into your browser
```

Alternatively, serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/SuperStore_Executive_Dashboard.html
```

## Project Structure

```
.
├── SuperStore_Executive_Dashboard.html   # the dashboard (data + logic, all-in-one)
├── SuperStore_Data.xlsx                  # source dataset
└── README.md
```

## Data

The dashboard uses standard SuperStore fields: Order Date, Ship Date, Ship Mode, Customer, Segment, Region, State, Category, Sub-Category, Sales, Quantity, Discount, and Profit. All filtering and aggregation happens client-side in the browser.

## Customizing

- **Update the data:** regenerate the embedded JSON array from a new export of the source spreadsheet and swap it into the `<script>` block.
- **Change the palette:** colors are defined as CSS variables (`--navy`, `--teal`, `--amber`, `--red`, `--gold`) near the top of the `<style>` block.
- **Add a chart:** follow the existing pattern — add a `<canvas>` card to the HTML, then a `render...()` function in the script that reads from the filtered dataset and calls `upsertChart()`.


