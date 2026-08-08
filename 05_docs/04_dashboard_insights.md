**Bongo Consumer Products Ltd. | January–December 2025**

---

## 📊 Executive Summary Insights

<p align="center">
  <img src="04_power_bi/dashboard_image/01_executive_summary.PNG" alt="Executive Dashboard" width="800">
</p>

### Insight 1: Total Supply Chain Leakage Stands at ৳29.22 Lakh

| Category | Leakage (৳) | Share |
|---|---|---|
| Procurement | 1,522,132 | 52.54% |
| Inventory | 1,065,218 | 35.63% |
| Logistics | 267,809 | 9.58% |
| Fulfillment | 67,200 | 2.25% |
| **Grand Total** | **2,922,360** | **100%** |

More than half of BCPL's total cost leakage originates at the Procurement stage — meaning the biggest problem is not transportation or returns, but the purchasing process itself. This suggests supplier pricing controls are weak, standard contract prices are not being consistently followed, and emergency/off-contract purchases are occurring too frequently.

**Recommendations:**
- Conduct contract audits for top variance suppliers
- Implement a price variance monitoring dashboard
- Tighten emergency purchase approval workflows
- Introduce quarterly supplier performance reviews

---

### Insight 2: Inventory Leakage is the Second Largest Cost Drain

Inventory leakage = ৳10.65 lakh (35.63% of total leakage). This indicates that working capital is unnecessarily tied up in inventory — creating cash flow pressure and inefficient use of warehouse space.

**Recommendations:**
- Implement ABC-XYZ inventory classification
- Launch a dead stock liquidation program
- Review safety stock policies
- Restrict reorders on slow-moving SKUs

---

### Insight 3: Top 5 Contributors Drive a Disproportionate Share of Leakage

| Contributor | Leakage (৳) |
|---|---|
| MegaChem Corp | 403,528 |
| Sylhet Regional Depot | 361,305 |
| Chattogram Regional Hub | 300,354 |
| GlobalPack Imports | 287,066 |
| Khulna Distribution Center | 269,142 |

Leakage is not evenly distributed across the supply chain — a small number of suppliers and depots are creating a disproportionate amount of leakage. This is a classic Pareto pattern. Focusing on high-impact contributors first will deliver faster ROI than launching a company-wide initiative.

**Recommendations:**
- Prioritize MegaChem Corp supplier audit
- Conduct Sylhet Depot inventory review
- Renegotiate GlobalPack Imports contract

---

### Insight 4: Procurement Leakage is Highly Volatile Month-to-Month

April (~৳190K) and November (~৳170K) show the highest Procurement leakage spikes. This is not random — unusually high spending in specific periods signals seasonal demand surges, emergency procurement, or planning failures.

**Recommendations:**
- Root-cause analysis of April and November purchase orders
- Monitor emergency PO ratio monthly
- Strengthen seasonal procurement planning

---

### Insight 5: Inventory Leakage Remains Consistently High Year-Round

Inventory leakage holds steady at approximately ৳75K–100K every month. This is not a one-time event — it reflects a structural inventory management issue embedded in current inventory policy.

**Recommendations:**
- Review reorder points
- Measure demand forecasting accuracy
- Make monthly aging reports mandatory
- Introduce warehouse-wise inventory KPIs

---

### Insight 6: Logistics and Fulfillment are Currently Secondary Concerns

Logistics (9.58%) and Fulfillment (2.25%) combined account for only ~12% of total leakage. If management resources are limited, solving Procurement and Inventory first delivers the highest ROI.

**Priority Ranking:** Procurement → Inventory → Logistics → Fulfillment

---

## 📦 Procurement Leakage Analysis

<p align="center">
  <img src="04_power_bi/dashboard_image/02_procurement_leakage.PNG" alt="Procurement Leakage" width="800">
</p>

### Insight 1: Nearly 1 in 3 Purchase Orders is Flagged for Variance

| KPI | Value |
|---|---|
| Total Procurement Leakage | ৳1,522,132 |
| Total POs | 1,062 |
| Flagged POs | 317 (29.8%) |
| Avg Price Variance | 6% |

317 flagged POs indicate this is not an isolated incident — it reflects a systematic control weakness in the procurement process. An average variance of 6% is particularly significant given the project's 5% threshold, meaning BCPL's purchasing operations are consistently operating outside acceptable bounds.

**Recommendations:**
- Implement automatic approval escalation when variance exceeds 5%
- Validate standard price at point of PO creation
- Introduce a monthly supplier variance scorecard

---

### Insight 2: Emergency Orders are the Most Expensive Purchase Type

