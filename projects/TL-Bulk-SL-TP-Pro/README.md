<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Bulk SL TP Pro

**Drag ONE line and every open position gets the same stop loss or take profit — without closing anything.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_BulkSLTPPro_screenshot.png" alt="TL Bulk SL TP Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Bulk SL TP Pro.ex5`](MT5/TL%20Bulk%20SL%20TP%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

position gets the same SL or TP - without closing anything.

## Install

- MT5\Experts\TL Bulk SL TP Pro.ex5 -> File > Open Data Folder > MQL5\Experts Refresh the Navigator, drag the EA onto a chart of the symbol you trade. Enable "Algo Trading" (the EA modifies SL / TP). "Allow DLL imports" is only needed for the link buttons.

## Drag Lines (chart symbol)

BUY SL / BUY TP / SELL SL / SELL TP lines appear as soon as there are buy or sell positions. Drag a line and release it -> all matching positions get that exact price as SL or TP. AUTO APPLY OFF: move the lines first, then press APPLY LINES (label shows NOT APPLIED until then). Each label shows: price · positions on the line · pips from the average entry · money if price reaches the line (swap included, commission not). Levels on the wrong side of the price / inside the broker's stops level are rejected and counted - nothing is half-changed silently.

## Quick Actions (chart symbol or All symbols)

SET SL / SET TP x pips from each entry (- / + buttons), BREAKEVEN (+ offset), REMOVE SL, REMOVE TP, UNDO (restores the SL / TP from before the last bulk change), CLOSE ALL (with confirmation).

## Filter

ONLY <symbol> / ALL SYMBOLS, BUYS + SELLS / BUYS ONLY / SELLS ONLY, input: all positions / manual only / one magic number.

The EA never opens a trade. Dashboard: X closes it to a pill, drag the header to move it, settings are kept per chart.

Test on demo first. Trading involves high risk. trader.lifestyle - Forex Factory thread: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
