<div align="center">

# ⚡ TL Smart Bots Pro

**Rebuild of the "smart bots" reel, read frame by frame: signal circle on XAUUSD M1, then market order + 3 stop orders pyramiding with momentum.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Smart_Bots_Pro_XAUUSD_M1_sbp_shot.png" alt="TL Smart Bots Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Smart Bots Pro.ex4`](MT4/TL%20Smart%20Bots%20Pro.ex4) |
| **MT5** | [`TL Smart Bots Pro.ex5`](MT5/TL%20Smart%20Bots%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **A silent reel, decoded** — the "Power of automatic trading bot / smart bots" reel has no voice and no description; every rule was read from the screen recording frame by frame.
- **Momentum pyramid basket** — 1 market order + 3 stop orders in trade direction.
- **Individual TP and SL per leg** — the reel's values are the defaults.
- **Break-even on the last leg** after 3 take profits.
- **No-repaint signal circles** — confirmed higher lows / lower highs, or manual baskets via buttons.
- **Animated dashboard** — basket table, live ladder and one-click BUY / SELL / CLOSE / AUTO.

## 🧠 Strategy rules

> A green (buy) or red (sell) **circle** appears on the XAUUSD M1 chart → a **basket** starts.

- **Basket:** 1 order at market + 3 **stop orders** in trade direction (buy: 3 buy stops above, sell: 3 sell stops below) — a pyramid on momentum.
- **Every leg has its own take profit and stop loss** (price distances from the reel, used as defaults):

| Leg | TP distance | SL distance |
|---|---|---|
| Market | 4.651 | 3.535 |
| Stop 1 | 3.043 | 4.435 |
| Stop 2 | 3.537 | 4.649 |
| Stop 3 | 2.310 | 4.899 |

- **Break-even:** after 3 take profits, the last open leg moves to break-even (+0.031).

### Signal circles

The reel does not say what draws the circles, so the EA offers three modes:

| Mode | Signal |
|---|---|
| **Structure** (default) | A confirmed **higher low** = BUY circle, a confirmed **lower high** = SELL circle. Swing point = extreme of 2 bars left / 4 bars right, confirmed 4 bars later — no repaint. |
| **Every swing point** | Every confirmed swing point draws a circle |
| **MANUAL** | Only the BUY / SELL basket buttons |

## 🖥️ Dashboard & chart

- Animated panel: drag the header, **X** closes it to a pill, click the pill to reopen.
- Signal, a basket table with every leg (entry / TP / SL / state), live ladder and statistics.
- One-click **BUY / SELL / CLOSE / AUTO** buttons.
- Tooltips can be switched off.
- Link buttons YouTube / RoboForex / WhatsApp / Forex Factory need "Allow DLL imports".

## 🛠️ Installation

1. In MetaTrader open **File → Open Data Folder**.
2. **MT4:** copy `TL Smart Bots Pro.ex4` into `MQL4 → Experts`. **MT5:** copy `TL Smart Bots Pro.ex5` into `MQL5 → Experts`.
3. Refresh the Navigator and drag the EA onto **XAUUSD M1**.
4. Allow Algo Trading. Tick **"Allow DLL imports"** only if you want the link buttons to work.

## ⚠️ Notes

- The reel used a lot size far too large for its account — **do not copy the lot size** of the reel. Start small.
- A basket of four legs adds exposure quickly as the stop orders fill. Test on a demo account first.
- The TP / SL distances are gold price distances from the reel; other symbols need their own values.

## 🙏 Credits

Rebuild of the Facebook reel "Power of automatic trading bot / smart bots" from the page **"Agibt" / AGI Bot AI** (XAUUSD M1, 26 Sep 2025).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
