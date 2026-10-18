<div align="center">

# ⚡ TL Trendline Bounce Pro

**Automatic trendlines and bounce entries, built after the popular YouTube trendline strategy.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL%20Trendline%20Bounce%20Pro%20-%20XAUUSD%20M15.png" alt="TL Trendline Bounce Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Trendline Bounce Pro.ex4`](MT4/TL%20Trendline%20Bounce%20Pro.ex4) |
| **MT5** | [`TL Trendline Bounce Pro.ex5`](MT5/TL%20Trendline%20Bounce%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Tori Trades' trendline bounce setup, automated** — the rules from the video, drawn and traded by one tool.
- **Top-down trendlines** — from the monthly chart down to the 4h structure, refined on lower timeframes.
- **Trend-only bounce entries** — BUY after a higher low, SELL after a lower high, when a candle closes on the right side of the line.
- **Line-based risk** — the stop sits just beyond the line; the line must be violated for a loss.
- **Ride the trend** — no fixed target; swing-based trailing plus an optional sideways-breakout stop jump.
- **Two modes** — fully automatic EA, or an indicator mode with lines, signals, alerts and virtual trades only.

## 🔀 Mode (first input)

| Mode | Behaviour |
|---|---|
| **EA mode** | Trades automatically. |
| **Indicator mode** | Lines, signals, alerts and virtual trades only — never sends orders. |

## 🧠 Strategy rules (from the video)

**Drawing the lines**

1. Top-down: monthly → weekly → daily → 4h → 1h → your timeframe.
2. First down line from the highest point, first up line from the lowest point.
3. Price may never intersect a line; capture as many touch points as possible.
4. The last touch (point B) of a line is point A of the next, steeper line.
5. New lines down to the 4h structure (point B = 4h swing); lower timeframes only refine.

**Trading the bounce**

| Item | Rule |
|---|---|
| **Entry** | Price comes back "at or near" the line and the candle closes on the right side. Only with the trend: BUY after a higher low, SELL after a lower high. |
| **Max. entries** | 2 per line (entry + the bonus re-entry from the video). |
| **Stop** | Just beyond the line — the line must be violated for a loss. |
| **Trailing** | After every new swing the stop moves — but never inside the line. |
| **Sideways phase** | Extra rule, can be switched off: when price moves sideways in profit and then breaks out in the trade direction, the stop jumps below the phase (SELL: above it). |
| **Exit** | A candle closes on the other side of the line. No target — ride the trend. |

All decisions are made on closed bars — no repaint.

## 🛠️ Installation

1. **MT5:** copy `MT5/TL Trendline Bounce Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
   **MT4:** copy `MT4/TL Trendline Bounce Pro.ex4` to `File → Open Data Folder → MQL4 → Experts`.
2. Restart the terminal or refresh the Navigator.
3. Drag it onto a chart (the video uses 15 min).
4. Enable **"Allow DLL imports"** only for the panel buttons (links only).

## 🙏 Credits

Strategy by **Tori Trades** (trendline bounce setup).

## ⚠️ Notes

- The MT5 Strategy Tester only provides about one year of history before the start date, so the monthly / weekly lines there are shorter than on a live chart.
- Trading involves high risk. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
