<div align="center">

# ⚡ TL Candle Based Pro

**Casper C.'s classic "Candle Based EA" (FF thread 332199) rewritten from scratch for MT4 and MT5.**

![version](https://img.shields.io/badge/version-v4.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Candle_Based_Pro_XAUUSD_M5_cbp_shot9.png" alt="TL Candle Based Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Candle Based Pro.ex4`](MT4/TL%20Candle%20Based%20Pro.ex4) |
| **MT5** | [`TL Candle Based Pro.ex5`](MT5/TL%20Candle%20Based%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **The classic, rebuilt from scratch.** Casper C.'s "Candle Based EA" (Forex Factory thread 332199, 2011) — rewritten so that *every* input actually works.
- **Works beyond 5-digit forex.** Forex, JPY pairs (3 digits), gold, silver and indices — all distances are in points of the symbol.
- **Real trade management.** A true break-even, a trailing stop that only starts in profit, and three money-management modes.
- **Safety built in.** Magic number and symbol filter, spread / stop-level / freeze-level / margin checks, state rebuilt after a restart.
- **Full dashboard** with break levels on the chart, tooltips and alerts.
- **MT4 + MT5.**

## 🧠 Strategy rules (unchanged from the original)

| | Condition |
|---|---|
| **BUY** | Price breaks above the **high** of the previous candle |
| **SELL** | Price breaks below the **low** of the previous candle |
| **EXIT a)** | Stop loss / take profit / break-even / trailing stop |
| **EXIT b)** | A break in the opposite direction closes the trade and opens the opposite one |

### 📏 All distances are in points of the symbol

> EURUSD (5 digits): 100 points = 10 pips  ·  Gold (2 digits): 100 points = 1.00 $ = "10 pips"

The original divided by 100000, which was only correct on 5-digit forex — that is gone.

## ⚙️ Key inputs

| Group | What it does |
|---|---|
| **Signal timeframe** | The candle that must be broken (current = chart timeframe) |
| **Buffer** | The break must exceed the high / low by X points (0 = any break) |
| **Break price** | Original (BUY on Ask > high, SELL on Bid < low) or Bid for both |
| **Trade direction** | Both / long only / short only |
| **Close on opposite break** | Exit b) of the system |
| **Entry limit counted** | Per direction (a reversal in the same candle is allowed) or per candle in total (original v1 / v2 behaviour) |
| **Max. new trades / candle** | 1 = original (0 = unlimited) |
| **Max. open positions** | 1 = one trade at a time, more than 1 = stacking like version 3 |
| **Stop loss / take profit** | In points, 0 = none |
| **Break-even** | When the profit reaches the trigger, the stop moves to entry + lock. Once. |
| **Trailing stop** | Starts only when the trade is in profit by the start value (0 = start at the distance, so the stop is at least break-even when it starts), then follows price at the distance with a min. step per modification. Never moves back. |
| **Money management** | Fixed lots / dynamic (lots per X of balance) / risk % of balance, with a max. lots cap |
| **Martingale** (optional, high risk) | Lots × multiplier after every loss in a row; after "max. steps" the cycle restarts at the base lot |
| **Filters** | Max. spread, trading window (server time), max. trades per day, stop new trades after a daily loss of X % of the balance |
| **Display** | Dashboard (auto two columns on small charts, click the header to collapse), break levels of the current candle, tooltips on every element (can be switched off), popup / sound / push alerts |
| **Other** | Auto trading on/off, magic number (one per chart), comment, slippage |

## 🔧 What was fixed vs. the original v1 / v2 / v3

- **Trailing distance** was `TrailingSL / 100000` — only right on 5-digit forex. On gold, 300 became 0.003 $ and the stop was dragged directly behind the price.
- **Trailing started at trade open** (`Bid − SL > TS` was true on the first tick), replacing the initial stop immediately — on the losing side of the entry.
- **"BE" was not a break-even:** it only stopped the trailing once the stop was above entry + 0.001 (a fixed price). No trigger, no move to entry.
- **v3 buffer:** `buffer_value*Point < Ask-Bid*Point` is calculated as Ask − (Bid × Point), which is always bigger — the buffer switched itself off on the first tick.
- **v3 pending orders:** the check compared the lot size with 1 instead of the order count and then deleted every order of the account; pending orders never expired.
- **No magic number / symbol filter:** it closed and modified manual trades and other EAs on all symbols, and `OrdersTotal() == 0` blocked it whenever anything else was open.
- **New-candle flag** was used up before the order result, so a rejected order was never retried in that candle; v2 printed an alert on every tick.
- **DynamicLot** had no lot step / min / max rounding (error 131), and used 0.01 lot per 10 $ in v1 / v2.
- **v3 martingale** detected losses by comparing the balance between ticks — wrong with any other trade, swap or deposit; the max. lot was equity / 1000.
- **Order loops** counted forward while closing (skipping orders), and there was a division by zero at balance 0.

**New safety:** stop level / freeze level checks, skip when the spread is wider than the stop, free margin check, no retry flood on "not enough money", ECN support (stops set after the order), no modifications while the market is closed, and state rebuilt after a restart.

## 🛠️ Installation

1. In your terminal open **File → Open Data Folder**.
2. **MT4:** copy `TL Candle Based Pro.ex4` to `MQL4 → Experts`. **MT5:** copy `TL Candle Based Pro.ex5` to `MQL5 → Experts`.
3. Restart the terminal (or right-click **Refresh** in the Navigator) and drag the EA onto a chart.
4. Tick **"Allow live trading"** (MT4) / **"Allow Algo Trading"** (MT5).
5. Optional: tick **"Allow DLL imports"** only if you want the YouTube / RoboForex / WhatsApp / Myfxbook buttons to open your browser — the EA trades fine without it.

## 🙏 Credits

Original "Candle Based EA" by **Casper C.** — Forex Factory thread 332199 (2011).

## ⚠️ Notes

- The optional martingale multiplies lot size after losses — exposure can grow quickly. Keep it off unless you understand the risk, and test on demo first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
