# ◼️ KILLZONES & EXECUTION SUITE [v6]

> Institutional time-and-price delivery engine with strict memory management for TradingView.

Built specifically for high-precision execution across index and commodity futures (NQ, ES, CL, GC). Strips out chart noise, prevents drawing-limit lag, and delivers pure algorithmic order-flow references directly to your workspace.

<img width="1253" height="751" alt="preview" src="https://github.com/user-attachments/assets/46587047-2241-4276-a3a2-0a676c22f6f3" />

---

### ◾ CORE ARCHITECTURE

**Strict 2-Session Memory Protocol**  
Drawings are strictly managed to preserve chart performance. The engine holds a maximum of two historical sessions per killzone, instantly purging obsolete boxes, lines, and bound LTF sweeps from memory the moment a new session opens.

**Dynamic Wick-to-Wick REQH / REQL Engine**  
Timeframe-aware relative equal highs and lows detection that auto-deletes the exact moment liquidity is raided.
* **LTF (<15m):** High-precision buffers (0.25 pts). Levels are strictly bound to active Killzone visibility blocks to prevent out-of-session clutter. 
* **HTF (15m+):** Expanding algorithmic buffers (1.5 pts up to 3.0 pts for Daily+) with independent persistent lifespans (1-week to 1-month). 

**Advanced Liquidity Sweeps (`x`) & FIFO Limits**  
Monitors HTF levels (`PDH`, `PDL`, `PWH`, `PWL`), active session extremes, and 4H opens. Drops an `x` marker on the raiding wick the instant price breaches liquidity by a single tick. Features a customizable **First-In-First-Out (FIFO) queue** (e.g., max 2 markers per session) to aggressively eliminate chart clutter during heavy chop. 

**Rolling 24-Hour 4H Opens**  
Automates the institutional 6-tier 4H cycle (18:00, 22:00, 02:00, 06:00, 10:00, 14:00 NY). Yesterday's levels—along with their respective sweep markers and erasable structural candle highlights—are automatically purged as new blocks print.

**True Algorithmic Gap Tracking (NDOG & NWOG)**  
Calculates true price imbalances between session closes and opens. Projects opening gaps forward continuously until incoming candle price action fully balances the void.

**True Day Open (TDO) Sweep Protocol**  
Plots the 00:00 NY True Day Open. Ignores pre-market overnight chop, only activating its sweep logic at 8:30 AM NY. The line automatically terminates the exact tick price sweeps the level.

**15-Minute Forward Projections**  
A dynamic visual engine. Exactly 15 minutes before an impending session open, a forward line and label project along the future x-axis, anchoring into the live range box at the opening bell.

---

### ◾ ON-CHART UI & HUD

**Risk & Position Desk**  
Reads native contract point values (`syminfo.pointvalue`) to output exact sizing and micro allocations based on user-defined dollar risk and point stop loss. 

**Dynamic Sweep Alert HUD**  
Real-time, on-screen text alerts (e.g., "PDH SWEPT", "ASIA HIGH SWEPT") that inject natively into the Position Desk, Watermark, or a customizable Standalone panel. Features smart vertical stacking (auto-inverting based on screen anchors) and automated time-decay pruning (alerts vanish after a custom minute duration).

**Macro Window Indicator**  
Auto-tracks the hourly institutional 30-minute macro injections (xx:45–xx:15), dynamically displaying its status on the HUD.

---

### ◾ SPECS

* **Assets:** NQ, MNQ, ES, MES, GC, CL
* **Optimal Timeframes:** 1m, 3m, 5m, 15m
* **Timezone:** Internal engine locked strictly to `America/New_York` algorithmic time
