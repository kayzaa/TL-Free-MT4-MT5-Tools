<div align="center">

# ⚡ TL Breakout Reversal Pro

**"All you need to know about trading" as an EA — small losses, running winners, position size = risk / stop.**

![version](https://img.shields.io/badge/version-v1.10-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Breakout_Reversal_Pro_XAUUSD_H1_brp_shot.png" alt="TL Breakout Reversal Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Breakout Reversal Pro.ex4`](MT4/TL%20Breakout%20Reversal%20Pro.ex4) |
| **MT5** | [`TL Breakout Reversal Pro.ex5`](MT5/TL%20Breakout%20Reversal%20Pro.ex5) |

> Compiled build only — source code is not published.

## 💡 The idea

"All you need to know about trading" — as an EA. Nothing else is in it.

- Price either goes up or down. No one knows what will happen next.
- Keep losses small and let winners run.
- **Position size = risk / stop loss.**
- You control the size of your loss (skill), not the size of your win (luck).
- Know when to pick up your chips and cash them in.
- Expectancy = P(win) × average win − P(loss) × average loss. The only part you control is the average loss.

## ✨ Highlights

- **Three choices, nothing more** — WAIT, BREAKOUT or REVERSAL, set via inputs or straight from the dashboard buttons.
- **Previous-bar levels** — trades the high / low of the previous bar (default: the previous **day**), drawn on any chart timeframe.
- **Risk-based sizing** — lots are calculated from the stop distance, so the money at risk stays the same whether the stop is wide or tight.
- **Cost guard** — skips trades where the spread eats too much of the stop.
- **Let winners run** — no fixed target by default; a bar-by-bar trailing stop takes over after +1R.
- **Live dashboard** — position size, spread cost, expectancy of closed trades and a CLOSE ALL button.

## 🧠 Strategy rules

The price action rules (quoted from H. Rearden on Forex Factory) — on every timeframe, price does one of three things:

- breaks out of the high, the low or both of the previous bar,
- does not break out of the previous bar,
- closes above a level (line) or not.

From that come your only three options:

| Option | What happens | Stop loss |
|---|---|---|
| **WAIT** | No new trade (open trades are still managed). | — |
| **BREAKOUT** | Price breaks the previous high → **BUY**; breaks the previous low → **SELL**. | The other end of the previous bar |
| **REVERSAL** | Price makes a new high and comes back below the previous high → **SELL**; makes a new low and comes back above the previous low → **BUY**. | Beyond the new extreme |

### Timeframe

Default is **D1** — the previous day's high / low. It works on any chart timeframe; the lines are drawn on lower charts too. Any timeframe can be set, but the smaller the bars, the more of every stop is eaten by the spread (see the cost guard).

### Trigger

| Trigger | Behaviour |
|---|---|
| **Break of the bar** | The trade opens the moment price breaks the line (tick by tick). |
| **Close beyond line** | Decided at the bar close: closed beyond the line = breakout; broke out but closed back inside = reversal. |

One trade at a time, max. one entry per bar. A close signal that falls into a session break (e.g. gold at the day change) is executed at the first tick after the market opens.

### Position size = risk / stop loss

Risk per trade is set in % of balance or as a fixed amount. The lot size is calculated from the stop distance: wide stop = small size, tight stop = bigger size — the loss stays the same. If even the minimum lot would risk more than twice the allowed amount, the trade is skipped.

### Cost guard (keep losses small)

The spread is part of every loss. If the spread costs more than 10 % of the stop (input, 0 = off), the trade is skipped — a stop that is mostly spread is not a trade. The dashboard shows the spread cost of the next BUY / SELL stop live.

### Let winners run — cash in your chips

No fixed target by default. At every bar close the stop trails behind the lowest low (BUY) / highest high (SELL) of the last 3 bars (input), starting after +1R. An optional take profit can be set as an R multiple, and the dashboard has a **CLOSE ALL** button.

## 🖥️ Dashboard & chart

**Chart:** lines at the previous bar's high / low, plus a mark on every bar:

| Mark | Meaning |
|---|---|
| 🟢 / 🔴 arrow | Broke the previous high / low and closed beyond it (breakout) |
| 🟠 orange arrow | Broke out but closed back inside (reversal) |
| ⚪ grey dot | Inside bar, no breakout |

**Dashboard:** price action of the forming bar, the three option buttons + trigger, next BUY / SELL line, live position size (risk / stop = lots), expectancy of the closed trades, current position and CLOSE ALL. Drag the header to move it; **X** collapses it to a pill, click the pill to reopen.

## 🛠️ Installation

1. **MT5:** copy `MT5/TL Breakout Reversal Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`.
   **MT4:** copy `MT4/TL Breakout Reversal Pro.ex4` to `File → Open Data Folder → MQL4 → Experts`.
2. Refresh the Navigator and drag the EA onto a chart.
3. Allow Algo Trading.
4. The dashboard's link buttons need **"Allow DLL imports"**.
5. Use one magic number per chart.

## 🙏 Credits

Price action rules quoted from **H. Rearden** on Forex Factory.

## ⚠️ Notes

Trading involves a high risk of loss. Test on a demo account first. No profit is promised — no one knows what will happen next.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
