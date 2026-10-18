<div align="center">

# ⚡ TL H1 Sweep Reversal Pro

**H1 liquidity sweep followed by an M5 reversal entry — Silkysilv's method automated.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_H1SweepReversalPro_chart.png" alt="TL H1 Sweep Reversal Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL H1 Sweep Reversal Pro.ex4`](MT4/TL%20H1%20Sweep%20Reversal%20Pro.ex4) |
| **MT5** | [`TL H1 Sweep Reversal Pro.ex5`](MT5/TL%20H1%20Sweep%20Reversal%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Sweep → reversal, fully automated** — the previous H1 high / low gets swept on M5, a close back through the sweep candle triggers the trade.
- **Clear targets** — stop beyond the sweep candle, target at the opposite side of the H1 range.
- **Set and forget** — open trades run until SL or TP; the EA never moves or closes them.
- **Any chart, any symbol** — the EA always reads M5 candles internally.
- **Visual audit trail** — H1 levels, sweep dots, trigger lines, signal arrows and risk / reward boxes on the chart.
- **Session and spread filters** — trade London open to New York close by default.

## 🧠 Strategy rules

At every new H1 candle, **RefHigh / RefLow** = high / low of the last completed H1 candle, and everything resets.

| | SELL | BUY (exact mirror) |
|---|---|---|
| **Sweep candle** | The **first** M5 candle of the hour that trades above RefHigh (a later, higher candle does **not** replace it) | The first M5 candle of the hour that trades below RefLow |
| **Trigger** | A later M5 candle of the same hour closes below the **low** of the sweep candle | A later M5 candle closes above the **high** of the sweep candle |
| **Entry** | Sell at market when that candle closes | Buy at market when that candle closes |
| **Stop loss** | Sweep candle high + spread + buffer (pips) | Sweep candle low − spread − buffer |
| **Take profit** | RefLow | RefHigh |

- **No confirmation before the hour ends** → the setup is cancelled.
- **No management:** open trades keep running until SL or TP — they are never moved or closed by the EA.
- **One trade at a time** by default.
- **Already at target?** If price is already at or beyond the target when the signal comes, the trade is skipped.

## 🖥️ Dashboard & chart

| Element | Meaning |
|---|---|
| **Grey lines** | RefHigh / RefLow of every hour |
| **Dots** | Sweep candles |
| **Dotted line** | Trigger level (low / high of the sweep candle) |
| **Arrows** | Signals — including the ones skipped by a filter |
| **Boxes** | Risk / reward of every trade the EA would take (green = target, red = stop, result in R) |
| **Dashboard** | Current levels, state of both setups, risk, position, results |

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Trade direction | Long + short / long only / short only |
| Confirmation inside range | Extra filter (default off): the confirmation close must also be back inside the H1 range |
| SL buffer (pips) | Default 1.0 pip (pip = 10 points on 5- and 3-digit symbols) |
| Add spread to SL | Default on |
| Max. open trades | 1 = one at a time; more = pyramiding (several trades at once) |
| Lot mode | Risk % of balance (default 5 %) or fixed lots |
| Session filter | Default 10:00–24:00 **server** time = London open (08:00 London) to New York close (17:00 New York) on GMT+2/+3 brokers, which most MT4 / MT5 brokers use. Adjust if your broker uses another time zone |
| Max. spread (pips) | 0 = off |
| Other | Magic number, comment, slippage, alerts (popup / sound / push), dashboard, tooltips on / off |

## 🛠️ Installation

1. Choose **File → Open Data Folder**.
2. Copy the file for your platform:
   - **MT4:** `TL H1 Sweep Reversal Pro.ex4` → **MQL4 → Experts**
   - **MT5:** `TL H1 Sweep Reversal Pro.ex5` → **MQL5 → Experts**
3. Restart the terminal, or right-click **Expert Advisors** in the Navigator → **Refresh**.
4. Drag the EA onto any chart and allow algo trading.
5. Tick **Allow DLL imports** only if you want the YouTube / RoboForex / WhatsApp / Forex Factory buttons to open links — the EA trades without it.

> **Strategy Tester:** use the M5 chart (the MT4 tester requires M5).

## 🙏 Credits

- Strategy: **Silkysilv** on Forex Factory, posts #111 / #112.

## ⚠️ Notes

- The default of 5 % risk per trade is very aggressive — consider lowering it, and test on a demo account first. No profit promise.
- Session times are in broker server time; check your broker's time zone.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
