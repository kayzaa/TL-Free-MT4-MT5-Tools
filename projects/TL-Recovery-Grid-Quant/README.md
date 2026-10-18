<div align="center">

# ⚡ TL Recovery Grid Quant

**Recovery-grid EA with daily equity trail, loss-pause guards and a full quant panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Recovery_Grid_Quant_view.png" alt="TL Recovery Grid Quant" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Recovery Grid Quant.ex5`](MT5/TL%20Recovery%20Grid%20Quant.ex5) |

> Compiled build only — source code is not published.

## Overview

What it is A grid & recovery basket EA for XAUUSD M3. It is my own rebuild of the system that K2M RapidSync describes in his Forex Factory thread "MT5 Grid and Recovery EA" (thread 1408891) and shows in his silent tester video. The original is closed source, so this is NOT his code. I rebuilt it from the public description, the panel screenshots and a second-by-second read of the video, then added guards against the one pattern that blows grid accounts.

How it trades
- Signal: MACD 12/26/9 and MACD 5/9/4 on M3 and M10 (5 sub-signals per timeframe, score -10..+10). Score >= 4 with M3 agreeing = BUY basket, <= -4 = SELL basket.
- Entry guard (as in the video panel "ENTRY GUARD STATUS"): EDGE      no new basket while price sits in the top/bottom 25 % of the H1 candle RES HOLD  max 4 baskets in a row in one direction, 3-5 s pause after a basket
- Grid: gap = ATR(M1,14) x 0.50, wider for deeper levels and in hot markets (G PROTECT x1.2 / x1.35 / x1.5), never below 3.30 $ + spread. Lots 0.02, 0.02, 0.03, 0.03, 0.03, 0.04 ... (as in the video), max 8 levels. From level 5 the gap grows x1.6 per level (auto grid), max gap 40 $.
- Every position in profit is trailed with a real stop loss (start 1.20 $, gap 0.50 $). That profit is "Realized" (R) for the basket.
- Basket close on R + Floating:  ETC  R+F >= +20  ·  RFC trail  arms at +10, closes at peak - 1.
- Daily equity trail: after +500 for the day a lock follows the peak (peak - 50).

Extra guards (not in the original) - the loss pattern Grid EAs win almost every basket and lose rarely but big. I logged 4,623 baskets (Jan-Sep 2026, real ticks) and lined every stopped basket up against the price data: the market before entry looks the same for winners and losers (sideways). The losers are baskets where a quiet range BREAKS OUT against the basket in the first 1-2 hours (first-hour move against the basket: median -21.6 $ vs 0 $ for normal baskets). The EA therefore has:
- **BREAKOUT EXIT** — in the first 120 min: >= 8 $ directed move against the first entry (efficiency >= 0.25) -> close the basket small, no new basket against the breakout for 60 min TIME WINDOW    new baskets only 12:00-16:00 server time (Asia open was the worst hour block, 12-16 the best; three testers in the thread found the same) TREND GUARD    no basket against a strong H1 trend (ADX >= 28 + EMA50 slope) IMPULSE GUARD  no new grid level while ATR(14)/ATR(120) on M1 >= 2.2 BASKET STOP    hard close at a floating loss of 6 % of balance + 4 h cooldown TIME GUARD     no new basket in the first 2 hours of the week and Friday after 19:00
All of them can be switched off to run the "original style" logic.

Backtests (XAUUSD M3, 30,000 USD, 1:500, every tick based on real ticks, RoboForex, 2026.01.01 - 2026.10.01, my rebuild - not the original EA):
- **no guards ("original style")** — Q1 -9,328 + Q2-Q3 -14,190 · DD 64 %  · worst basket -8,227
The guards remove the account-killing tail. They do NOT create an edge: the entry signal (my MACD approximation) has none in these tests. Treat this EA as a study tool / framework, not as a money machine.

Requirements
- HEDGING account (several positions per symbol). Netting is not supported.
- Allow DLL imports (only used by the 4 link buttons on the panel).
- Defaults are for gold with 2-digit prices. Gaps/trailing are in price ($).
- Reference capital in the thread: 30,000 USD for 0.01-0.02 start lot.

Panel

## Entry Guard Status · Grid Engine (Final G, lot ladder) · Basket R+F (Etc / Rfc gauge)

DAILY EQUITY TRAIL · LOSS-PATTERN GUARDS · PERFORMANCE. Hover any block for help. Chart lines: ETC target, RFC arm/lock, next grid level, day range and extension.

Risk ---- This is a grid. It can lose a lot of money in a long one-way market, even with the guards. Test on demo first. Past tests do not predict the future.

trader.lifestyle · free tools thread: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
