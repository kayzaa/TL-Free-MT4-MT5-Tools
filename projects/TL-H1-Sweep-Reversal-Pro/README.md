<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL H1 Sweep Reversal Pro

**H1 liquidity sweep followed by an M5 reversal entry — Silkysilv's method automated.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_H1SweepReversalPro_chart.png" alt="TL H1 Sweep Reversal Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL H1 Sweep Reversal Pro.ex4`](MT4/TL%20H1%20Sweep%20Reversal%20Pro.ex4) |
| **MT5** | [`TL H1 Sweep Reversal Pro.ex5`](MT5/TL%20H1%20Sweep%20Reversal%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Strategy (as described by Silkysilv on Forex Factory, posts #111 / #112):

Every new H1 candle RefHigh / RefLow = high / low of the last completed H1 candle. Everything resets.

SELL
- The FIRST M5 candle of the hour that trades above RefHigh is the sweep candle (a later, higher candle does NOT replace it).
  - A later M5 candle of the same hour closes below the LOW of the sweep candle.
  - Sell at market when that candle closes. Stop loss  = sweep candle high + spread + buffer (pips) Take profit = RefLow

BUY - the exact mirror M5 candle below RefLow = sweep candle, a later M5 close above its HIGH -> buy, SL = sweep low - spread - buffer, TP = RefHigh.

No confirmation before the hour ends -> the setup is cancelled. Open trades keep running until SL or TP (they are never moved or closed by the EA). One trade at a time by default. Risk 5 % of the balance per trade by default. If the price is already at / beyond the target when the signal comes, the trade is skipped.

The EA always reads M5 candles, so it works on any chart timeframe and any symbol. For backtests use the M5 chart (MT4 tester: M5 is required).

Installation
- **MT5: copy MT5\TL H1 Sweep Reversal Pro.ex5 to** — File > Open Data Folder > MQL5\Experts MT4: copy MT4\TL H1 Sweep Reversal Pro.ex4 to  File > Open Data Folder > MQL4\Experts Restart the terminal or right-click "Expert Advisors" in the Navigator > Refresh. Enable "Allow DLL imports" if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to open links (the EA trades without it).

Main inputs Trade direction ............ long + short / long only / short only Confirmation inside range .. extra filter (default off): the confirmation close must also be back inside the H1 range SL buffer (pips) ........... default 1.0 pip (pip = 10 points on 5- and 3-digit symbols) Add spread to SL ........... default on Max. open trades ........... 1 = one at a time, more = pyramiding (several trades at once) Lot mode ................... Risk % of balance (default 5 %) or fixed lots Session filter ............. default 10:00-24:00 SERVER time = London open (08:00 London) to New York close (17:00 New York) on GMT+2/+3 brokers, which most MT4/MT5 brokers use. Adjust if your broker uses another time zone. Max. spread (pips) ......... 0 = off Magic number, comment, slippage, alerts (popup / sound / push), dashboard, tooltips on/off

On the chart
- **Grey lines** — = RefHigh / RefLow of every hour Dots         = sweep candles, dotted line = trigger level (low / high of the sweep candle) Arrows       = signals (also the ones that were skipped by a filter) Boxes        = risk / reward of every trade the EA would take (green = target, red = stop, result in R) Dashboard    = current levels, state of both setups, risk, position, results

Risk warning: 5 % risk per trade is very aggressive. Test on a demo account first. No profit promise - trading involves high risk.

trader.lifestyle - free tools thread on Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
