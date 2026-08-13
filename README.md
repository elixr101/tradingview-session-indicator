# ◼️ KILLZONES [v5]

> Precision session tracking and institutional pricing models for TradingView.

Engineered for clean, quantitative execution on high-volatility assets like Nasdaq futures. This indicator strips away chart noise through strict memory management, displaying only what is mathematically necessary for immediate contract risk management and order flow tracking.

*(Reference `image_cda618.jpg` for the intended dark-mode visual configuration).*

---

### ◾ CORE ARCHITECTURE

**Strict Memory Engine**
Chart clutter is a liability. The custom memory engine ruthlessly purges obsolete drawings, holding a strict maximum of two historical data points per session.

**15-Minute Forward Projection**
A predictive visual engine. Exactly 15 minutes before an impending killzone, a localized preview (opening line and label) projects into the future on the x-axis. The moment the session executes, the preview dissolves into the live session box, and the oldest historical session is terminated to maintain the 2-session max.

**True Day Open (TDO) Sweep Protocol**
Plots the midnight True Day Open. To prevent false signals during low-volume hours, the algorithm ignores all price action until the 8:30 AM NY equities open. Post-8:30, the line instantly terminates the exact millisecond price sweeps the open.

**Gap Mechanics (NDOG & NWOG)**
Tracks New Day and New Week Opening Gaps. Gap boxes track the exact target price of the previous close and project infinitely rightward until a future candle perfectly intersects and fills the void.

**Rolling 4H Arrays**
Maintains a rolling 24-hour cycle of 4-hour opening price lines (18:00, 22:00, 02:00, etc.). As a new 4H candle opens, yesterday's equivalent line is seamlessly deleted to keep the workspace pristine.

---

### ◾ AESTHETICS & VIBE

Designed natively for the dark chart. The visual hierarchy is heavily weighted toward raw price action, using muted colors and sharp, flushed lines.

* **Flush Terminations:** Opening lines, boxes, and closing lines snap perfectly to the exact minute of the session range. No overhanging ticks, no visual lag. 1-candle offsets have been mathematically corrected.
* **Minimalist Boundaries:** Session ranges can be configured to track wicks or bodies. Labels are small, highly transparent, and stay out of the way.
* **Muted Institutional Palette:** Deep blues, washed reds, and faded greens. HTF levels (`PDH`, `PDL`, `PWH`, `PWL`) are sharply defined but remain visually subordinate to the candlesticks.
* **Rolling 9:30 AM Lines:** Vertical dashed execution lines that track the opening bell, automatically rolling out the oldest variations based on your exact custom input.

---

### ◾ USAGE

Apply directly to a dark-themed TradingView workspace (15m timeframe recommended). All parameters, including maximum pip-filters for ranges, session timings, and gap opacities, are fully modular in the script settings.