| Order Type | Avg Variance |
|---|---|
| Emergency | 20.8% |
| Rush | 17.1% |
| Regular | 3.3% |

This is the most powerful insight in the Procurement analysis. Emergency orders carry a variance more than 6x higher than regular orders. This suggests the issue is less about supplier behavior and more about planning failure — BCPL is effectively paying a premium because the procurement team is being forced into last-minute buying.

**Recommendations:**
- Monitor emergency order frequency as a KPI
- Review safety stock policies
- Recalculate reorder points for high-volume SKUs
- Introduce forecast accuracy measurement

---

### Insight 3: Import Suppliers Drive 64% of Procurement Leakage

| Supplier Type | Leakage Share |
|---|---|
| Import | 63.86% |
| Local | 36.14% |

Despite being fewer in number, import suppliers contribute a disproportionately high share of leakage — likely due to foreign currency fluctuation, import lead time pressure, and weaker contract negotiation leverage.

**Recommendations:**
- Renegotiate contracts with strategic import suppliers
- Evaluate alternative local sourcing options
- Establish long-term procurement agreements to reduce price volatility

---

### Insight 4: Just 3 Import Suppliers Dominate Procurement Leakage

| Supplier | Leakage (৳) |
|---|---|
| MegaChem Corp | 403,528 |
| GlobalPack Imports | 287,066 |
| AsiaFood Commodities | 239,877 |
| **Combined** | **~930,471 (59%)** |

Addressing these 3 suppliers alone could recover the majority of procurement leakage — no company-wide supplier management program required.

**Recommendations:**
- MegaChem Corp: contract compliance audit + price renegotiation
- GlobalPack Imports: alternative sourcing analysis + multi-supplier strategy
- AsiaFood Commodities: leverage purchase volume for better pricing

---

### Insight 5: Procurement Leakage Follows a Seasonal Pattern

Major spikes: February (~৳175K), April (~৳190K), July (~৳155K), November (~৳165K). Procurement discipline significantly deteriorates in certain months — likely driven by peak-demand periods pushing the business toward emergency buying.

**Recommendations:**
- Audit April and November purchase history
- Build a seasonal procurement planning calendar
- Implement peak-season inventory buffering

---

## 🏭 Inventory Leakage Analysis

<p align="center">
  <img src="04_power_bi/dashboard_image/03_inventory_leakage.PNG" alt="Inventory Leakage" width="800">
</p>

### Insight 1: Dead Stock Rate at 23%, Average Age 126 Days

| KPI | Value |
|---|---|
| Inventory Leakage | ৳1,065,218 |
| Dead Stock Snapshots | 336 |
| Dead Stock % | 23% |
| Avg Dead Stock Age | 126 Days |
| Total Holding Cost | ৳4,596,484 |

In FMCG, inventory is meant to move fast. A 126-day average stock age and 23% dead stock rate means roughly 1 in 4 items has become slow-moving or dead stock — tying up cash, wasting warehouse space, and creating future write-off risk.

**Recommendations:**
- Conduct monthly inventory aging reviews
- Launch a 90+ day stock reduction initiative
- Add inventory turnover KPI to the management dashboard

---

### Insight 2: Sylhet Regional Depot is the Largest Inventory Leakage Driver

| Warehouse | Dead Stock Leakage (৳) |
|---|---|
| Sylhet Regional Depot | 361,305 (Highest) |
| Chattogram Regional Hub | 300,354 |
| Khulna Distribution Center | 269,142 |
| Tejgaon Central Warehouse | 134,417 (Lowest) |

This is not a warehouse efficiency issue — it signals a demand-supply mismatch. Sylhet's demand was overestimated, excess stock was pushed to the depot, and redistribution did not happen.

**Recommendations:**
- Conduct a Sylhet depot inventory audit
- Launch a slow-moving SKU transfer program
- Build a region-specific forecasting model

---

### Insight 3: Packaged Food Drives Nearly 50% of Dead Stock Leakage

Packaged Food = 49.88% of dead stock leakage (average age: 132 days). The inventory problem is not warehouse-wide — one product category is creating a disproportionate share of the issue.

> *"Inventory is not excessive everywhere; inventory is excessive in the wrong products."*

**Recommendations:**
- Rationalize Packaged Food SKUs
- Run a promotional clearance campaign
- Review category-wise reorder parameters

---

### Insight 4: Largest Holding Cost Burden is in the 31–60 Day Bucket

| Stock Age | Holding Cost (Approx.) |
|---|---|
| 0–30 Days | ~৳1.0M |
| 31–60 Days | ~৳1.7M (Highest) |
| 61–90 Days | ~৳0.85M |
| 91–120 Days | ~৳0.55M |
| 120+ Days | ~৳0.45M |

