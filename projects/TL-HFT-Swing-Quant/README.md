<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL HFT Swing Quant

**The fxDreema box-breakout video as an EA: 12-bar / 30-pip box, signal line cross, fixed SL / TP — with quant panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_HFT_Swing_Quant_hsq_view_1600x1000.png" alt="TL HFT Swing Quant" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL HFT Swing Quant.ex5`](MT5/TL%20HFT%20Swing%20Quant.ex5) |

> Compiled build only — source code is not published.

## Overview

Enable "Allow DLL imports" only if you want the RoboForex / WhatsApp / YouTube / Forex Factory buttons to open links.

## Rules (1:1 rebuild of the fxDreema project "HFT Swing Trade X", Boxxocode ep546)

- No open position + the last 12 closed bars fit into 30 pips (highest high - lowest low) + the last close is inside that box -> Line High / Line Low are set, once per bar Line Signal = (High + Low) / 2. Three horizontal lines are drawn.
- BUY : the last close crosses above Line Signal (or above Line High when Mode_ALL_signal = true). SELL: the last close crosses below Line Signal (or below Line Low).  Max one entry per bar.
- SL 15 pips, TP 30 pips (measured from the closing price, like fxDreema).
- Lot: Mode_Lots_X = martingale (look at the last trade: loss -> lot x 1.6, win -> back to Lot_start), Mode_Max_Lots = lot limit 0.5. Mode_Lots_X = false -> fixed Lot_start.
- After every entry the lines are deleted and the variables reset to 0.
- 1 pip = 10 points on 5/3 digit symbols and on gold (0.10). Override with "Points per pip".

## Panel (quant style, collapsible with Min): execution, swing box state + range gauge, signal matrix,

box scope, martingale ladder, performance of this EA, the fxDreema block blueprint checked live. English tooltips on everything (switch off in the inputs).

WARNING: martingale can wipe out an account. In our own test on XAUUSD M1 (real ticks, 2026) Not financial advice - backtests are no promise.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
