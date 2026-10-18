<div align="center">

# ⚡ TL Trap Arsenal Quant

**156 trap trading tools in ONE animated quant dashboard — every tool can be switched on and off.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Trap_Arsenal_Quant_sheet_00.png" alt="TL Trap Arsenal Quant" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Trap Arsenal Quant.ex4`](MT4/TL%20Trap%20Arsenal%20Quant.ex4) |
| **MT5** | [`TL Trap Arsenal Quant.ex5`](MT5/TL%20Trap%20Arsenal%20Quant.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **A full trap-trading arsenal in one animated dashboard** — every tool can be switched on and off, by input or live in the panel.
- **58 trap detectors** on closed candles (no repaint) — from SFPs and turtle soup to Judas swings, CISD and Bollinger head fakes.
- **Liquidity map** — equal highs / lows, unswept swing liquidity, previous day / week / month levels, sessions, pivots, heatmap and more.
- **TRAP EDGE LAB** — runs every detector over the loaded history so you can see how each one behaved.
- **Scanner + risk tools** — MTF trap matrix, multi-symbol scanner, anti stop-hunt stop calculator, prop guard and a 2-click trade panel.
- **Optional auto trader "Trend Trap"** — trades liquidity sweep traps only in the direction of the trend.

## 🧠 How it works

| Module | What's inside |
|---|---|
| **Liquidity** | Equal highs / lows ($$$ pools), unswept swing liquidity (BSL / SSL), PDH / PDL, PWH / PWL, PMH / PML, round numbers, Asian range, session highs / lows, opening range, opens, pivots / Camarilla, 3-touch trendlines, stop cluster zones, liquidity heatmap, liquidity voids, obvious triple tops / bottoms. |
| **Trap detectors** (58, closed candles) | SFP, key level sweeps, equal H/L raids, turtle soup (+1), bull / bear traps, range fakeouts, PDH / PDL fakeouts, stop-hunt spikes, fakey, hikkake, Wyckoff spring / upthrust, failed auction (80 % rule), ORB trap, double sweep, pivot fakeout, trendline + round number fakeouts, sweep + MSS, inducement, inverse FVG, Judas swing, candle range theory, CISD, sweep → FVG, SMT divergence, pin bar / engulfing after sweep, outside + two / three bar reversals, trapped traders (Brooks), H2 / L2, gap & trap, absorption, effort vs result, VSA, low-volume breakouts, delta / OBV divergence, RSI / hidden / MACD / stochastic divergence, failure swings, CCI false breaks, MACD zero fakeouts, divergence traps, Bollinger head fake, band re-entry, Keltner fakeout, z-score stretch, ATR spike reversal, news spike traps. |
| **TRAP EDGE LAB** | Every detector is run over the loaded history, with the stop placed beyond the trap extreme. |
| **Scanner** | MTF trap matrix M5..D1, multi-symbol trap scanner, session sweep statistics, stop-hunt heatmap, breakout quality, crowding, fear / greed proxy, retail sentiment (manual), trap confluence. |
| **Risk** | Anti stop-hunt stop calculator, position size, stop placement check for open trades, anti-trap checklist, trap time lock, prop guard, account + journal, trade panel (2-click), trade manager, hidden stop. |
| **Alerts** | Trap alerts, liquidity approach, level cross, line alerts, spread, Telegram, screenshots. |

## 🤖 Auto trader — Trend Trap

On by default (needs **Algo Trading** enabled). Liquidity sweep traps — SFP, key level sweep, equal H/L raid, stop-hunt spike, turtle soup and round number fakeout — are traded **only in the direction of the trend** (close + EMA50 vs EMA200 of the chart timeframe):

> **LONG:** a bear trap in an uptrend.
> **SHORT:** a bull trap in a downtrend.

| Rule | Setting |
|---|---|
| Initial stop | Behind the trap, at least 2.5 ATR |
| Exit | Chandelier trailing stop 6 ATR, no fixed target |
| Positions | One at a time |
| Risk | 0.5 % per position |
| Market | Gold only, M15 or higher (inputs) |
| Small accounts | When 0.5 % risk would need less than the minimum lot, the EA uses the minimum lot of 0.01 as long as that risks at most 2.5 % (inputs "Small account"); otherwise it skips the signal. |

Every skipped signal is written to the Experts log with the reason. Switch the auto trader off in the inputs if you only want the analysis tools.

## 🖥️ Dashboard & chart

- Click a **category** on the left; **MODULES** opens the on / off switches.
- **X** closes the panel to a pill; drag the header to move it.
- Hover anything for an explanation (tooltips can be switched off).

## 🛠️ Installation

1. Open `File → Open Data Folder`. **MT5:** copy `TL Trap Arsenal Quant.ex5` to `MQL5 → Experts`. **MT4:** copy `TL Trap Arsenal Quant.ex4` to `MQL4 → Experts`.
2. Restart the terminal or refresh the Navigator, then drag it onto a chart.
3. Enable **Allow DLL imports** only for the link buttons, and **Algo Trading** only if you use the trade panel or the auto trader.

## ⚠️ Notes

- The auto trader is **on by default** — turn it off in the inputs if you only want analysis.
- It is built for gold on M15 or higher; other symbols and lower timeframes behave differently and are sensitive to trading costs. Test on a demo account first.
- Statistics in the panel are historical and no promise of future results.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
