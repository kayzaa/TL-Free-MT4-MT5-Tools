<!-- auto-generated: remove this line after hand-editing so publish keeps your text -->
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

## What It Does

Hedge-cycle basket engine. Each cycle opens 1 buy plus 2 sell-stop hedges below it. All positions are closed together at one money target (basket TP). If price moves a set distance away from the basket, a follow-up cycle opens with a bigger buy lot (multiplier). Decisions are made on the bar open only.

## Install

- Copy "TL Equilibrium Pro.ex5" to File > Open Data Folder > MQL5 > Experts.
- Restart MT5 or refresh the Navigator.
- Drag it onto a EURUSD H1 chart. Enable Algo Trading.
- Tick "Allow DLL imports" if you want the panel link buttons to work (only used for those buttons).

## Requirements

- HEDGING account (it does not trade on netting accounts, the panel shows a warning).
- Backtested on EURUSD H1 with 5-digit pricing. Other symbols need their own distances.

## Risk

This is a hedge / martingale-style basket. It wins often and in small steps, but it in the tests. Other settings I tried (for example a wider cycle distance) wiped the account in 2024. Test on demo first and only use money you can afford to lose. Past results are no guarantee for the future.

More free tools: <https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4>

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
