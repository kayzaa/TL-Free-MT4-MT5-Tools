<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Candle Based Pro

**Casper C.'s classic "Candle Based EA" (FF thread 332199) rewritten from scratch for MT4 and MT5.**

![version](https://img.shields.io/badge/version-v4.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Candle_Based_Pro_XAUUSD_M5_cbp_shot9.png" alt="TL Candle Based Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Candle Based Pro.ex4`](MT4/TL%20Candle%20Based%20Pro.ex4) |
| **MT5** | [`TL Candle Based Pro.ex5`](MT5/TL%20Candle%20Based%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

The "Candle Based EA" by Casper C. (FF thread 332199, 2011) rebuilt from scratch so that EVERY input works - on forex (5 digits), JPY pairs (3 digits), gold, silver and indices.

## System (unchanged)

- **BUY** — : price breaks above the HIGH of the previous candle SELL : price breaks below the LOW of the previous candle EXIT : a) stop loss / take profit / break-even / trailing stop b) break in the opposite direction (closes the trade and opens the opposite one)

## Install

- **MT4: copy "TL Candle Based Pro.ex4" to** — File > Open Data Folder > MQL4 > Experts MT5: copy "TL Candle Based Pro.ex5" to  File > Open Data Folder > MQL5 > Experts Restart the terminal (or right click "Refresh" in the Navigator), drag the EA on a chart, tick "Allow live trading" (MT4) / "Allow Algo Trading" (MT5). Tick "Allow DLL imports" only if you want the YouTube / RoboForex / WhatsApp / Myfxbook buttons to open the browser (the EA trades fine without it). The .mq4 / .mq5 source files are included - one source file compiles in both editors.

## All Distances Are In Points Of The Symbol

- **gold (2 digits): 100 points = 1.00 $ = "10 pips"** — |   EURUSD (5 digits): 100 points = 10 pips The original divided by 100000 (only correct on 5-digit forex) - that is gone.

## Inputs

- SIGNAL Signal timeframe ........ candle that must be broken (current = chart timeframe) Buffer .................. break must exceed high / low by X points (0 = any break) Break price ............. Original (BUY on Ask > high, SELL on Bid < low) or Bid for both Trade direction ......... both / long only / short only Close on opposite break . exit b) of the system Entry limit counted ..... per direction (a reversal in the same candle is allowed) or per candle in total (original v1 / v2 behaviour) Max. new trades / candle  1 = original (0 = unlimited) Max. open positions ..... 1 = one trade at a time, > 1 = stacking like version 3
- STOP LOSS / TAKE PROFIT (points, 0 = none)
- BREAK-EVEN: when the profit reaches the trigger, the stop moves to entry + lock. Once.
- TRAILING STOP: starts only when the trade is in profit by the start value (0 = start at the distance -> the stop is at least break-even when it starts), then follows the price at the distance; min. step per modification. Never moves back.
- MONEY MANAGEMENT: fixed lots / dynamic (lots per X of balance) / risk % of balance. Martingale (optional, HIGH RISK): lots x multiplier after every loss in a row, after "max. steps" the cycle starts again at the base lot. Max. lots cap.
- FILTERS: max. spread, trading window (server time), max. trades per day, stop new trades after a daily loss of X % of the balance.
- DISPLAY: dashboard (auto two columns on small charts, click the header to collapse), break levels of the current candle on the chart, tooltips on every element (can be switched off), alerts popup / sound / push.
- OTHER: auto trading on/off, magic number (one per chart), comment, slippage.

## What Was Wrong In The Original Versions (v1, v2, v3)

- Trailing distance = TrailingSL / 100000 -> only right on 5-digit forex. On gold 300 became 0.003 $ and the stop was dragged directly behind the price.
- The trailing stop started at trade open (Bid - SL > TS is true on the first tick), so it replaced the initial stop immediately - on the losing side of the entry.
- "BE" was not a break-even: it only stopped the trailing once the stop was above entry + 0.001 (a fixed price). No trigger, no move to entry.
- v3 buffer: "buffer_value*Point < Ask-Bid*Point" is calculated as Ask - (Bid*Point), which is always bigger -> the buffer switched itself off on the first tick.
- v3 pending orders: the check compared the LOT size with 1 instead of the order count and then deleted every order of the account; pending orders never expired.
- No magic number / symbol filter: it closed and modified manual trades and other EAs on all symbols, and "OrdersTotal() == 0" blocked it whenever anything else was open.
- The new-candle flag was used up before the order result -> a rejected order was never retried in that candle; v2 printed an alert on every tick.
- DynamicLot without lot step / min / max rounding (error 131), 0.01 lot per 10 $ in v1/v2.
- v3 martingale detected losses by comparing the balance between ticks -> wrong with any other trade, swap or deposit; the max. lot was equity / 1000.
- Order loops counted forward while closing (skips orders), division by zero at balance 0. Plus new safety: stop level / freeze level checks, spread wider than the stop -> skip, free margin check, no retry flood on "not enough money", ECN (stops after the order), no modifications while the market is closed, state rebuilt after a restart.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
