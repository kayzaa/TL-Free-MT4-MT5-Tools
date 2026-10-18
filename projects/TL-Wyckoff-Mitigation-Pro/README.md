<div align="center">

# ⚡ TL Wyckoff Mitigation Pro

**Wyckoff distribution schematic + two-candle system: SA → UT / spring → flip → entry, with phase tracker. EA or indicator mode.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_WyckoffMitigationPro_screenshot.png" alt="TL Wyckoff Mitigation Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Wyckoff Mitigation Pro Indicator.ex4`](MT4/TL%20Wyckoff%20Mitigation%20Pro%20Indicator.ex4) |
| **MT4** | [`TL Wyckoff Mitigation Pro.ex4`](MT4/TL%20Wyckoff%20Mitigation%20Pro.ex4) |
| **MT5** | [`TL Wyckoff Mitigation Pro Indicator.ex5`](MT5/TL%20Wyckoff%20Mitigation%20Pro%20Indicator.ex5) |
| **MT5** | [`TL Wyckoff Mitigation Pro.ex5`](MT5/TL%20Wyckoff%20Mitigation%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Wyckoff distribution schematic #2 + the two-candle system (2CS)** turned into clear, rule-based setups.
- **Step-by-step model**: 2CS origin → SA → UT / spring → flip → entry, for sells *and* buys.
- **Phase tracker** in the dashboard shows exactly where the current setup stands.
- **Full trade plan** — entry, stop, mitigation target, partial at the SA level and break-even.
- **EA or indicator** — run the EA in Indicator mode for signals only, or use the pure indicator that never trades.
- **Closed bars only** — no repaint.

## 🧠 Strategy rules

| Step | Rule |
|---|---|
| **2CS origin** | The last opposite candle before the newest leg high / low (inside bars do not count). |
| **SA** | The first **close** through the 2CS origin = sign of weakness (sell) / strength (buy). |
| **UT / SPRING** | After the SA, price runs the high (sell) / low (buy) from before the SA. |
| **FLIP** | A close through the last candle of the UT / spring leg = a new two-candle break → flip zone. |
| **ENTRY** | Limit at the flip zone edge (or middle), or market at the flip close. |
| **STOP** | Beyond the UT / spring + ATR buffer, or fixed points (the video uses 15 NAS points). |
| **TARGET** | The origin of the leg (the mitigation), with a minimum reward / risk filter. |
| **MANAGEMENT** | Partial close (default 50 %) when the SA level runs + stop to break-even; early exit when price closes back beyond the flip zone ("the high runs"). |
| **FILTERS** | Optional higher-timeframe 2CS leg in the trade direction, session hours, direction. |

## 🖥️ Dashboard & chart

- **On the chart:** 2CS origin box, SA / UT / SPRING labels, grey FLIP zone, and a red risk + blue reward box per setup with its outcome in R.
- **Dashboard:** two-candle system status, distribution + accumulation phase tracker (SA → UT → FLIP → ENTRY), trade plan, virtual results of the loaded history (bar OHLC, stop first, no spread), position and alerts.
- **X** closes the dashboard to a pill; drag the header to move it. It automatically avoids other trader.lifestyle panels.

## 📦 Files

| File | Type | Folder |
|---|---|---|
| `TL Wyckoff Mitigation Pro.ex5` | EA (trades) — set **Mode** to Indicator mode for signals only | `MQL5 → Experts` |
| `TL Wyckoff Mitigation Pro Indicator.ex5` | Same model as a pure indicator (never trades) | `MQL5 → Indicators` |
| `TL Wyckoff Mitigation Pro.ex4` | EA (trades) | `MQL4 → Experts` |
| `TL Wyckoff Mitigation Pro Indicator.ex4` | Pure indicator | `MQL4 → Indicators` |

## 🛠️ Installation

1. Open `File → Open Data Folder`.
2. **MT5:** copy the EA to `MQL5 → Experts` and/or the indicator to `MQL5 → Indicators`. **MT4:** copy the EA to `MQL4 → Experts` and/or the indicator to `MQL4 → Indicators`.
3. Refresh the Navigator and drag the EA or the indicator onto a chart.
4. Enable **Allow DLL imports** only if you want the link buttons in the dashboard to work.

## 🙏 Credits

- Built after the public **IMPACT FX** YouTube video *"How to spot mitigation before it happens"* (Wyckoff distribution schematic #2 + the two-candle system). This is an independent build of the rules shown in the video.

## ⚠️ Notes

- The video trades NAS100 on M1 (and 5-second charts). Spread matters a lot on very low timeframes and forex majors — check your symbol and timeframe on demo before going live.
- The virtual results in the dashboard use bar OHLC, stop first and no spread.
- Trading involves high risk.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
