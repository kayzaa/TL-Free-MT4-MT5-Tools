<div align="center">

# ⚡ TL Martingale Calculator Pro

**Plan a martingale / recovery sequence before you trade it — lots, levels and exposure.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Martingale Calculator Pro.ex4`](MT4/TL%20Martingale%20Calculator%20Pro.ex4) |
| **MT5** | [`TL Martingale Calculator Pro.ex5`](MT5/TL%20Martingale%20Calculator%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **See the whole grid before you trade it** — price, lot, total lots, break-even, margin and P/L for every level.
- **Broker-real risk colours** — rows turn yellow, orange or red using your broker's actual margin-call / stop-out levels.
- **A clear verdict** — how many levels your account survives, the estimated stop-out price and the risk : reward.
- **Two modes** — plan a VIRTUAL grid or project the next levels from your LIVE open trades.
- **Live panel settings** — type a value or use − / +, results update on the spot.
- **Plays nicely with others** — it's an indicator, so it runs on the same chart as TL Trade Panel Pro or any EA.

## 🧠 What it calculates

**For every level of a martingale / grid:**

- Price, lot, total lots
- Average (break-even) price and pips back to break-even
- Floating P/L when price reaches the level
- Total margin and margin level %
- Profit if the basket take profit is hit after that level

**For the whole sequence:**

- Margin level at the last level and TP profit
- Estimated **STOP-OUT price** with all levels open
- Loss at an optional hard stop
- Risk : reward
- **Verdict:** how many levels your account survives

**Row colours** (using your broker's real stop-out / margin-call levels):

| Colour | Meaning |
|---|---|
| 🟨 Yellow | Margin call |
| 🟧 Orange | Not enough free margin to open |
| 🟥 Red | Stop-out |

## 🔀 Modes

- **VIRTUAL** — plan a grid from the live price, a typed price or the dragged **START** line.
- **LIVE** — your open trades of the symbol become the first levels (silver lines); the next levels are projected from the last entry and the last lot.

## ⚙️ Key inputs

**Live on the panel** (type a value or use − / +):

| Setting | What it does |
|---|---|
| Direction | BUY or SELL grid |
| Start lot | Lot of the first level |
| Lot multiplier | 2 = classic martingale, 1 = plain grid |
| Lot added per level | Additive martingale |
| Step | Distance between levels in pips |
| Step multiplier | Wider gaps level by level |
| Number of levels | Up to 40 |
| Basket TP | Pips from the average price |
| Hard stop | Stop beyond the last level |

**Inputs:** commission per lot, magic filter for LIVE mode, colours.

## 🖥️ Chart

Level lines with lot labels, a basket TP line, a stop-out line and a hard-stop line.

## 🛠️ Installation

1. Copy the file for your platform:
   - **MT5:** `TL Martingale Calculator Pro.ex5` → **File → Open Data Folder → MQL5 → Indicators**
   - **MT4:** `TL Martingale Calculator Pro.ex4` → **File → Open Data Folder → MQL4 → Indicators**
2. Refresh the Navigator and drag the indicator onto a chart.
3. **"Allow DLL imports"** is only needed for the link buttons.

## ⚠️ Notes

- This is a planning calculator — it places no orders.
- Grid / martingale-style exposure can grow quickly; the stop-out estimate shows where that ends. Test any sequence on demo first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
