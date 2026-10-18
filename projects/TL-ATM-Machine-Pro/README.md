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

## Overview

nkpoette's 3-CCI "ATM Machine" system from Forex Factory as ONE MT5 EA. Source: thread "I will code your EAs and Indicators for no charge", posts by "pips stunner" (#42, #43, #49, #53, #55 - May/June 2009): <https://www.forexfactory.com/thread/post/2773438#post2773438>

## The Original Rules (quoted from the thread)

- 3 CCI on the median price (HL/2): Trend 140, Entry 100, Power 42 (template "nkpoette's hard work")
- "Buy when 3 CCI ... are above Zero, sell when 3 CCI ... are below zero"
- "No stop loss, no take profit, no trailing stop"
- "the EA must use a stop and reverse system"
- "No money management, to be set manually" + magic number for many pairs
- "works best on all pairs and 15 or 30 min time frames" (GBPJPY, EURJPY, GBPUSD M15/M30)

## What The EA Does

- Signal mode ALIGN (default, post #42): all 3 CCI flip to the same side of zero -> BUY / SELL.
- Signal mode CROSS: the "ATM Machine Modified" alert - all 3 CCI cross zero together (on the same candle, or within X candles via "CROSS mode window").
- Stop and reverse: an opposite signal closes the position and opens the new direction. Alternative exit: "close when the 3 CCI disagree" (flat until the next signal).
- Closed-candle signals by default (no repaint). "Live candle" = like the original alert.
- The template's CCI window (140 sea green / 100 red / 42 yellow) is built in - no extra files.
- Panel: position, the 3 CCI with gauges + TH-MTF-bar strips (last 40 candles), results, signal history of the chart, TRADING ON/PAUSE, CLOSE ALL, link buttons.
- Signal arrows on the chart, popup / sound / push alerts.
- Optional protection (NOT in the original, all off by default): SL, TP, break-even, trailing, max spread, trading hours, Friday close, direction filter, lot per balance.

## Installation

- Copy "TL ATM Machine Pro.ex5" to  MQL5\Experts\  (File > Open Data Folder).
- Restart MT5 or right-click "Expert Advisors" > Refresh in the Navigator.
- Drag the EA on a chart (e.g. GBPJPY M15). Enable "Allow Algo Trading". Enable "Allow DLL imports" only if you want the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook) to open your browser.
- One chart per pair. Use a different magic number if you run the same pair twice.

## Risk Warning

The original has NO stop loss - the position is only closed by the opposite signal. Test on a demo account first. Past results do not guarantee future results. Trading involves high risk. No profit promise.

trader.lifestyle  ·  <https://www.youtube.com/@traderlifestyle>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
