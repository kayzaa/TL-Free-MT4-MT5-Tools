<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## Overview

Trade the edges of value like a fund manager. Built after the live trade of hedge fund trader Imre Gams with Tim Flossbach (YouTube: "So tradet ein Hedgefonds-Manager WIRKLICH").

## Files

- **MT5/Experts/TL Auction Edge Pro.ex5** — EA  (input "Mode": EA or Indicator only) MT5/Indicators/TL Auction Edge Pro Indicator.ex5  indicator build (never trades)

## Install

- File -> Open Data Folder -> MQL5 -> copy the files into Experts / Indicators, refresh the Navigator, drag the tool on a chart. Allow "DLL imports" for the link buttons.

## The Idea (auction market theory)

- Markets are auctions. BALANCE = fair value found (sideways, breakouts AND breakdowns fail). IMBALANCE = trend, the market searches a new fair value.
- Value box + volume profile (70 % value area): VAH, POC, VAL, thin areas (LVN) beyond the edges.
- Value migration (higher / lower) and the space between a fast and a slow EMA.

## Setups

- **EDGE** — sell the value area high, buy the value area low of a confirmed balance RETURN    the market comes back to the value it left (fib 50 % confluence) BREAK     optional: accepted break = price + time (closes outside) + volume RE-ENTRY  stopped out? If the market goes up there and reverses - sell again (max 2 per idea) Trigger   no confirmation: a little selling / buying at the edge (rejection, optional volume) Score     0-100 (balance, edge, LVN / fib, trigger, EMAs, context, central bank, reward:risk, news)
  - below the minimum the desk does nothing.

## Risk Management (all in R)

- One idea risks a fixed % over ALL DCA steps: first step at market, DCA limit steps towards the stop, ONE stop for all, optional add after a fast impulse + slow return (no news).
- Stop where the idea is wrong: beyond the failed breakout / defended swing, never widened.
- SWING plan: cover the initial risk at the opposite edge (partial), stop to entry, runner to the next value / x R, trailing behind defended swings once the balance broke (accepted). SCALP plan: everything at the opposite edge.
- A winner never becomes a loser (stop to entry at +x R).
- News filter (MT5 calendar): new information breaks the balance.

## Trading Desk (animated panel)

Auction state, value map (live profile + price), setup radar (score rings + checklist), price / time / volume acceptance, trade desk (DCA steps, invalidation, cover risk, runner), risk desk, track record (virtual, every idea of the history), rule carousel. X closes the desk to a pill, drag the header to move it, hover = help.

## Notes

- Signals on closed bars only - no repaint.
- The track record is a bar-data simulation incl. spread, not a backtest.
- Test on a demo account first. Trading involves high risk - only risk money you can afford to lose.

trader.lifestyle

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
