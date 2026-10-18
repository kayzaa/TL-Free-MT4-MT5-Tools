<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL POC Retest Pro

**Free trading tool by trader.lifestyle**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL POC Retest Pro.ex4`](MT4/TL%20POC%20Retest%20Pro.ex4) |
| **MT5** | [`TL POC Retest Pro.ex5`](MT5/TL%20POC%20Retest%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

What it is An EA that trades the "accumulation -> volume profile POC -> retest" pattern shown in two short videos that were posted as a request on Forex Factory:
- **@worldwidecpt** — "How to catch entries like a professional trader" (accumulation, volume profile, manipulation, distribution) @shadow.intel.trades "Combine this pattern with volume for precise entries" (accumulation, volume profile breakout, pullback to POC, continuation) Credit for the trading idea goes to both creators. This is an independent MetaTrader implementation; it is not an official product of either of them.

The pattern (rules from the videos)
- Accumulation   price moves sideways and builds a range
- Profile        a fixed range volume profile over the WHOLE range -> POC (POC = price level with the most volume traded inside the range)
- Manipulation   price sweeps the liquidity below the range (BUY) / above it (SELL) or Breakout    price closes out of the range in trade direction (video 2)
- Push           price pushes through the POC and continues - no chasing
- Retest         wait for the pullback into the POC
- Reaction       a candle in trade direction at the POC = entry Stop              below the manipulation low (BUY) / above the manipulation high (SELL) Target            the liquidity high above (BUY) / low below (SELL) SELL is the exact mirror of BUY.

How the EA turns the discretionary parts into clear rules (defaults)
- **Range** — at least 20 bars (max 80) whose high-low span is at most 4 x ATR(14), and whose closes cross the middle of the range at least 3 times (sideways, not a slow trend). The box grows while price stays inside. The first bar outside fixes the box and the volume profile. Profile     24 rows (TradingView's default), tick volume, value area 70 %. "Auto" data: the profile is built from lower timeframe bars (e.g. M1 data for an H1 chart, at most 60 sub-bars per chart bar) like TradingView's fixed range volume profile. If that history is not available it uses the chart bars. Push        price must trade beyond the opposite range edge (BUY: above the range high), optional: X ATR beyond the POC instead. Retest      a later bar comes back to within 0.10 ATR of the POC. Reaction    within 3 bars after the touch a candle closes in trade direction AND beyond the POC (BUY: bullish candle closing above the POC). Optional: body >= 50 %. Cancelled   a close 0.30 ATR through the POC on the wrong side, or 48 bars after price left the range without an entry. Setup type  SWEEP = the other side of the range was swept first (video 1), BREAKOUT = price closed out of the range in trade direction (video 2). Input: both / sweep only / breakout only. HTF bias    optional filter (video 2): last closed H4 bar above (BUY) / below (SELL) EMA 50. One setup per range. Closed bars only - nothing repaints.

Stop, target, exit
- **Stop** — beyond the lowest low (BUY) / highest high (SELL) of the range and everything after the exit (= the manipulation extreme) + 0.10 ATR. Alternatives: beyond the retest candles, or an ATR multiple. Target      the highest high (BUY) / lowest low (SELL) of the 100 bars before the range = the liquidity the price came from. If it is closer than 1.5R (or there is none) the EA uses a 3R target (input: skip the trade / trade without TP instead). Target mode "R multiple" is available as well. Break-even  optional, off by default: stop to entry after +1R. Stop and target are sent with the order. One trade at a time by default.

Money management 1 % risk of the balance per trade (lot size from the stop distance) or fixed lots, max. lots, max. open trades, max. spread, magic number. If even the minimum lot would risk more than twice the allowed amount, the trade is skipped instead of being increased.

Auto trading is OFF by default The EA starts in signal mode: ranges, profiles, signals, alerts and the dashboard work, no orders are sent. Switch it on with the input "Auto trading ON" or the AUTO TRADING button on the dashboard.

On the chart Dark chart theme (restored when the EA is removed), every range as a box with its volume profile (gold = POC row, blue = value area), the gold POC line, dotted value area lines, red dashed lines when the liquidity below / above the range was swept, glowing BUY / SELL labels at the entry, stop and target zones. Everything is anchored to time and price and follows scrolling and zooming. Deleted objects are rebuilt automatically.

Dashboard
- **ACCUMULATION** — state (searching / accumulation / left the range / BUY or SELL setup), range high / low, size in bars and ATR, how price left the range VOLUME PROFILE   mini profile of the range, POC, value area high / low, price vs POC SETUP CHECKLIST  BUY | SELL: range, sweep, close out of the range, push, retest, HTF bias, last signal and why it was (not) traded STOP · TARGET    stop and target settings, lots, break-even POSITION         position, stops, results, AUTO TRADING on / off, CLOSE ALL Drag the header to move it, X folds it to a small pill (click to reopen). Hover any block for an explanation (tooltips can be switched off). The dashboard moves away from other trader.lifestyle panels on the same chart.

Differences to the videos
- The videos are discretionary: you draw the range and the profile by hand. The EA uses the defined rules above, so it will not always pick exactly the same range you would.
- Forex has no central volume. The profile uses the broker's tick volume (like TradingView on forex symbols); different brokers can show slightly different POCs.
- Entries are taken at the close of the reaction candle, not intrabar.
- The "higher timeframe bias" of video 2 is not defined in the video; the EA offers an EMA filter for it (off by default).

Installation MT5: MT5\Experts\TL POC Retest Pro.ex5 -> File > Open Data Folder > MQL5\Experts MT4: MT4\Experts\TL POC Retest Pro.ex4 -> File > Open Data Folder > MQL4\Experts Refresh the Navigator (right-click > Refresh) and attach the EA to a chart. It uses the chart's symbol and timeframe. For orders enable Algo Trading / AutoTrading in the terminal. "Allow DLL imports" is only needed for the YouTube / RoboForex / WhatsApp / Forex Factory buttons (they open your browser via the Windows shell32.dll). The EA trades without it.

Main inputs Range: min / max bars, max height in ATR, min crosses, ATR period. Profile: rows, data (auto lower timeframe / chart bars), value area %. Setup: type (both / sweep / breakout), direction, push mode + ATR, retest tolerance, cancel distance, reaction candle, bars for the reaction, expiry, HTF bias filter + TF + EMA. Stop & target: stop mode + buffer, target mode, bars for the liquidity target, min. R, no-room rule, R target, break-even. Money: risk % or fixed lots, max. lots, max. open trades, max. spread. Display: dashboard, position, auto-avoid, tooltips, chart drawing, labels, history bars, ranges / profiles drawn, dark theme, alerts (popup / sound / push).

Risk warning: no profit promise - trading involves high risk. Test on a demo account first.

trader.lifestyle - free tools thread on Forex Factory: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
