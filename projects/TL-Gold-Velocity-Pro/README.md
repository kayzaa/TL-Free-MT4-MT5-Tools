<div align="center">

# ⚡ TL Gold Velocity Pro

**Catch fast gold bursts and ride the move — velocity detection with a live speed gauge.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Gold_Velocity_Pro_gvp_panel_compact_preview.png" alt="TL Gold Velocity Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Gold Velocity Pro.ex5`](MT5/TL%20Gold%20Velocity%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Burst detection, tick by tick** — measures how far gold moved inside a window *and* how fast it is moving right now.
- **Two playbooks** — **RIDE** jumps on the burst, **REBOUND** waits for exhaustion and trades the bounce.
- **Tick-precise exits** — hard SL at the broker plus a trailing stop, with SL / TP re-anchored to the real fill price.
- **Ready-made presets** — Sniper, Balanced, Scalper, FF-Original, Rebound or full Manual control.
- **Greed Shield** — daily target, daily loss stop, max trades per day and a pause after a losing streak.
- **Intel layer** — liquidity sweep check, news score, DXY, FED rate, MACD, Bollinger, volume and RSI combined into one bias score.

## 💡 The idea

Built from a Forex Factory request:

> "Catch FAST movement and jump on the train while it lasts — a drop or rise of ~10 $ with an acceleration of 1 $ or more per second, TP 2–5 $, SL 2 $."

On top of that, the EA adds the **rebound** idea (catch the bounce after the hype), the **"second tool"** (news scoring, DXY, FED rate, MACD, BB, volume, RSI) and a **Greed Shield** that stops trading once the day's goal is reached.

## 🧠 How it works

| Term | Meaning |
|---|---|
| **MOVE** | Net price move inside a window (e.g. 15 $ within 30 s) |
| **SPEED** | $ per second over the last second (e.g. ≥ 1 $/s) |
| **BURST** | MOVE and SPEED in the same direction |

- **RIDE mode** — enter **with** the burst (market order).
- **REBOUND mode** — wait until the burst is exhausted (speed drops below X % of its peak **and** price comes back X $ from the extreme), then trade the bounce **against** the burst.
- **Exit** — hard SL at the broker + tick-precise trailing stop (+ optional TP, break-even and time exit). SL / TP are re-anchored to the real fill price, because bursts slip.

## 🎯 Presets

| Preset | Settings |
|---|---|
| **SNIPER** (default) | 15 $ in 30 s, 1 $/s, SL 10 $, trailing from +2 $ (distance 1 $), no fixed TP, max spread 1.50 $ |
| **BALANCED** | 10 $ in 20 s, SL 5 $, trailing 0.5 / 0.5, 07–23 server time |
| **SCALPER** | 8 $ in 30 s, 0.5 $/s, SL 5 $, trailing 1 / 0.5, 07–23 |
| **FF-ORIGINAL** | The original request 1:1 — 10 $ / 60 s / 1 $/s, TP 3 $, SL 2 $ |
| **REBOUND** | 10 $ burst in 30 s, bounce after exhaustion, TP 8 / SL 4 |
| **MANUAL** | Set every value from input groups 1–4 yourself |

## 🛡️ Greed Shield (group 5)

- **Daily target** (default 5 %) → close everything, done for the day.
- **Daily loss stop** (5 %), max trades per day, pause after N losses in a row.
- **Goal tracker** in the panel: 100 $ → 100,000 $ at X % per day.

## 🔭 Intel (group 6b) — "the second tool"

- **Liquidation sweep:** the burst must take out the high / low of the last X minutes.
- **News score** (live only, MQL5 calendar): for every USD high / medium event, the EA learns from one year of calendar history how many $ gold moved per sigma of surprise (actual vs. forecast). After a release it shows the expected gold reaction; optional filter "trade only in news-score direction". Report: `MQL5\Files\gvp_newsscore.csv`.
- **DXY** (real symbol or synthetic from EURUSD / USDJPY / GBPUSD / USDCAD / USDSEK / USDCHF), **FED rate decision** from the calendar, **MACD**, **Bollinger**, **volume**, **RSI**.
- Everything combined into a **BIAS SCORE** from −100 to +100 (+ = gold up), usable as an optional filter.
- **News mode:** OFF / ONLY inside the news window / AVOID news.

## 🛠️ Installation

1. Copy `TL Gold Velocity Pro.ex5` into **File → Open Data Folder → MQL5 → Experts**.
2. Restart MT5 or right-click **Expert Advisors → Refresh** in the Navigator.
3. Drag the EA onto an **XAUUSD** chart (any timeframe, M1 recommended).
4. Enable **Algo Trading**. For the panel buttons, allow DLL imports.

## 📋 Requirements

- Symbol: **XAUUSD**.
- A **VPS close to your broker's server** is recommended — burst trading is latency-sensitive.
- The news score uses the MQL5 economic calendar and works in live trading only.

## ⚠️ Notes

- Bursts move fast: slippage and spread spikes are part of the game. SL / TP are re-anchored to the real fill, but fills can still differ from the trigger price.
- Dollar distances are built for gold; other symbols would need their own distances.
- Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
