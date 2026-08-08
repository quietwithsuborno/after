All DAX measures are stored in the `_Measures` table in Power BI.

---

## 📦 Procurement Measures

```dax
Total Procurement Leakage =
SUMX(
    vw_procurement_price_variance,
    vw_procurement_price_variance[total_leakage_amount]
)
```

```dax
Procurement Leakage % =
DIVIDE([Total Procurement Leakage], [Grand Total Leakage]) * 100
```

```dax
Avg Variance % =
AVERAGE(vw_procurement_price_variance[variance_pct])
```

```dax
Flagged PO Count =
COUNTROWS(
    FILTER(
        vw_procurement_price_variance,
        vw_procurement_price_variance[is_leakage_flagged] = 1
    )
)
```

```dax
Rush Emergency Order % =
DIVIDE(
    COUNTROWS(
        FILTER(
            vw_procurement_price_variance,
            vw_procurement_price_variance[order_type] IN {"Rush", "Emergency"}
        )
    ),
    COUNTROWS(vw_procurement_price_variance)
) * 100
```

```dax
Total POs Analyzed =
COUNTROWS(vw_procurement_price_variance)
```

**Calculated Column — vw_procurement_price_variance:**
```dax
month_num = MONTH(vw_procurement_price_variance[order_date])
```

---

## 🏭 Inventory Measures

```dax
Total Inventory Leakage =
SUMX(
    vw_inventory_holding_leakage,
    vw_inventory_holding_leakage[dead_stock_holding_cost]
)
```

```dax
Dead Stock Count =
COUNTROWS(
    FILTER(
        vw_inventory_holding_leakage,
        vw_inventory_holding_leakage[is_dead_stock] = TRUE()
    )
)
```

```dax
Dead Stock % =
DIVIDE(
    COUNTROWS(
        FILTER(
            vw_inventory_holding_leakage,
            vw_inventory_holding_leakage[is_dead_stock] = TRUE()
        )
    ),
    COUNTROWS(vw_inventory_holding_leakage)
) * 100
```

```dax
Avg Stock Age Days =
AVERAGEX(
    FILTER(
        vw_inventory_holding_leakage,
        vw_inventory_holding_leakage[is_dead_stock] = TRUE()
    ),
    vw_inventory_holding_leakage[stock_age_days]
)
```

```dax
Total Holding Cost =
SUM(vw_inventory_holding_leakage[holding_cost])
```

**Calculated Column — vw_inventory_holding_leakage:**
```dax
age_bucket_order =
SWITCH(
    TRUE(),
    vw_inventory_holding_leakage[stock_age_days] <= 30,  1,
    vw_inventory_holding_leakage[stock_age_days] <= 60,  2,
    vw_inventory_holding_leakage[stock_age_days] <= 90,  3,
    vw_inventory_holding_leakage[stock_age_days] <= 120, 4,
    5
)
```

---

## 🚚 Logistics Measures

```dax
Total Logistics Leakage =
SUMX(
    vw_logistics_cost_overrun,
    vw_logistics_cost_overrun[total_leakage_per_shipment]
)
```

```dax
Total Late Penalty =
SUM(vw_logistics_cost_overrun[late_penalty])
```

```dax
Late Shipment Count =
COUNTROWS(
    FILTER(
        vw_logistics_cost_overrun,
        vw_logistics_cost_overrun[is_late] = 1
    )
)
```

```dax
Late Shipment % =
DIVIDE(
    COUNTROWS(
        FILTER(
            vw_logistics_cost_overrun,
            vw_logistics_cost_overrun[is_late] = 1
        )
    ),
    COUNTROWS(vw_logistics_cost_overrun)
) * 100
```

```dax
Avg Freight Overrun % =
AVERAGE(vw_logistics_cost_overrun[overrun_pct])
```

**Calculated Column — vw_logistics_cost_overrun:**
```dax
month_num_logistics = MONTH(vw_logistics_cost_overrun[shipment_date])
```

---

## 📋 Fulfillment Measures

