<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Weekly Pivot Pro

**Davit's weekly Fibonacci pivots as an EA — 38 / 61 / 78 ladder, PP target and basket stop.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_WeeklyPivotPro_post.png" alt="TL Weekly Pivot Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Weekly Pivot Pro.ex4`](MT4/TL%20Weekly%20Pivot%20Pro.ex4) |
| **MT5** | [`TL Weekly Pivot Pro.ex5`](MT5/TL%20Weekly%20Pivot%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Strategy: Davit's "Pivot Trading" thread  <https://www.forexfactory.com/thread/588764-pivot-trading>

## Files

- **MT5/TL Weekly Pivot Pro.ex5** — -> MQL5\Experts MT4/TL Weekly Pivot Pro.ex4   -> MQL4\Experts Enable "Allow algo trading" and "Allow DLL imports" (DLL is only used by the link buttons). Attach the EA to one chart per pair you want to trade (M15 or H1 chart, any timeframe works).

## The Levels (same as Davit's pivot indicator, broker weekly candle)

- **PP** — = (High + Low + Close) / 3 of last week R/S  = PP +/- 0.382 / 0.618 / 0.786 / 1.0 / 1.382 / 1.618 / 2.0 x last week's range If your pivots differ from Davit's chart: "Week candle" = Shifted week + hour offset.

## Entries (ladder / position building)

- **SELL ladder at R38, R61, R78** — ·   BUY ladder at S38, S61, S78   (each stage on / off, own lot multiplier) Confirmation (default = mizi123's rule): a closed H1 candle ends in the level zone -> that stage is traded. Other modes: Touch (enter at the level) · Rejection candle · TDI cross (Davit, RSI 13 / 2 / 7) Zone tolerance (default 10 pips): pivots are zones, the level counts N pips early. Pivot levels stay fixed for the whole week (broker weekly candle). One ladder per side and week (option).

## Exits

Take profit = weekly pivot (or one level back towards the pivot)
- **Hard stop per order beyond R138 / S138 (+5 pips)** — -  or R100 / R161 / off Trend exit: an H1 candle closes beyond R100 / S100 -> that side is closed (Davit: "smash 100 = trend") Optional half-way break-even / partial close, Friday close 21:00 server

## Basket Stop  (mizi123's request)

Close everything when the open loss reaches X money or X % of the balance (swap + commission included) Scope: this symbol · all symbols of this magic number · whole account (closes this EA's orders) Default: closes the orders and blocks new entries until next week.

## Range / Trend Filter + Scanner  (mizi123's request)

3 votes per pair and week from the completed weekly candles:
- weekly ADX (Wilder 14) >= 25
  - >= 2 of the last 4 weeks traded beyond their own R100 / S100
  - efficiency of the last 4 weekly closes >= 0.6 (net move / path) 0 votes = RANGING, 1 = MIXED, 2-3 = TRENDING.  Filter: skip TRENDING (default), only RANGING, with the trend, off. Live: price beyond R100 / S100 this week -> no new counter trades. The scanner shows every pair of Davit's list: regime, ADX, zone touched this week ("touched R61"), distance to PP. Click a pair to open it.

## News Filter

No new entries 30 min before / after high impact news (Forex Factory feed or MT5 calendar). MT4 / FF feed: add <https://nfs.faireconomy.media> under Tools > Options > Expert Advisors > Allow WebRequest.

## Risk Warning

This is a counter-trend system that adds to losing positions. Test it on demo first. Backtests are no guarantee for the future.

More free tools + coding help: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
