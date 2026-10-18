<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
<div align="center">

# ⚡ TL Liquidity Sweep Pro

**Liquidity sweep + CHoCH confirmation with a 0–100 setup score and TP1–TP3 + break even.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Liquidity_Sweep_Pro_tllsp_M5_s3.png" alt="TL Liquidity Sweep Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Liquidity Sweep Pro.ex4`](MT4/TL%20Liquidity%20Sweep%20Pro.ex4) |
| **MT5** | [`TL Liquidity Sweep Pro.ex5`](MT5/TL%20Liquidity%20Sweep%20Pro.ex5) |

> Compiled build only — source code is not published.

## What It Does

- BSL / SSL: dotted lines on unswept swing highs / lows (buy-side / sell-side liquidity).
- EQH / EQL: near-identical highs / lows are connected and tagged - stacked stops, liquidity magnet.
- Sweep = wick through a level + close back on the other side, marked with an X on the wick.
- Every sweep gets a quality score 0-100: wick depth past the level 30 %, reclaim strength 25 %, rejection wick 15 %, relative volume 15 % (only!), level significance (age + EQH/EQL) 15 %. The HTF bias only nudges the score (+/-5). It never blocks a trade.
- Signal: sweep score >= Min sweep score, then (default) CHoCH confirmation = close through the recent minor structure within the confirmation window, otherwise the setup quietly expires. Both sides swept on one candle = conflict, nothing fires. One trade at a time.
- Stop just beyond the sweep wick + small ATR buffer. TP1 / TP2 / TP3 = 1 / 2 / 3 x risk. At TP1 the stop moves to break-even.
- Dashboard: trend, HTF bias, signal, last sweep, trade state and statistics
- Alerts: popup / sound / push on new trade signals (optional also on qualifying sweeps).
- Buffers for EAs: 0 = long entry price, 1 = short entry price, 2 = sweep score (+bull / -bear).
- Closed-bar logic: nothing repaints.

## Install

- MT5: copy MT5\TL Liquidity Sweep Pro.ex5 to  File > Open Data Folder > MQL5\Indicators
- MT4: copy MT4\TL Liquidity Sweep Pro.ex4 to  File > Open Data Folder > MQL4\Indicators Refresh the Navigator, drag the indicator on the chart.
- For the YouTube / RoboForex / WhatsApp / Myfxbook buttons tick "Allow DLL imports".

## Settings Tip

Choppy market: raise "Min sweep score" towards 65 and keep "Require CHoCH confirmation" ON.

## Honest Note

about what happens next. The tool grades the setup - it does not remove the risk. Statistics are before spread / commission.

Links: YouTube <https://www.youtube.com/@traderlifestyle> Myfxbook: <https://www.myfxbook.com/community/programming/my-free-eas-indicators-/3376352,1>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