```dax
Total Fulfillment Leakage =
SUMX(
    vw_fulfillment_error_cost,
    vw_fulfillment_error_cost[total_leakage_per_order]
)
```

```dax
Return Rate % =
DIVIDE(
    COUNTROWS(
        FILTER(
            vw_fulfillment_error_cost,
            vw_fulfillment_error_cost[is_return] = 1
        )
    ),
    COUNTROWS(vw_fulfillment_error_cost)
) * 100
```

---

## 💰 Grand Total Measures

```dax
Grand Total Leakage =
[Total Procurement Leakage] +
[Total Inventory Leakage] +
[Total Logistics Leakage] +
[Total Fulfillment Leakage]
```

---

## 🔍 Root Cause — Pareto Measures

```dax
Cumulative Supplier Leakage % =
VAR CurrentLeakage =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(
            ALL(vw_leakage_by_supplier_route),
            vw_leakage_by_supplier_route[leakage_amount] >=
            MAX(vw_leakage_by_supplier_route[leakage_amount])
        )
    )
VAR TotalLeakage =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        ALL(vw_leakage_by_supplier_route)
    )
RETURN
DIVIDE(CurrentLeakage, TotalLeakage) * 100
```

```dax
Cumulative Route Leakage % =
VAR CurrentLeakage =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(
            ALL(vw_leakage_by_supplier_route),
            vw_leakage_by_supplier_route[leakage_amount] >=
            MAX(vw_leakage_by_supplier_route[leakage_amount])
            && vw_leakage_by_supplier_route[dimension_type] = "Route"
        )
    )
VAR TotalLeakage =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(
            ALL(vw_leakage_by_supplier_route),
            vw_leakage_by_supplier_route[dimension_type] = "Route"
        )
    )
RETURN DIVIDE(CurrentLeakage, TotalLeakage) * 100
```

```dax
Top 3 Supplier Leakage % =
VAR Top3 =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        TOPN(
            3,
            FILTER(vw_leakage_by_supplier_route,
                vw_leakage_by_supplier_route[dimension_type] = "Supplier"),
            vw_leakage_by_supplier_route[leakage_amount]
        )
    )
VAR Total =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(vw_leakage_by_supplier_route,
            vw_leakage_by_supplier_route[dimension_type] = "Supplier")
    )
RETURN DIVIDE(Top3, Total) * 100
```

```dax
Top 3 Route Leakage % =
VAR Top3 =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        TOPN(
            3,
            FILTER(vw_leakage_by_supplier_route,
                vw_leakage_by_supplier_route[dimension_type] = "Route"),
            vw_leakage_by_supplier_route[leakage_amount]
        )
    )
VAR Total =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(vw_leakage_by_supplier_route,
            vw_leakage_by_supplier_route[dimension_type] = "Route")
    )
RETURN DIVIDE(Top3, Total) * 100
```

```dax
Top 3 Warehouse Leakage % =
VAR Top3 =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        TOPN(
            3,
            FILTER(vw_leakage_by_supplier_route,
                vw_leakage_by_supplier_route[dimension_type] = "Warehouse"),
            vw_leakage_by_supplier_route[leakage_amount]
        )
    )
VAR Total =
    CALCULATE(
        SUM(vw_leakage_by_supplier_route[leakage_amount]),
        FILTER(vw_leakage_by_supplier_route,
            vw_leakage_by_supplier_route[dimension_type] = "Warehouse")
    )
RETURN DIVIDE(Top3, Total) * 100
```

---

## 💡 Recommendations Measures

```dax
Est. Procurement Savings =
[Total Procurement Leakage] * 0.60
```

```dax
Est. Inventory Savings =
[Total Inventory Leakage] * 0.50
```

```dax
Est. Logistics Savings =
[Total Logistics Leakage] * 0.55
```

```dax
Est. Total Savings =
[Est. Procurement Savings] +
[Est. Inventory Savings] +
[Est. Logistics Savings]
```

```dax
Leakage Recovery % =
DIVIDE([Est. Total Savings], [Grand Total Leakage]) * 100
```

```dax
Remaining Leakage =
[Grand Total Leakage] - [Est. Total Savings]
```
