<div align="center">

# ⚡ TL Hurst Envelope Pro

**7iv3's Hurst cycle method: centred-MA envelopes, Murrey math levels and Gann 1×1 in one EA.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Hurst_Envelope_Pro_XAUUSD_M5_hep_shot.png" alt="TL Hurst Envelope Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Hurst Envelope Pro.ex4`](MT4/TL%20Hurst%20Envelope%20Pro.ex4) |
| **MT5** | [`TL Hurst Envelope Pro.ex5`](MT5/TL%20Hurst%20Envelope%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **7iv3's method, automated** — built on the Forex Factory thread "Analysis and Trading based on Envelopes, Waves, Cycles".
- **Hurst centred MAs** — 32 / 64 / 128 / 256 / 512 with fixed-width envelopes (edge band / mid band).
- **Murrey Math + Gann** — octave 0/8 … 8/8 plus 1×1 and 2×1 angles in Murrey units.
- **Three switchable setups** — 1×1 Break, Edge Band and Mid Band / 2×1 Pullback.
- **No lookahead** — only closed bars are used; the estimated right end of each CMA is drawn dotted.
- **Split exits** — every setup opens two orders: half takes target 1, the rest runs to target 2 with the stop at break-even.

## 🧩 The building blocks

- **J.M. Hurst centred moving averages** 32 / 64 / 128 / 256 / 512 with fixed-width envelopes (edge band / mid band).
- **Murrey Math octave** 0/8 … 8/8.
- **Gann 1×1 and 2×1 angles** in Murrey units (1/8 of price per 1/8 of the frame).

## 🧠 Strategy rules

Each setup can be switched on / off — **by default only S1 is on**.

> **S1 — 1×1 BREAK (7iv3 core)**
> A swing low at 0/8–2/8 (or outside the 128 envelope). A bar closes above the descending 1×1 angle **and** the VTL ("action signal"). The EA waits for the retest of the broken 1×1 / 50 % of the new move and buys. Targets: 6/8 and 7/8. Optional (off by default): exit when price closes back below the ascending 2×1. Short = mirror.

> **S2 — EDGE BAND (Hurst)**
> In a flat (cyclic) market: a bar outside the 128 envelope, the next bar closes back inside → trade back to the CMA (mid band).

> **S3 — MID BAND / 2×1 PULLBACK**
> 3+ CMAs point in one direction. Pullback to the 2×1 angle / 50 % of the move → targets: the high of the move and the focal-point doubling.

**Trade handling**

- Every setup is opened as **two orders**: half closes at target 1, the other half runs to target 2 with the stop at break-even.
- **H1 filter ("reverb"):** trades only in the direction of the H1 CMA 128.

## 🔍 No lookahead

Centred moving averages need future bars — every indicator that draws them repaints. This EA only uses **closed bars**. The missing right end is estimated on every bar (default: truncated TMA = "LWMA bridge" of Terry Pascoe; alternatives: shift 16 of parisboy, or linear). The estimated part is drawn **dotted** on the chart.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Risk per setup | Risk as % of balance |
| Min. / max. stop | Stop limits in 1/8 of the Murrey octave |
| Min. reward / risk | Minimum reward : risk ratio |
| Envelope mode | Auto % / CW points / octave |
| Murrey frame | Frame size (0 = auto) |
| H1 filter | Trade only in the direction of the H1 CMA 128 |
| Cycle filter | Optional cycle filter |
| Trading window | Trading time window |
| Max. setups | Maximum number of setups |

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `TL Hurst Envelope Pro.ex5` → **File → Open Data Folder → MQL5 → Experts**
   - **MT4:** `TL Hurst Envelope Pro.ex4` → **File → Open Data Folder → MQL4 → Experts**
2. Refresh the Navigator and drag the EA onto a chart (recommended: **XAUUSD or BTCUSD, M5**).
3. Tick **"Allow Algo Trading"** (MT4: **"Allow live trading"**).
4. **"Allow DLL imports"** is only needed for the link buttons on the dashboard.

## ⚠️ Notes

- The **price part** of 7iv3's method is automated faithfully. The **timing part** (astronomy, cycle composites) cannot be automated.
- S2 and S3 are **off by default**. Treat the EA as a study / signal tool first and run it on a demo account before going live.
- Free edition — no lock, no expiry. Trading involves high risk; there is no profit promise.

## 🙏 Credits

- Method: **7iv3** in the Forex Factory thread [Analysis and Trading based on Envelopes, Waves, Cycles](https://www.forexfactory.com/thread/709088-analysis-and-trading-based-on-envelopes-waves-cycles) (started by **parisboy**, indicators by **Terry Pascoe**).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
