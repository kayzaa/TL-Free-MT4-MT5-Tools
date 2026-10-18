<div align="center">

# ⚡ TL Confluence Zones Pro

**Smart-money zones that are scored, not just painted: 9 confluence factors → 0–100 score, plan only after confirmation.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_ConfluenceZonesPro_screenshot.png" alt="TL Confluence Zones Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Confluence Zones Pro.ex4`](MT4/TL%20Confluence%20Zones%20Pro.ex4) |
| **MT5** | [`TL Confluence Zones Pro.ex5`](MT5/TL%20Confluence%20Zones%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Zones that are scored, not just painted** — 9 independent confluence factors add up to a 0–100 score, every factor visible in the panel.
- **Plans only after confirmation** — a zone arms on the touch; entry, invalidation and targets appear only when a candle closes back out of it.
- **Full smart-money toolkit** — order blocks (chart + higher timeframe), fair value gaps, liquidity pools, BOS / CHoCH, HTF key levels and an EMA ribbon.
- **Market map dashboard** — 15M / 1H / 4H / 1D structure, bias, nearest liquidity and a built-in position sizer.
- **No repaint** — everything runs on closed bars; plans never move after they appear.
- **Nothing hidden** — every historical plan stays on the chart with its outcome in R.
- **EA-ready** — iCustom buffers for the ribbon, plans, score and trends.

## 🧠 How it works

| Stage | What happens |
|---|---|
| **WATCHZONE** | The strongest zone close to price gets a blue frame — attention, no trade yet. |
| **CONFLUENCE** | 9 independent factors → a score from 0 to 100, every factor shown in the panel. |
| **BUY / SELL ZONE** | Order blocks from the chart **and** the higher timeframe arm when price touches them. |
| **CONFIRMATION** | A candle closes back out of the zone → **ENTRY, INVALIDATION, TARGET**. |

### The 9 confluence factors (max 100)

| Factor | Points |
|---|---|
| HTF trend in the zone's direction | 20 (neutral 8) |
| Premium / discount of the HTF range | 15 (half in: 8) |
| HTF key level inside the zone | 15 |
| Fair value gap from the displacement | 10 |
| Liquidity grab when the zone was built | 10 |
| Relative volume of the displacement | 10 (1.5×) / 5 (1.0×) |
| Fresh zone (first touch) | 10 / 4 (second touch) |
| EMA ribbon stacked | 5 + 5 |
| Higher-timeframe zone / stacked on one | 10 |

### No repaint

Everything is calculated on closed bars. Higher-timeframe data is only used after that HTF candle has closed. Plans never move after they appear.

## 🖥️ Dashboard & chart

**On the chart**

- **Buy / sell zones** (order blocks) with volume and strength %, named MAIN BUY, DEEP BUY, MAIN SELL, PREMIUM SELL; higher-timeframe zones get a thick frame.
- **Fair value gaps** with fill %, removed once filled.
- **Liquidity pools**: equal highs (BSL — seller stops) and equal lows (SSL — buyer stops), xN = number of equal swings, "liquidity pocket" for 2+, sweeps marked.
- **BOS / CHoCH** labels on the chart timeframe and the higher timeframe.
- **HTF key levels** (blue): higher-timeframe swings, previous day / week high and low.
- **EMA ribbon** 8 / 21 / 50 / 200.
- **Every historical plan** with its outcome (+R / −1R) — nothing hidden.
- **The current plan**: ENTRY, INVALIDATION, TARGET 1 (nearest liquidity), TARGET 2.

**Dashboard** — drag it anywhere; X shrinks it to a small pill, click the pill to open it again.

- **Market map**: 15M / 1H / 4H / 1D structure, candle pattern, flow, EMA ribbon, decision (bias), nearest liquidity above / below in pips.
- **Watchzone**: score ring plus all 9 factors with their points.
- **Trade plan + position sizer** (risk % → lots for the stop distance).
- **Layer buttons**: zones, FVG, liquidity, levels, BOS / CHoCH, ribbon, signals.
- **Statistics box** that replays every plan of the loaded history bar by bar (stop first when stop and target are hit in the same bar, no spread / commission) — so you can judge the tool on facts, not screenshots.
- Automatically avoids other trader.lifestyle panels on the same chart.

## 🤖 For EAs (iCustom buffers)

| Buffer | Content |
|---|---|
| 0–3 | EMA ribbon |
| 4 | Buy plan entry |
| 5 | Sell plan entry |
| 6 | Plan stop |
| 7 | Plan target 1 |
| 8 | Best watchzone score (last closed bar) |
| 9 | Chart trend (+1 / −1) |
| 10 | HTF trend (+1 / −1) |

## 🛠️ Installation

1. Open `File → Open Data Folder`.
2. **MT5:** copy `TL Confluence Zones Pro.ex5` to `MQL5 → Indicators`. **MT4:** copy `TL Confluence Zones Pro.ex4` to `MQL4 → Indicators`.
3. Refresh the Navigator and drag the indicator onto a chart.
4. Tick **Allow DLL imports** only if you want the link buttons to open your browser.

## ⚠️ Notes

- The statistics box ignores spread and commission and assumes the stop is hit first when both levels fall in one bar.
- Zones and confluence are an analysis framework — not a guarantee. Not financial advice.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
