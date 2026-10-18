<div align="center">

# ⚡ TL ATM Machine Pro

**nkpoette's 3-CCI "ATM Machine" stop-and-reverse system from Forex Factory as one EA — all three CCI windows embedded in the panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL ATM Machine Pro.ex5`](MT5/TL%20ATM%20Machine%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **The classic 3-CCI "ATM Machine"** from Forex Factory, rebuilt as one MT5 Expert Advisor.
- **Stop and reverse** — an opposite signal closes the trade and flips into the new direction, just like the original spec.
- **Two signal modes**: ALIGN (all three CCI on the same side of zero) or CROSS (all three cross zero together).
- **No extra files** — the template's three CCI windows (140 / 100 / 42) are built right into the panel.
- **Closed-candle signals by default** — no repaint; a live-candle option mirrors the original alert.
- **Optional protection** (SL, TP, break-even, trailing and more) — all off by default, so the original stays the original.

## 🧠 Strategy rules

The original rules, as posted in the thread:

> - 3 CCI on the median price (HL/2): **Trend 140**, **Entry 100**, **Power 42** (template "nkpoette's hard work")
> - "Buy when 3 CCI ... are above Zero, sell when 3 CCI ... are below zero"
> - "No stop loss, no take profit, no trailing stop"
> - "the EA must use a stop and reverse system"
> - "No money management, to be set manually" + a magic number for running many pairs
> - "works best on all pairs and 15 or 30 min time frames" (GBPJPY, EURJPY, GBPUSD M15/M30)

How the EA turns them into trades:

| Setting | Behaviour |
|---|---|
| **Signal mode ALIGN** (default, post #42) | All 3 CCI flip to the same side of zero → **BUY** (above) / **SELL** (below). |
| **Signal mode CROSS** | The "ATM Machine Modified" alert — all 3 CCI cross zero together, on the same candle or within X candles ("CROSS mode window"). |
| **Exit: stop and reverse** | The opposite signal closes the position and opens the new direction. |
| **Exit: CCI disagree** (alternative) | Close as soon as the 3 CCI disagree, then stay flat until the next signal. |
| **Signal candle** | Closed candle by default (no repaint). "Live candle" behaves like the original alert. |

**Optional protection** — not part of the original and all **off by default**: stop loss, take profit, break-even, trailing stop, max spread, trading hours, Friday close, direction filter and lot per balance.

## 🖥️ Dashboard & chart

- **Position** block with the current trade.
- **The 3 CCI** (140 sea green / 100 red / 42 yellow) with gauges and TH-MTF-bar strips of the last 40 candles.
- **Results** and the **signal history** of the chart.
- **TRADING ON / PAUSE** and **CLOSE ALL** buttons, plus link buttons.
- **Signal arrows** on the chart and **popup / sound / push alerts**.

## 🛠️ Installation

1. In MT5 open `File → Open Data Folder → MQL5 → Experts` and copy `TL ATM Machine Pro.ex5` there.
2. Restart MT5, or right-click **Expert Advisors → Refresh** in the Navigator.
3. Drag the EA onto a chart (e.g. GBPJPY M15) and enable **Allow Algo Trading**.
4. Enable **Allow DLL imports** only if you want the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) to open your browser.
5. Use one chart per pair. Running the same pair twice? Give each copy its own magic number.

## 🙏 Credits

- System by **nkpoette**; EA requirements from posts #42, #43, #49, #53 and #55 by **"pips stunner"** (May/June 2009) in the Forex Factory thread ["I will code your EAs and Indicators for no charge"](https://www.forexfactory.com/thread/post/2773438#post2773438).

## ⚠️ Notes

- The original system has **no stop loss** — a position is only closed by the opposite signal. Always-in-the-market exposure can run against you for a long time; consider the optional protection and test on a demo account first.
- No money management is built into the original — set your lot size manually.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
