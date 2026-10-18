<div align="center">

# ⚡ TL Martingale Calculator Pro

**Plan a martingale / recovery sequence before you trade it — lots, levels and exposure.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Martingale Calculator Pro.ex4`](MT4/TL%20Martingale%20Calculator%20Pro.ex4) |
| **MT5** | [`TL Martingale Calculator Pro.ex5`](MT5/TL%20Martingale%20Calculator%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

## Install

- **MT5: copy "TL Martingale Calculator Pro.ex5" to** — File > Open Data Folder > MQL5 > Indicators MT4: copy "TL Martingale Calculator Pro.ex4" to  File > Open Data Folder > MQL4 > Indicators Refresh the Navigator and drag it onto a chart ("Allow DLL imports" only for the link buttons). It is an indicator, so it runs on the same chart as TL Trade Panel Pro or any EA.

## What It Shows

For every level of a martingale / grid: price, lot, total lots, average (break-even) price, pips back to break-even, floating P/L when the price reaches the level, total margin, margin level %, and the profit if the basket take profit is hit after that level. margin level at the last level, TP profit, estimated STOP-OUT price with all levels open, loss at an optional hard stop, risk : reward, and a verdict: how many levels your account survives. Rows turn yellow (margin call), orange (not enough free margin to open) or red (stop-out), using your broker's real stop-out / margin-call levels.

## Modes

VIRTUAL - plan a grid from the live price, a typed price or the dragged START line.
- **LIVE** — - your open trades of the symbol become the first levels (silver lines), the next levels are projected from the last entry and the last lot.

## Settings (live on the panel - type or use - / +)

BUY or SELL grid, start lot, lot multiplier (2 = classic martingale, 1 = plain grid), lot added per level (additive martingale), step in pips, step multiplier (wider gaps), number of levels (max. 40), basket TP in pips from the average, hard stop beyond the last level. Inputs: commission per lot, magic filter for LIVE mode, colours.

## Chart

Level lines with lot labels, basket TP line, stop-out line, hard-stop line.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
