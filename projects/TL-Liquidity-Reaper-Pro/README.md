<div align="center">

# ⚡ TL Liquidity Reaper Pro

**Independent MetaTrader implementation of the published Liquidity Reaper [JOAT] rules — requested on Forex Factory.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Liquidity Reaper Pro.ex5`](MT5/TL%20Liquidity%20Reaper%20Pro.ex5) |

> Compiled build only — source code is not published.

## Overview

Independent MetaTrader implementation of the published Liquidity Reaper [JOAT] rules by officialjackofalltrades, requested by Xepo-fx in post #256. Original indicator: <https://www.tradingview.com/script/7J5v2QPQ-Liquidity-Reaper-JOAT/> Video: <https://www.youtube.com/watch?v=RJuGsIMTd1k> Request: <https://www.forexfactory.com/thread/post/15960735#post15960735>

## Installation (MT5 Release)

- MT5: copy the EX5 into File > Open Data Folder > MQL5 > Experts.
- Refresh Navigator and attach the EA to a standard candlestick chart.
- The chart symbol and timeframe are used for signals.
- Auto Trading is OFF by default. Signals, rails, zones and dashboard still work.
- For orders, enable InpAutoTrade or the panel toggle AND MetaTrader's trading permissions. Use a demo account to become familiar with the behavior first.
- Allow DLL imports only if you want the website buttons to open your browser.
- The imported Windows shell32 function is used for these buttons only.

## Signal Rules

Confirmed swing highs/lows become liquidity pools. Default strength is 8 completed bars on each side. A pivot is not known before the right bars close. Crossing a pool consumes it and opens a pending sweep for that side. Confirmation is allowed on bars 1, 2 or 3 after the sweep, never the sweep bar. BUY: close above the swept low pool AND above the confirmation candle's open. SELL: close below the swept high pool AND below the candle's open. The maximum excursion beyond the pool must reach 25% of the ORIGINAL sweep candle's range. The extreme is updated while the sweep remains pending. Confirmation volume must be at least 1.1 times its 20-bar SMA, including the confirmation candle. A new sweep on a side replaces that side's pending one. When several pools are crossed together, the oldest crossed pool is retained, matching the public indicator's reverse traversal and overwrite behavior. Active pool limit: 12 per side. Swept zones remain for 120 bars by default.

## Stop / Targets / Execution

Default stop distance: Wilder ATR(14) x 1.5 from the signal close. Alternative: percentage of the signal close. TP1/TP2/TP3 are 1R/2R/3R. All three targets are shown. InpExitTarget selects a FULL-position exit at TP1, TP2 or TP3; default TP3. No automatic partial exits, break-even or trailing. One EA position per symbol/magic. Opposite signals close and reverse by default; InpReverse=false ignores new signals while a position is open. Same-direction signals do not add exposure. CLOSE ALL affects this EA's symbol/magic only. Default sizing is 0.5% of balance using the actual quote-to-stop distance. InpRiskPct=0 selects fixed lots. Lot size is rounded down; undersized orders are skipped rather than increased to the broker minimum. Spread, lot cap, margin, tick size and stop distance are checked. SL and selected TP are sent with the order. A failed request is logged and is not retried on that signal. Foreign positions on an MT5 netting symbol prevent new orders. Use a distinct magic number for independent instances/timeframes. Startup history never creates orders. Signals are handled once per closed bar.

## Important Differences From A Tradingview Indicator

Orders are submitted after the confirmation candle closes, at the next available quote. Fill prices, spread, slippage and broker trading rules apply. TradingView can show tentative intrabar signals; this EA waits for bar close. Forex tick volume is selected by default. InpRealVolume uses real volume only when the broker supplies it. Different feeds, sessions and bars can change signals; matching settings do not guarantee identical TradingView chart marks. The video's manually drawn trendlines are not an automatic trend filter. Chart TP/SL graphics describe the most recent signal, including signals which were not traded. The POSITION block reports actual broker positions separately. The visual framework freezes after its stop or TP3 is touched and is replaced by the next signal. The chosen execution target does not alter signal history. On restart, signal state is rebuilt from InpWarmup bars (default 3000). Raid counts refer to this loaded history, not to an account's trade results.

## Dashboard

Standard trader.lifestyle Canvas panel: drag the header, X to minimize to a pill, click the pill to reopen. Hover explanations, responsive columns, RoboForex / WhatsApp / YouTube / Forex Factory / IndicatorGenius buttons. Native time/price chart objects follow scrolling and zooming. Deleted panel and overlay objects are recreated. No account lock and no expiry.

Trading involves risk. Signals do not guarantee profitable trades. This package is an independent implementation, not an official JOAT product. No source code is included in the Forex Factory ZIP.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
