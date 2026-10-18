<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL KenneDyne DRIVE EA

**The D.R.I.V.E. framework + Engulfing Killer Order Block entry, built from 6,794 channel posts. Made for gold.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_KenneDyneDRIVE_screenshot.png" alt="TL KenneDyne DRIVE EA" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL KenneDyne DRIVE EA.ex5`](MT5/TL%20KenneDyne%20DRIVE%20EA.ex5) |

> Compiled build only — source code is not published.

## Overview

An Expert Advisor built around the trading method taught in the Telegram channel "KenneDyne spot" (t.me/KenneDynespot): the D.R.I.V.E. framework + the Engulfing Killer Order Block entry. Built for XAUUSD (Gold), works on any symbol.

All 6,794 channel posts (Jul 2023 - Oct 2026) were read and the rules were taken from his own posts. The post numbers are quoted in brackets.

## 1. The Method As Implemented

Timeframe alignment ("2 timeframes below", post #6047 / #7127)
- **Swing/Day (default) : W1 direction** — ->  H4 breakout + POI  ->  M15 entry Position            : MN direction  ->  D1 breakout + POI  ->  H1 entry Scalping            : D1 direction  ->  H1 breakout + POI  ->  M5 entry

D - DIRECTION (bias)
- Key levels = Malaysian SNR on the direction TF: swing highs/lows measured on candle BODIES; only FRESH levels (never touched again) are used.
  - Level touched + last breakout-TF swing before the touch broken by a candle CLOSE  -> bias in the rejection direction (reversal).
  - Level broken by a breakout-TF close        -> bias in the breakout direction, the broken level becomes the POI (RBS / SBR retest).
  - Structure confirmation one TF below the direction TF ("Weekly bias: Daily BO = confirmation", post #4139): a D1 close beyond the last D1 swing sets the bias as well.
R / I - RANGE + INTEREST POINT
- Every breakout-TF structure break (close beyond the last swing) in bias direction creates a POI = the order block at the origin of the impulse leg ("every H4 candle = new entry opportunity on M15", post #5823).
  - The POI is dropped when price closes beyond its invalidation, when the bias flips or after "POI lifetime" bars.
E - ENTRY: Engulfing Killer OB on the entry TF, at the POI
- Type I  (Stop Hunt + Body Breakout)  - bullish: candle 1 bearish, candle 2 sweeps the low of candle 1 and CLOSES above the HIGH of candle 1. KenneDyne: "Type I has high probability, others are 50/50" (#3916).
  - Type II (Shift in Market Structure + Body BO) is available, OFF by default.
V - VALUE OF RISK
- 0.5 % risk per trade, lot size from the stop distance.
  - SL behind the pattern extreme + buffer, max SL (skip wider setups).
  - TP1 = 3R: 90 % closed, the runner goes to break-even and runs to the next opposite direction-TF key level (max 600 pips). Min reward:risk 1:3.
  - Daily limits: max 1 % loss, stop after 2 losses, max 3 trades.

## Filters

- Asian window 00:00-04:00 UTC (engulfings/breakouts there are "often fake", #3376 / #3497), late Friday (weekly close), high impact USD news (live, MT5 economic calendar).

## 2. Installation

- Copy "TL KenneDyne DRIVE EA.ex5" to  MQL5\Experts\  (File > Open Data Folder).
- Restart MT5 or right-click "Expert Advisors" > Refresh in the Navigator.
- Drag the EA onto an XAUUSD chart (any timeframe - the EA reads its own TFs).
- Enable "Algo Trading" and "Allow DLL imports" (only used to open the panel links YouTube / RoboForex / WhatsApp / Forex Factory / IndicatorGenius). The dashboard appears top-left: drag the header to move it, X closes it to a small pill (click the pill to reopen), hover any block for an explanation.
- On start the EA rebuilds the last 30 days (bias, POIs, signals, no trades), so the current state is visible immediately.

- Broker time: in the Strategy Tester set "Broker GMT offset winter/summer" (default 2/3 = EET brokers such as RoboForex, IC Markets...). Live, the offset is detected automatically.

## 3. Key Settings

Timeframe alignment ..... W1 > H4 > M15 (default) | MN > D1 > H1 | D1 > H1 > M5 Type I / Type II ........ which Killer OB types are traded (default I only) Entry model ............. confirmation (market at pattern close) | limit at OB edge Stop mode ............... ATR (default) | fixed pips (30-40 as posted) | pips scaled to price (pips x price / 2000) TP1 mode ................ 3R (default) | 100 pips Risk per trade .......... 0.5 % Daily limits ............ 1 % / 2 losses / 3 trades Filters ................. Asia, Friday cutoff, news

## 5. Files

- TL KenneDyne DRIVE EA.ex5 ... the Expert Advisor README_EN.txt ............... this file DRIVE_STRATEGY_EN.txt ....... the rules extracted from the channel (short form)

- Created with IndicatorGenius  -  <https://indicatorgenius.com/> Trader Lifestyle  -  youtube.com/@traderlifestyle  -  Forex Factory thread 1428808

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
