# Killzones & Session Range Indicator (Pine Script v5)

An all-in-one, highly customizable **ICT / Smart Money Concepts (SMC)** session, killzone, and opening price level indicator built for TradingView.

Designed for intraday execution and clean chart management, this indicator automatically handles multi-session ranges, high-timeframe liquidity sweeps, 24-hour rolling 4H opening prices, and opening gaps with automatic fill-detection and historic object garbage collection.

---

## ✨ Features

### 🎯 Killzones & Session Ranges

* **Customizable Session Windows:** Tracks Asia, London (LOKZ), New York AM (Extended 08:30–11:00 AM), NY Lunch, and NY PM sessions in NY timezone (`America/New_York`).
* **High/Low Range Extensions:** Draws range boxes with optional horizontal extension lines off session high and low prices (supports Wick or Body calculations).
* **Smart Garbage Collection:** Retains **2 full days** of historical session/killzone drawings, temporarily holding 3 days during day transitions until the NY AM session closes to keep your charts light and lag-free.

### 📐 HTF Liquidity & Opening Levels

* **Previous Day High/Low (PDH / PDL):** Extends previous daily highs/lows with right-aligned labels until price sweeps/fills them.
* **Previous Week High/Low (PWH / PWL):** Extends previous weekly highs/lows with right-aligned labels until filled.
* **True Day Open (Midnight):** Plots Midnight NY True Day Open horizontal lines (capped to max 2 active days).
* **9:30 AM Equity Open Divider:** Vertical line marking the 09:30 AM NY equity open, auto-clearing at every new weekly open.
* **Rolling 24-Hour 4-Hour Opens:** Plots 4-Hour candle opening prices (18:00, 22:00, 02:00, 06:00, 10:00, 14:00) on a **strict rolling 24-hour cycle**—deleting yesterday's corresponding 4H line as each new one prints.

### 📊 Opening Gaps (NDOG & NWOG)

* **New Day Opening Gap (NDOG) & New Week Opening Gap (NWOG):** Automatically draws gap boxes with centered text labels.
* **Exclusive NWOG Priority:** NWOG automatically overrides NDOG on weekly opens to prevent overlapping boxes.
* **Accurate Fill Engine:** Checks exact High/Low price intersections within the gap boundaries and deactivates extensions instantly upon full mitigation.
* **Multi-Timeframe Filtering:** Restricts gap box rendering strictly to timeframes between **1 Hour (1H) and 1 Week (1W)**.

### ⏱️ Automated Timeframe Deactivation

* Features an intraday filter threshold ($\le$ 1 Hour / 60-min). Indicator elements automatically turn off cleanly on higher timeframe charts (4H, Daily) to prevent chart clutter.

---

## 🛠️ Installation & Setup

1. Open **TradingView** and navigate to any chart.
2. Click on the **Pine Editor** tab at the bottom of the screen.
3. Click **New** $\rightarrow$ **Blank indicator script**.
4. Paste the source code into the editor.
5. Click **Save** and then click **Add to chart**.

---

## ⚙️ Configuration & Settings

| Input Group | Setting | Description | Default |
| --- | --- | --- | --- |
| **Killzone Toggles & Colors** | Master Toggle & Displays | Toggle individual sessions, box colors, and text styles | Enabled |
| **Session Times** | NY AM Session | Extended NY AM session time | `0830-1100` |
| **True Day Open** | Show Line / Max Days | Midnight open line style, color, and max limit | Enabled (Max 2) |
| **HTF High/Low Levels** | PDH/PDL & PWH/PWL | Toggles, line widths, opacity, and right labels | Enabled |
| **Opening Gaps** | NDOG / NWOG | Box colors, transparency, and text size settings | 1H–1W Timeframe |
| **4-Hour Open Lines** | Rolling Cycle | Toggle specific 4H opening price lines | 24-Hour Cycle |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/) if you want to submit a pull request or report a bug.

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
