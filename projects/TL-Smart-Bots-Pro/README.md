<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Smart Bots Pro

**Rebuild of the "smart bots" reel, read frame by frame: signal circle on XAUUSD M1, then market order + 3 stop orders pyramiding with momentum.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Smart_Bots_Pro_XAUUSD_M1_sbp_shot.png" alt="TL Smart Bots Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Smart Bots Pro.ex4`](MT4/TL%20Smart%20Bots%20Pro.ex4) |
| **MT5** | [`TL Smart Bots Pro.ex5`](MT5/TL%20Smart%20Bots%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it is A rebuild of the Facebook reel "Power of automatic trading bot / smart bots" (page "Agibt" / AGI Bot AI, XAUUSD M1, 26 Sep 2025). The reel has no voice and no description - every rule below was read from the screen recording frame by frame.

What the reel shows (and what the EA does)
- A green (buy) or red (sell) CIRCLE appears on the M1 chart.
- A basket starts: 1 order at market + 3 STOP orders in trade direction (buy: 3 buy stops above, sell: 3 sell stops below) = pyramid on momentum. Reel: buy 3746.140, buy stops 3747.905 / 3748.367 / 3748.829
- Every leg has its OWN take profit and stop loss (values of the reel, defaults): leg      TP distance   SL distance market      4.651         3.535 stop 1      3.043         4.435 stop 2      3.537         4.649 stop 3      2.310         4.899
- After 3 take profits the last open leg goes to break-even (+0.031).
- Result in the reel: all 4 legs hit TP, 400 -> 4,459 USD with 3.00 lots per leg (that is ~30x the account in lots - pure gambling, do NOT copy the lot size).

Signal circles The reel does not say what draws the circles. Default "Structure": a confirmed HIGHER LOW = BUY circle, a confirmed LOWER HIGH = SELL circle (swing point = extreme of 2 bars left / 4 bars right, confirmed 4 bars later, no repaint). On real XAUUSD M1 data of the same day this hits all 4 circles of the reel within +-2 bars. Other modes: every swing point, or MANUAL = only the BUY / SELL basket buttons.

Dashboard Animated panel (drag the header, X closes it to a pill, click the pill to reopen): signal, basket table with every leg (entry / TP / SL / state), live ladder, one-click BUY / SELL / CLOSE / AUTO buttons, statistics. Tooltips can be switched off. Buttons YouTube / RoboForex / WhatsApp / Forex Factory need "Allow DLL imports".

Honest backtest (RoboForex, XAUUSD M1, 0.01 lot per leg, 10,000 USD) (signal 13:59 server time) closed with 4 of 4 take profits like in the video.

Install MT5: copy "TL Smart Bots Pro.ex5" to MQL5\Experts, MT4: the .ex4 to MQL4\Experts, refresh the Navigator, drag it on XAUUSD M1, allow Algo Trading (+ DLL for the buttons).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