Counterintuitively, the biggest holding cost burden comes from the 31–60 day bucket, not 120+ days. Dead stock is the visible problem, but general overstocking is the hidden problem.

**Recommendations:**
- Optimize reorder quantities
- Recalibrate safety stock levels
- Shift to demand-driven replenishment

---

### Insight 5: Dead Stock Pattern is Consistent Across All Warehouses

Packaged Food is the dominant dead stock contributor across Sylhet, Chattogram, and Khulna — not just one location. This is not a warehouse execution issue; it points to an upstream planning problem.

> *"If only one warehouse had the problem, blame the warehouse manager. When all warehouses show the same pattern, the problem is central planning."*

**Recommendations:**
- Conduct category-level forecasting review
- Align Sales & Operations Planning (S&OP)
- Redesign Packaged Food replenishment policy

---

## 🚚 Logistics Leakage Analysis

<p align="center">
  <img src="04_power_bi/dashboard_image/04_logistics_leakage.PNG" alt="Logistics Leakage" width="800">
</p>

### Insight 1: 19% Late Shipment Rate — Nearly 1 in 5 Deliveries Arrives Late

| KPI | Value |
|---|---|
| Total Logistics Leakage | ৳267,809 |
| Late Delivery Penalty | ৳87,000 |
| Late Shipments | 150 |
| Late Shipment Rate | 19% |
| Avg Freight Overrun | 15% |

A significant portion of logistics leakage comes not from transportation costs alone, but from service failure. Late deliveries reduce distributor confidence, create future sales risk, and generate avoidable penalty costs.

**Recommendations:**
- Track route-wise OTIF (On-Time In-Full) as a KPI
- Launch a carrier performance monitoring dashboard
- Implement delay root-cause logging

---

### Insight 2: Route Leakage Ranking

| Route | Total Leakage (৳) |
|---|---|
| Dhaka–Sylhet Highway | ~82K |
| Sylhet Tea Belt | ~62K |
| Khulna–Jessore Belt | ~57K |
| Dhaka–Chattogram Highway | ~38K |
| Chattogram Coastal | ~18K |
| Dhaka Metro | ~11K |

Dhaka–Sylhet Highway is the single largest logistics leakage source, driven primarily by long-distance freight movement. Notably, Sylhet also appears as the worst performer in the Inventory dashboard — reinforcing it as a regional supply chain risk cluster.

---

### Insight 3: Sylhet Tea Belt — A Double Leakage Situation

Sylhet Tea Belt: ~32% cost overrun, ~৳22K+ in late penalties. This route simultaneously incurs excess freight costs and late delivery penalties — placing it in the most dangerous quadrant of the Route Risk Matrix.

**Recommendations:**
- Launch a dedicated route improvement program
- Optimize rural delivery scheduling
- Develop seasonal disruption contingency plans

---

### Insight 4: On-Time Delivery at 81% — Below FMCG Standards

| Status | Rate |
|---|---|
| On-Time | 81.25% |
| Late | 17.13% |
| Failed | 1.63% |

FMCG distribution typically targets 95%+ on-time delivery. At 81%, BCPL's logistics network is functional but not reliably consistent — a gap that becomes increasingly expensive as business scales.

**Recommendations:**
- Set OTIF target at ≥95%
- Introduce carrier incentive programs
- Deploy real-time shipment tracking

---

### Insight 5: Dhaka–Chattogram Highway Can Serve as an Internal Benchmark

The Route Risk Matrix shows Dhaka–Chattogram Highway with moderate cost overrun and very low late penalty — making it the network's best-performing route. Its operational practices should be studied and replicated across higher-risk routes.

---

## 🎯 Root Cause Analysis — 80/20 Leakage Drivers

<p align="center">
  <img src="04_power_bi/dashboard_image/05_root_cause_analysis.PNG" alt="Root Cause" width="800">
</p>

### Insight 1: Leakage is Concentrated — Targeted Fixes are Possible

| KPI | Value |
|---|---|
| Total Leakage | ৳2,922,360 |
| Top 3 Suppliers Drive | 59% of Procurement Leakage |
| Top 3 Routes Drive | 76% of Logistics Leakage |
| Top 3 Warehouses Drive | 82% of Inventory Leakage |

Although BCPL's problem is systemic, the solution can be targeted. Management does not need to intervene everywhere — fixing a small number of high-impact entities can drive majority of the leakage reduction.

---

### Insight 2: Just 3 Suppliers Drive 59% of Procurement Leakage

Out of 15 suppliers, only 3 are responsible for the majority of procurement leakage. If the procurement team can effectively manage these 3 suppliers, the impact on overall leakage will be significant.

