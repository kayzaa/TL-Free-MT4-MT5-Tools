<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Fibo Compass Pro

**FiboCompassArrows rebuilt for MT4 and MT5 with the first animated canvas quant panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Fibo_Compass_Pro_fcp_6_H1.png" alt="TL Fibo Compass Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Fibo Compass Pro.ex4`](MT4/TL%20Fibo%20Compass%20Pro.ex4) |
| **MT5** | [`TL Fibo Compass Pro.ex5`](MT5/TL%20Fibo%20Compass%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Does

- Takes the high / low of the previous completed D1 candle (any source timeframe can be chosen, the small Sunday candle is skipped) and builds the compass: 200 %    STOP TRADING   - full-range extension, stop opening trades 138.2 %  BUY TP         - target for breakout buys 100 %    BREAKOUT BUY   - previous high 78.6 %   RETRACE SELL   - top of the retrace sell zone (78.6 - 100 %) 50 %     PIVOT / TP     - middle, target for retrace trades 23.6 %   RETRACE BUY    - top of the retrace buy zone (0 - 23.6 %) 0 %      BREAKOUT SELL  - previous low -38.2 %  SELL TP        - target for breakout sells -100 %   STOP TRADING
- Arrows when price hits a level: up arrow = buy level, down arrow = sell level, diamond = TP / pivot, cross = stop-trading level. Hover any arrow for the details.
- Trigger: "Touch" (live, the moment price touches the level - like the original) or "Close cross" (confirmed when a candle closes through the level). By default only the FIRST hit of each level per day fires (no arrow spam).
- Alerts: popup / sound / push / e-mail, separately for entry, TP and stop levels.
- History: arrows on all calculated bars + the level sets of the last 5 days.
- Dashboard (animated, hover any block for an explanation): live zone ("RETRACE BUY ZONE", "BREAKOUT SELL - BELOW LOW", ...), compass gauge with the price marker, every level with price and distance in pips, D1 range, last signal.
  - click X to close it - a small pill stays, click the pill to open it again
  - drag the header (or the pill) to move it anywhere on the chart
  - position and open / closed state survive timeframe and symbol changes
- Buffers for EAs: 0 = buy, 1 = sell, 2 = TP / pivot, 3 = stop-trading (EMPTY_VALUE = no signal).

## Why The Original Did Not Work

- "unsupported file extension": the code must be saved as .mq4 (not .txt) inside MQL4\Indicators.
- The original only painted arrows on the current candle and erased them on every tick, so nothing stayed on the chart. This version keeps the full history.

## Install

- MT5: copy MT5\TL Fibo Compass Pro.ex5 to  File > Open Data Folder > MQL5\Indicators
- MT4: copy MT4\TL Fibo Compass Pro.ex4 to  File > Open Data Folder > MQL4\Indicators Refresh the Navigator, drag the indicator on the chart (any timeframe below D1).
- For the YouTube / RoboForex / WhatsApp / Forex Factory buttons tick "Allow DLL imports".

- Questions / more free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
