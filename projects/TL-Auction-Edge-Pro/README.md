<div align="center">

# ⚡ TL Auction Edge Pro

**Trade the edges of value like a fund manager — auction market theory with value area, rotations and edge entries.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_AuctionEdgePro_screenshot.png" alt="TL Auction Edge Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Auction Edge Pro Indicator.ex5`](MT5/TL%20Auction%20Edge%20Pro%20Indicator.ex5) |
| **MT5** | [`TL Auction Edge Pro.ex5`](MT5/TL%20Auction%20Edge%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Auction market theory, automated** — the EA reads balance vs. imbalance and trades the edges of value.
- **Value box + volume profile** — 70 % value area with VAH, POC, VAL and the thin areas (LVN) beyond the edges.
- **Scored setups** — every idea gets a 0–100 score; below your minimum the desk does nothing.
- **Risk in R** — one fixed % per idea across all DCA steps, one stop, a winner never becomes a loser.
- **News-aware** — MT5 calendar filter, because new information breaks the balance.
- **Animated trading desk** — auction state, value map, setup radar, trade and risk desk, all in one panel.

## 🧠 The idea (auction market theory)

- Markets are auctions. **BALANCE** = fair value found: price moves sideways, and breakouts **and** breakdowns fail. **IMBALANCE** = trend: the market searches for a new fair value.
- A **value box + volume profile** (70 % value area) marks VAH, POC, VAL and the thin areas (LVN) beyond the edges.
- **Value migration** (higher / lower) and the space between a fast and a slow EMA add context.

## 🎯 Setups

| Setup | Logic |
|---|---|
| **EDGE** | Sell the value area high, buy the value area low of a confirmed balance. |
| **RETURN** | The market comes back to the value it left (fib 50 % confluence). |
| **BREAK** | Optional: an accepted break = price + time (closes outside) + volume. |
| **RE-ENTRY** | Stopped out, but the market reaches the level again and reverses? Enter again (max 2 per idea). |

- **Trigger** — no blind entries: a little selling / buying at the edge is required (rejection, optional volume).
- **Score 0–100** — built from balance, edge, LVN / fib, trigger, EMAs, context, central bank, reward : risk and news. Below the minimum score the desk does nothing.

## 🛡️ Risk management (all in R)

- One idea risks a **fixed %** across **all** DCA steps: the first step at market, DCA limit steps towards the stop, **one** stop for all of them, and an optional add after a fast impulse + slow return (not around news).
- The stop goes where the idea is wrong — beyond the failed breakout / defended swing — and is never widened.
- **SWING plan:** cover the initial risk at the opposite edge (partial close), stop to entry, the runner goes to the next value / x R, then trails behind defended swings once the balance has broken (accepted).
- **SCALP plan:** everything closes at the opposite edge.
- A winner never becomes a loser: stop to entry at +x R.
- **News filter** (MT5 economic calendar).

## 🖥️ Trading desk (animated panel)

- **Auction state** and **value map** (live profile + price).
- **Setup radar** with score rings and checklist.
- **Price / time / volume acceptance**.
- **Trade desk** — DCA steps, invalidation, cover risk, runner.
- **Risk desk**, a virtual **track record** of every idea in the chart history, and a rule carousel.
- **X** closes the desk to a pill, drag the header to move it, hover anything for help.

## 📦 Files

| File | Role |
|---|---|
| `TL Auction Edge Pro.ex5` | The EA — input **"Mode"** switches between EA and Indicator only |
| `TL Auction Edge Pro Indicator.ex5` | Indicator build — never trades |

## 🛠️ Installation

1. In MetaTrader 5 open **File → Open Data Folder**.
2. Copy `TL Auction Edge Pro.ex5` into `MQL5 → Experts` and `TL Auction Edge Pro Indicator.ex5` into `MQL5 → Indicators`.
3. Refresh the Navigator and drag the EA or the indicator onto a chart. For the EA, enable Algo Trading.
4. Enable **"Allow DLL imports"** only if you want the panel's link buttons to work.

## ⚠️ Notes

- Signals are calculated on closed bars only — no repaint.
- The track record is a bar-data simulation including spread, not a full strategy test, and says nothing about future results.
- DCA steps add to a position in the direction of the stop — size the risk per idea carefully.
- Test on a demo account first. Trading involves high risk — only risk money you can afford to lose.

## 🙏 Credits

Built after the live trade of hedge fund trader **Imre Gams** with **Tim Flossbach** (YouTube: "So tradet ein Hedgefonds-Manager WIRKLICH").

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
