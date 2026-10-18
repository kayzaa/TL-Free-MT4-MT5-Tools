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

## ✨ Highlights

- **Liquidity mapped for you** — BSL / SSL lines on unswept swing highs / lows, EQH / EQL clusters tagged automatically.
- **Sweeps marked live** — a wick through a level that closes back on the other side gets an **X** on the wick.
- **0–100 quality score** — every sweep is graded on wick depth, reclaim strength, rejection, volume and level significance.
- **CHoCH confirmation** — by default a signal fires only after a close through the recent minor structure.
- **Full trade plan** — stop beyond the sweep wick, TP1 / TP2 / TP3 at 1 / 2 / 3 × risk, break-even at TP1.
- **Closed-bar logic** — nothing repaints, and EA-ready buffers are included.

## 🧠 How it works

### What it draws

- **BSL / SSL** — dotted lines on unswept swing highs / lows (buy-side / sell-side liquidity).
- **EQH / EQL** — near-identical highs / lows are connected and tagged: stacked stops, a liquidity magnet.
- **Sweep** — a wick through a level plus a close back on the other side, marked with an **X** on the wick.

### Sweep score (0–100)

| Component | Weight |
|---|---|
| Wick depth past the level | 30 % |
| Reclaim strength | 25 % |
| Rejection wick | 15 % |
| Relative volume | 15 % (only) |
| Level significance (age + EQH / EQL) | 15 % |

The HTF bias only nudges the score (± 5) — it never blocks a trade.

### Signal & trade plan

1. Sweep score ≥ **Min sweep score**.
2. Then (default) **CHoCH confirmation**: a close through the recent minor structure within the confirmation window — otherwise the setup quietly expires.
3. Both sides swept on one candle = conflict, nothing fires. One trade at a time.
4. **Stop** just beyond the sweep wick + a small ATR buffer.
5. **TP1 / TP2 / TP3** = 1 / 2 / 3 × risk. At TP1 the stop moves to **break-even**.

## 🖥️ Dashboard & chart

- Dashboard with trend, HTF bias, signal, last sweep, trade state and statistics.
- **Alerts:** popup / sound / push on new trade signals (optionally also on qualifying sweeps).
- **Buffers for EAs:**

| Buffer | Content |
|---|---|
| 0 | Long entry price |
| 1 | Short entry price |
| 2 | Sweep score (+ bull / − bear) |

## ⚙️ Settings tip

Choppy market? Raise **"Min sweep score"** towards 65 and keep **"Require CHoCH confirmation"** ON.

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `MT5\TL Liquidity Sweep Pro.ex5` → **File → Open Data Folder → MQL5 → Indicators**
   - **MT4:** `MT4\TL Liquidity Sweep Pro.ex4` → **File → Open Data Folder → MQL4 → Indicators**
2. Refresh the Navigator and drag the indicator onto the chart.
3. For the YouTube / RoboForex / WhatsApp / Myfxbook buttons, tick **"Allow DLL imports"**.

## ⚠️ Notes

- A sweep score grades the setup — it says nothing certain about what happens next and does not remove the risk.
- Dashboard statistics are before spread / commission.

## 🔗 Links

- [My free EAs & indicators on Myfxbook](https://www.myfxbook.com/community/programming/my-free-eas-indicators-/3376352,1)

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