---

### Insight 3: Just 3 Routes Drive 76% of Logistics Leakage

Two of the top 3 problematic routes are Sylhet-related — further establishing Sylhet as a high-risk region across multiple supply chain dimensions.

---

### Insight 4: Sylhet Region Appears Repeatedly Across All Dimensions

Sylhet appears in:
- ✅ Highest inventory leakage warehouse (Sylhet Regional Depot)
- ✅ Highest absolute logistics leakage (Dhaka–Sylhet Highway)
- ✅ Worst late delivery rate (Sylhet Tea Belt)
- ✅ Highest dead stock concentration

> *"Sylhet is not a symptom. Sylhet may be the root cause cluster."*

**Recommendation:** Launch a dedicated Sylhet Supply Chain Review — covering depot inventory, route performance, demand forecasting, and regional planning alignment.

---

### Insight 5: MegaChem Corp is the Single Largest Leakage Contributor Project-Wide

MegaChem Corp alone generates ৳403,528 in leakage — the highest of any single entity across the entire project. Improving this one supplier relationship would have an outsized impact on overall leakage reduction.

---

## 💰 Recovery Plan & Recommendations Insights

<p align="center">
  <img src="04_power_bi/dashboard_image/06_recommendations.PNG" alt="Recovery Plan & Recommendations" width="800">
</p>

### Insight 1: 54.52% of Total Leakage is Recoverable

| KPI | Value |
|---|---|
| Total Leakage | ৳29.22 Lakh |
| Estimated Recoverable Savings | ৳15.93 Lakh |
| Recovery Potential | 54.52% |
| Unrecoverable | 45.48% |

Not all leakage can be recovered — some has already been incurred due to market conditions, currency fluctuation, and fuel costs. However, BCPL still has the opportunity to recover more than half of its identified leakage through targeted interventions.

---

### Insight 2: Procurement Improvements Deliver the Highest ROI

| Category | Recoverable Savings (৳) |
|---|---|
| Procurement | 913,279 |
| Inventory | 532,609 |
| Logistics | 147,295 |

> *"If BCPL can only invest in one area, Procurement should be first."*

Procurement savings alone exceed the combined recoverable savings from Inventory and Logistics.

---

### Insight 3: Just 7 Initiatives Can Deliver ৳9.53 Lakh in Annual Savings

| Priority | Action | Est. Saving (৳) | Difficulty |
|---|---|---|---|
| 1 | Re-negotiate MegaChem Corp | 241,000 | Medium |
| 2 | Dual-source GlobalPack Imports | 172,000 | Medium |
| 3 | Demand forecasting — Sylhet depot | 180,000 | High |
| 4 | Route optimization — Sylhet Tea Belt | 34,000 | Medium |
| 5 | Renegotiate AsiaFood Commodities | 144,000 | Low |
| 6 | SKU rationalization — Packaged Food | 150,000 | High |
| 7 | Carrier review — Khulna–Jessore Belt | 32,000 | Low |
| | **Total** | **953,000** | |

Management does not need 100 initiatives. A few targeted actions can deliver outsized impact — exactly what executive audiences want to hear.

---

### Insight 4: ROI-Based Implementation Sequencing

Not all initiatives should start simultaneously. Sequencing by effort-to-impact ratio maximizes early wins.

**Phase 1 (0–3 Months) — Quick Wins:**
- AsiaFood Commodities renegotiation → ৳144,000 (Low difficulty)
- Khulna–Jessore carrier review → ৳32,000 (Low difficulty)
- MegaChem Corp contract review → ৳241,000 (Medium difficulty)

**Phase 2 (3–6 Months):**
- GlobalPack Imports dual-sourcing → ৳172,000
- Sylhet Tea Belt route optimization → ৳34,000

**Phase 3 (6–12 Months) — Structural Fixes:**
- Sylhet depot demand forecasting → ৳180,000
- Packaged Food SKU rationalization → ৳150,000

---

### Insight 5: AsiaFood Commodities is the Most Attractive Quick Win

AsiaFood Commodities: ৳144,000 in estimated savings, Low difficulty. Among all initiatives, this offers the most attractive effort-to-impact ratio and could realistically be executed within the first 30 days.

---

### Insight 6: Sylhet Confirmed as High-Priority Recovery Target

Sylhet-related recovery opportunities:
- Sylhet Depot demand forecasting → ৳180,000
- Sylhet Tea Belt route optimization → ৳34,000

This is consistent with findings across every other dashboard page — Sylhet-focused supply chain improvement should be treated as a standalone strategic initiative.

---

*All data is synthetic. Cost assumptions are illustrative estimates for portfolio demonstration purposes.*
