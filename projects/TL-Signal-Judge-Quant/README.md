<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Signal Judge Quant

**Reads every indicator, arrow and level on your chart and scores each new signal 0–100 with 17 scenario checks.**

![version](https://img.shields.io/badge/version-v1.04-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_SignalJudgeQuant_Post.png" alt="TL Signal Judge Quant" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Signal Judge Quant.ex4`](MT4/TL%20Signal%20Judge%20Quant.ex4) |
| **MT5** | [`TL Signal Judge Quant.ex5`](MT5/TL%20Signal%20Judge%20Quant.ex5) |

> Compiled build only — source code is not published.

## What It Does

Attach it to any chart that already has indicators on it. The EA
- finds every indicator on the chart (main window + sub windows) and every arrow / text signal object that indicators draw, + every HORIZONTAL LINE / ZONE on the chart (from indicators or drawn by hand: full-width lines, horizontal trend lines with start / end, rectangle edges),
- works out what kind of signal each one gives - arrows, colour changes, trend-state flips, up/down line switches, line crosses, band re-entries, oscillator level exits (30/70, 20/80, -100/+100 ...), zero-line crosses - and which signal just fired,
- judges that signal with 17 scenario checks and gives it a score 0-100: 70+ STRONG  - the signal has substance 55+ VALID   - acceptable, check the cons 40+ WEAK    - doubtful <40 REJECT  - no substance, skip it

## The 17 Checks (hover any row in the dashboard for the details)

Trend EMA 50/200 · two higher timeframes (last COMPLETED candle) · swing structure (HH/HL, LH/LL, breaks) · momentum (RSI + MACD) · overextension · trend strength ADX (trend signals vs. reversal signals) · volatility regime (ATR percentile) · room to the next unbroken swing level · location in the range · signal candle · volume · RSI divergence · do the OTHER indicators agree · TRACK RECORD of this indicator on this chart (only signals resolved before the judged one count - no look-ahead) · spread + session activity · REPAINT / LAG TEST. Red flags cap the score: repainting, trading into a level, against every trend, spread too wide.

## Horizontal Lines (v1.02)

All horizontal levels of the main window form one source "Horizontal lines":
- **breakout** — = a candle closes through the line   (judged as trend signal) rejection = touches the line, closes back       (judged as reversal signal)
A segment only counts between its start and end, a full-width line from the moment it was drawn. On top, the "Room to next S/R" check now uses your lines as support / resistance - a buy right under your "D1 High" is flagged as trading into a level (the check names the line). Inputs: "Source: horizontal lines / zones as signals", "Judge: use the chart's horizontal lines as support / resistance".

## Repaint Detector

Many arrow indicators repaint: in history they look perfect, live they are useless. The EA watches every indicator live and counts signals that vanish, move or appear late. It also flags arrows that sit exactly on swing highs / lows (typical for zigzag-type indicators). Such indicators are marked "REPAINTS" and their signals are capped at 40.

## Dashboard (animated, drag the header, X closes it to a pill)

VERDICT          indicator, signal, BUY/SELL, score gauge, pros / cons, browse older signals and see if they worked SCENARIO CHECKS  the 17 checks with bars and values with / against trend, higher TFs, trending / ranging, room, volatility - and: did the judge's VALID signals do better than its REJECT signals? INDICATORS       every indicator found, its last signal, click to pin AUTO TRADER      all trade settings + live status Score tags are drawn at the signals on the chart. Show / hide every block with the chips in the header (VERDICT, CHECKS, MATRIX, LIST, TRADER) - remembered per chart. Defaults: inputs "Panel blocks". The AUTO TRADER block shows by default only when auto trading is ON. The indicator list can show ALL / only JUDGED indicators (that give signals) / only ACTIVE ones (current direction, no grey dot) - button "SHOW" or input. The version number is shown next to the name.

## Auto Trading (Off by default)

- trade only signals from score X (and optionally only certain indicators)
- lots: fixed or risk % of the balance
- stop loss / take profit in ATR or in pips
- trailing stop (pips or ATR) with start and step
- break-even after X pips, lock Y pips
- news filter: no new trades X minutes before / after high (or high + medium) impact news of the symbol's currencies, optional close before news MT5: built-in economic calendar. MT4: Forex Factory calendar - add <https://nfs.faireconomy.media> under Tools > Options > Expert Advisors > Allow WebRequest.
- trading hours (server time, also over midnight) + trading days
- basket: several positions per direction (max, min distance), basket take profit / stop loss in account money
- close positions on an opposite signal that passes the score
- max spread filter
Always test on a demo account first. A good score raises the odds, it does not guarantee a winning trade.

## Strategy Tester

The tester has no chart indicators. Put them into "Extra indicators", e.g. MACD, RSI(14), BANDS(20,2), MA(50), EMA(20), STOCH(5,3,3), CCI(14), SAR, ICHIMOKU, ALLIGATOR, FRACTALS, AO, ADX(14), MyCustomIndicator Custom names = file name in the Indicators folder, read with its default inputs.

## Notes

MT4 HIDDEN COPIES (v1.04): because MT4 can't read the indicator on the chart, the EA loads its own hidden copy (default inputs). A copy that draws lines or labels would draw them a second time - the EA now removes everything its copies draw and puts moved objects back (input "Source: remove what the EA's hidden indicator copies draw"). To read the indicator with YOUR settings, list it in "Extra indicators" with its numeric inputs in order, e.g. MyLevels(5,10,20) (numbers only, up to 8; leave them out for the defaults). Put the chart copy into "Ignore" if you only want the extra-list version judged. MT5 reads the indicators exactly as they sit on the chart (your inputs). MT4 has no access to the chart instance: built-ins are read from their name (e.g. "MACD(12,26,9)"), custom indicators via iCustom with their default inputs. MT4 only tells the EA the DISPLAY name of an indicator - since v1.01 the EA searches MQL4\Indicators (incl. sub folders) for the matching file by itself (needs "Allow DLL imports"). If it still shows "add file name to Extra list", put the file name (without .ex4) into "Extra indicators". "objects only - no buffers" = the indicator only draws objects; its arrows are read in the row "Objects: ...".

## Changes

v1.04  MT4: no more duplicate lines / labels from the EA's hidden indicator copies; numeric inputs for custom indicators in the extra list v1.03  show / hide panel blocks (chips + inputs), trader block auto-hidden when auto trading is off, indicator list filter, version next to the name v1.02  horizontal lines + zones: breakout / rejection signals and used as support / resistance in the judge; indicator list shows all sources v1.01  MT4: finds the indicator file behind the display name automatically, clear messages ("add file name to Extra list" / "objects only"), 3 load attempts (MT4 returns nothing on the very first load) v1.00  first release

## Install

- MT5: copy MT5\TL Signal Judge Quant.ex5 to  File > Open Data Folder > MQL5\Experts
- MT4: copy MT4\TL Signal Judge Quant.ex4 to  File > Open Data Folder > MQL4\Experts Refresh the Navigator and drag the EA on a chart with your indicators.
- For the YouTube / RoboForex / WhatsApp / Forex Factory buttons tick "Allow DLL imports". For auto trading tick "Allow Algo Trading".

- Questions / more free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
