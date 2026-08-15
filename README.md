# ◼️ KILLZONES & EXECUTION SUITE [v5]

> Institutional time-and-price delivery engine with strict memory management for TradingView.

Built specifically for high-precision execution across index and commodity futures (NQ, ES, CL, GC). Strips out chart noise, prevents drawing-limit lag, and delivers pure algorithmic order-flow references directly onto dark-theme charts.

<img width="1253" height="751" alt="preview" src="https://github.com/user-attachments/assets/46587047-2241-4276-a3a2-0a676c22f6f3" />

---

### ◾ CORE ARCHITECTURE

**Strict 2-Session Memory Protocol**  
Drawings are strictly managed to preserve chart performance. The engine holds a maximum of two historical sessions per killzone, instantly purging obsolete boxes and lines from memory the moment a new session opens.

**15-Minute Forward Projections**  
A dynamic visual engine. Exactly 15 minutes before an impending session open, a forward line and label project along the future x-axis, anchoring seamlessly into the live range box at the opening bell.

**True Day Open (TDO) Sweep Protocol**  
Plots the 00:00 NY True Day Open. Ignores pre-market overnight chop, only activating its sweep logic at 8:30 AM NY. The line automatically terminates the exact tick price sweeps the level.

**Single-Trigger Liquidity Sweeps (`x`)**  
Monitors HTF levels (`PDH`, `PDL`, `PWH`, `PWL`) and active session extremes. Drops a subtle `x` marker on the raiding wick the instant price breaches liquidity by a single tick, immediately deactivating the level to eliminate repetitive false signals.

**True Algorithmic Gap Tracking (NDOG & NWOG)**  
Calculates true price imbalances between session closes and opens. Projects opening gaps forward continuously until incoming candle price action fully balances the void.

**Rolling 24-Hour 4H Opens**  
Automates the institutional 6-tier 4H cycle (18:00, 22:00, 02:00, 06:00, 10:00, 14:00 NY), automatically cycling out yesterday's levels as new blocks print.

**On-Chart Execution Desk & Macro HUD**  
* **Risk/Position Desk:** Reads native contract point values (`syminfo.pointvalue`) to output exact sizing and micro allocations based on user-defined dollar risk and point stop loss.
* **Macro Window Indicator:** Auto-tracks the hourly institutional 20-minute macro injections (xx:45–xx:15).
* **Minimalist HUD Watermark:** Configurable typography panel with multi-line spacing control.

---

### ◾ VISUAL DESIGN

Engineered specifically for dark execution terminals with zero visual clutter:
* **Color-Matched Extensions:** Range extension lines automatically inherit the exact tone of their parent killzone with custom line-style controls.
* **Flush Coordinates:** Session start, midpoint, and extension markers snap directly to execution minutes without overhanging ticks or visual drift.
* **Modular 11-Tier Settings:** Granular control over Killzone font sizes, line transparencies, gap opacities, and HUD placement.

---

### ◾ SPECS

* **Assets:** NQ, MNQ, ES, MES, GC, CL
* **Optimal Timeframes:** 1m, 3m, 5m, 15m
* **Timezone:** Internal engine locked strictly to `America/New_York` algorithmic time
