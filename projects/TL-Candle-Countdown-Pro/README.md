<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Candle Countdown Pro

**Candle countdown for any timeframe list — including custom M4 / M7 / S30 — with trend state per candle.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Candle_Countdown_Pro_ccp_7_XAU_M1.png" alt="TL Candle Countdown Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Candle Countdown Pro.ex5`](MT5/TL%20Candle%20Countdown%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Does

- Counts down the close of the candle for a whole LIST of timeframes at once, on any chart timeframe - e.g. the M4 candle on an M1 chart.
- Every MT5 timeframe works: M1 M2 M3 M4 M5 M6 M10 M12 M15 M20 M30 H1 H2 H3 H4 H6 H8 H12 D1 W1 MN ... and custom ones MT5 does not have: M7, M45, H5, D2, S30 (seconds), or just a number (7 = 7 minutes). Input "Timers: list", separated by commas, e.g.  M1,M4,M15,H1,H4,D1
- Trend of every running candle in every timeframe: mini candle + arrow + pips since the open (green = bullish, red = bearish), "BULL / BEAR BIAS" summary over all timers, direction pill on the focus timer, the chart tag turns green / red too.
- Focus timer (input "Timers: focus timer", or simply click a row in the panel): big countdown with a progress ring, "M1 candle 3 of 4 in this M4", and a live tag right next to the current candle on the chart.
- Final seconds pulse red (input "Timers: final seconds highlighted").
- Market open / closed from the broker's sessions - timers pause while the market is closed and show when it opens again. All times are server time, exactly like the chart.
- Alerts before the close (popup / sound / push / e-mail), e.g. "M4,H1" 10 seconds before the close, or 0 = when the new candle opens. Optional tick sound in the final seconds.
- Panel: click X to close it to a small pill that keeps counting, click the pill to reopen, drag the header to move it. Position, focus and open / closed state survive timeframe changes.
- Buffers for EAs: 0 = focus candle seconds left, 1 = chart candle seconds left, 2 = focus candle direction (+1 bullish / -1 bearish / 0 flat).

## How Custom Timeframes Are Aligned

Intraday timers start at midnight server time like MT5's own bars (a length that does not divide the day, e.g. M7, ends its last candle at midnight). W1 starts on Sunday, MN on the 1st.

## Install

- Copy  TL Candle Countdown Pro.ex5  to  File > Open Data Folder > MQL5\Indicators Refresh the Navigator and drag the indicator on the chart.
- For the YouTube / RoboForex / WhatsApp / Forex Factory buttons tick "Allow DLL imports".

- Questions / more free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
