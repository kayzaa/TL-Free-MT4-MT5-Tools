<div align="center">

# ⚡ TL Equilibrium Pro

**Hedge-cycle basket engine: buy + sell-stop hedges, one basket money target, follow-up cycles by distance.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_EquilibriumPro_Panel.png" alt="TL Equilibrium Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Equilibrium Pro.ex5`](MT5/TL%20Equilibrium%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Hedge-cycle basket engine** — every cycle pairs a buy with two sell-stop hedges below it.
- **One money target** — all positions of the basket close together at a single basket TP.
- **Follow-up cycles by distance** — when price moves a set distance away from the basket, a new cycle opens with a bigger buy lot (multiplier).
- **Bar-open decisions** — the engine only acts on the open of a new bar.
- **Built-in panel** with a warning if the account type is not supported.

## 🧠 Strategy rules

> **Cycle:** open 1 buy + 2 sell-stop hedges below it.
> **Exit:** close all positions together when the basket reaches the money target (basket TP).
> **Follow-up:** if price moves the set cycle distance away from the basket, open the next cycle with the buy lot multiplied.
> **Timing:** all decisions are made on the bar open only.

## 📋 Requirements

- **Hedging account** — the EA does not trade on netting accounts (the panel shows a warning).
- Built for **EURUSD H1** with 5-digit pricing. Other symbols need their own distances.

## 🛠️ Installation

1. In MT5 open `File → Open Data Folder → MQL5 → Experts` and copy `TL Equilibrium Pro.ex5` there.
2. Restart MT5 or refresh the Navigator.
3. Drag the EA onto a **EURUSD H1** chart and enable **Algo Trading**.
4. Optional: tick **Allow DLL imports** — only used for the panel link buttons.

## ⚠️ Notes

- This is a **hedge / martingale-style basket**: the lot grows with every follow-up cycle, so exposure can build up quickly when price keeps moving away. The cycle distance is a critical setting — changing it changes the risk profile a lot.
- Test on a demo account first and only use money you can afford to lose.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
