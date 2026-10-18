<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Liquidity Tracker Pro

**Liquidity sweep-and-run EA from the "Liquidity Tracker" video, with full multi-column panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Liquidity_Tracker_Pro_shot_H4_prev.png" alt="TL Liquidity Tracker Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Liquidity Tracker Pro.ex5`](MT5/TL%20Liquidity%20Tracker%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

No account lock, no broker lock, no expiry date. Runs with any broker.

Built from the video "How to Find Liquidity & Then Trade It" (Bulls, Bears and Backtests, YouTube 1tdbd0SFR_8). Every setting of the original TradingView indicator was read from the video frame by frame and rebuilt for MT5, plus the two trades shown in the video as rules.

## Installation

- Copy "TL Liquidity Tracker Pro.ex5" to  MQL5\Experts\ (File -> Open Data Folder). The two sub-window indicators are embedded.
- Tools -> Options -> Expert Advisors: allow Algo Trading and "Allow DLL imports" (DLL is only used by the 3 panel buttons to open links).
- Drag the EA onto a chart. The video trades GOLD (XAUUSD) on H4. Want only the indicator + alerts?  Trade mode = OFF.
- Push alerts to your phone: Tools -> Options -> Notifications -> MetaQuotes ID.

- Source code (optional): folder "src". To compile, first compile the two indicators into MQL5\Indicators\ (they are embedded as #resource).

## Part 1 - Liquidity Levels (price chart)

- **PMH / PML** — previous monthly high / low   (pink,   width 2) PWH / PWL  previous weekly high / low    (orange, width 2) PDH / PDL  previous daily high / low     (teal) PSH / PSL  previous swing high / low     (lime, pivot 30 left / 3 right, major swings) EQH / EQL  equal highs / lows            (white dotted, off by default) NYH/NYL, LONH/LONL, ASIAH/ASIAL  session ranges, only below H2 New York 09:30-16:00 NY time, London 08:00-16:00 London time, Asia 09:00-15:00 Tokyo time - daylight saving handled automatically. Labels "PWH  4697.07" sit in a gap of the line, equal prices side by side. Older periods are dashed and only drawn over the period they were live. All 7 settings groups of the original (General, Sessions, Swing, Equal highs/lows, Day, Week, Month) are inputs 1-7 with the same defaults.

## Part 2 - Wavetrend (sub-window)

Blue wave rising = buying pressure, falling = selling pressure. Area: BLUE = money flowing in, PURPLE = money flowing out. Dots = momentum change. BIG RED dot above +60 = extreme / overbought. BIG GREEN dot below -60 = extreme / oversold.

## Volume Explosion (sub-window)

Volume grouped over several bars (you see the trend, not single bars), grey inner band and yellow SURGE lines either side (Bollinger style). Bars through the yellow line = volume explosion (yellow dot). The original formula is not published - this is a faithful rebuild of the behaviour shown in the video.

## Panel

Liquidity map (nearest pools above/below, distance in % and ATR), WaveTrend + volume mini charts, the setup checklist, trade box, alerts, statistics. Hover any box for the explanation from the video. The panel always fits: on a small chart it is split into 2-3 columns or scaled down - nothing is cut off.

## 1. Approaching Zone - price within X % (default 0.25 %) of a weekly /

monthly level: "a trade is fast approaching".

## 2. Zone Broken - a candle Closed through the level.

Popup, sound and push notification. Setup and trade alerts on top.

## The Two Trades

When price reaches liquidity it does one of two things:

## Liquidity Sweep (grab and reverse) - video trade #1, gold H4, 24-28 Aug 2026

Level broken -> closes back inside within 18 bars -> checklist (extreme WaveTrend dot, money flow turned, volume against the break, weak break / Monday, waves turned) -> trigger: close through the day low (PDL) / day high (PDH) -> stop above the sweep extreme, target 2R. The EA takes the video trade at the same candle: Wed 26 Aug 20:00, sell after the PDL broke, +2R.

## Liquidity Run (break and continue) - video trade #2, gold H4, 5 Aug 2026

Candle closes through the level -> checklist (money flow side and curve, volume through the surge line, Tue-Thu, expansive candles, no extreme dot against it, smaller level already broken) -> entry: AT THE BREAK (default, best in the backtest - video: "you could have taken it here ... 16 to 1"), stop just behind the broken level FVG 50% LIMIT ("line in the sand" - what he waited for in the video) target 4R ("aimed for a four to one"). The EA finds the video's fair value gap (4213-4237 vs 4213-4243 in the video) and the 4R target is hit.

Monday is treated as quiet (no RUN breaks on Monday), Wednesday / Thursday are shown as peak days - both from the video.

## Risk / Management Inputs

Risk % per trade (default 1 %), fixed lot or lot per balance, max lot, max spread, max trades per week, break-even, swing trailing, time exit, Friday close. If the minimum lot would risk more than 1.5x your planned risk (very wide stop, small account) the trade is skipped. Entries that fall into the gold daily break (market closed) are queued and sent at the reopen.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
