<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Small Matter Pro

**hayseed's top-down ladder system: D1 TSR bias, H4 ALMA trigger and a ladder basket.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Small_Matter_Pro_panel.png" alt="TL Small Matter Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Small Matter Pro.ex5`](MT5/TL%20Small%20Matter%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Built after the Forex Factory trading journal "it's a small matter" by hayseed (<https://www.forexfactory.com/thread/462458-its-a-small-matter),> his posts #27 #140 #237 #284 #338 #362 #366 #369 #432 and his own MT4 tools (TSR.mq4, alma.mq4, ZigZag w order alerts.mq4, send sell and sell limits.mq4).

## The Rules

1  BIAS     weekly TSR(89) (hull MA) lime -> buys only, red -> sells only 2  TRIGGER  ALMA(9, 6, 0.85) colour change on H4 in the bias direction 3  ZIGZAG   the current H4 zigzag(12,5,3) leg points the same way 4  ENTRY    1 market order + a ladder of 5 limit orders beyond the price (his script "send sell and sell limits") 5  EXITS    target = 0.30 x weekly ATR per order from 6 open orders all targets are cut to 1/3 from the average price winners are closed when the H4 zigzag leg reaches 2x its average length basket trailing stop ("trailing account profit closeall") basket kept when the bias turns (hayseed: "negative till the market resumes") NO stop loss per order - a safety net closes the basket at -25 % of balance

## Install

- Copy "TL Small Matter Pro.ex5" to MQL5\Experts, restart or refresh the Navigator.
- One chart per pair (any timeframe; the EA works on H4 internally), one magic number per pair.
- HEDGING account required (the ladder holds several orders at once).
- Enable "Allow DLL imports" only for the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook).

## Risk Warning

Averaging without a stop loss can lose the whole account. hayseed's own verified

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
