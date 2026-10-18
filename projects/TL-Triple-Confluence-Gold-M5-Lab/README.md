<div align="center">

# ⚡ TL Triple Confluence Gold M5 Lab

**Trend-pullback analysis for gold M5: EMA 25/75/140 structure, ATR-based stops and clear signal pills. Indicator only.**

![version](https://img.shields.io/badge/version-v1.20-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/Screenshot_MT5.png" alt="TL Triple Confluence Gold M5 Lab" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Triple Confluence Gold M5 Lab.ex4`](MT4/TL%20Triple%20Confluence%20Gold%20M5%20Lab.ex4) |
| **MT5** | [`TL Triple Confluence Gold M5 Lab.ex5`](MT5/TL%20Triple%20Confluence%20Gold%20M5%20Lab.ex5) |

> Compiled build only — source code is not published.

## Free Forex Factory Edition / Discretionary Chart Indicator

Separate filename: TL Triple Confluence Gold M5 Lab.ex5 / .ex4 MT4 and MT5 builds included. See PLATFORM_NOTES.txt. No orders, DLL, account lock or expiry.

## Purpose

Trend-pullback analysis for Gold M5. Choose whether a setup fits your own plan; there is no requirement to trade every signal. The indicator places no orders. Credits: Trader DNA, <https://www.youtube.com/watch?v=wf6s7HHUP_8.> The precise mechanical filters and exits below are our implementation additions.

## Entry Rules / Defaults

EMA25 > EMA75 > EMA140 for BUY, reversed for SELL. Middle and slow EMA must each move >=0.08 ATR over 8 closed bars in that direction; fast EMA may flatten during the pullback. Fast/slow separation >=0.50 ATR. Signed efficiency over 30 bars >=0.10 in the EMA direction: direction*(close-close[30])/sum(abs(close changes),30 bars). RSI75 >51 for BUY, <49 for SELL; close beyond slow EMA on trend side. All trend gates rechecked each close; failures clear the pending EMA touch. Two consecutive qualifying trend bars required. No retained trend permission. An EMA must be touched within 8 bars, allowing 0.10 ATR tolerance. Track deepest touched EMA. Confirmation closes beyond that EMA and prior close in trend direction, with a matching bullish/bearish body and stochastic K/D cross. Stochastic14/3/3; A extreme and B standard enabled. A means both lines <=20 for BUY or >=80 for SELL on cross/preceding bar. Both classes target 2R. At least 6 bars between decisions. Touch consumed after an entry decision. No requirement to close beyond fast EMA when a deeper EMA was tested.

## Stop / Target / Time Exit

BUY stop = lowest low of last 5 completed candles minus 0.25 ATR. SELL stop = highest high of last 5 candles plus 0.25 ATR. Stop distance from the signal CLOSE must be at least 1 ATR (widen if needed). Skip a setup if that distance exceeds 3 ATR. No future swing pivots are used. Entry at next bar open, stop remains fixed. Next-open risk can differ from close-based ATR bounds, especially at gaps. Invalid next-open risk => GAP SKIP. TP = 2 times initial entry-to-stop price risk. No trailing, BE or partials. If no SL/TP resolved first, exit at close of the 36th completed holding bar (entry bar counts as 1). M5: 180 trading minutes, longer across closures. TIME EXIT can win or lose; its result contributes to totals and cash estimates. It is an OHLC simulation at the close, not guaranteed executable slippage-free.

## Costs And Outcomes

Recorded spread from each historical bar is used by default, with fixed InpSpreadPoints=30 fallback if missing. Symbol points are not dollars. BUY entry adds the entry bar spread; SELL exit OHLC adds each exit bar spread. Bar spread does not reconstruct tick-by-tick ask quotes or spread at exact fill. Assumed round-turn commission = 7 account-currency units / lot; set your costs. Price-R includes spread, excludes commission. Money deducts commission and uses CURRENT tick value/size and selected lots (default0.10). No historical FX, swap or slippage reconstruction. Current symbol pricing may differ by broker. If both SL/TP occur in one bar without an opening resolution, show AMBIGUOUS, excluded from dashboard settled totals. Unresolved signals show OPEN and are excluded from resolved panel totals. Independent overlapping hypothetical signals; NOT account returns/equity.

## UI / Installation

- Copy EX5 to MQL5/Indicators/TripleConfluence (EX4 under MQL4/Indicators).
- Refresh Navigator, attach Gold M5 Lab to XAUUSD M5, Inputs > Reset.
- Default instance ID G avoids colliding with older indicator ID A. Prefer one theme-owning indicator per chart.
- Large Canvas dashboard: drag header, X collapses, pill reopens, hover explanations.
- PREVIOUS/NEXT selects real historical signal. Selected risk/target guides and BUY/SELL pills show TP, SL, TIME EXIT, OPEN, AMBIGUOUS or GAP SKIP plus R/points.
- Current trend permission always refers to latest completed bar even when browsing history. Collision handling may show small dots instead of full pills.
- CSV export in local MQL Files overwrites the loaded window (default5000 bars).
- Link buttons show URLs; no DLL or browser automation required. Alerts/push off.
- Theme restored on remove. No orders are placed.
- Buffers: 0/1/2 EMAs; 3BUY/4SELL next-open entry; 5SL; 6TP; 7outcome.
- Status0 OPEN,1TP,2SL,3AMBIGUOUS,4GAP SKIP,5TIME EXIT. Outcome is retrospective, never an entry filter. Forming candles excluded from completed outcomes.

## Provenance

The original video supplies the EMA/RSI/stochastic concept. This edition adds explicit trend conditions, swing stops, target and time-exit rules. Created with IndicatorGenius.com — <https://indicatorgenius.com/> <https://trader.lifestyle> | <https://www.youtube.com/@traderlifestyle>

The screenshot illustrates the chart and individual signal labels. This archive contains no strategy test reports or aggregate performance tables. Read FF_POST_BBCODE.txt for the formatted forum description.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
