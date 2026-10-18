<div align="center">

# ⚡ TL POC Reaction Pro

**Trades the reaction candle at heatmap POC zones and targets the current POC.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_POC_Reaction_Pro_XAUUSD_M5_tlprp_shot.png" alt="TL POC Reaction Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL POC Reaction Pro.ex5`](MT5/TL%20POC%20Reaction%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Daily POC zones, automatically.** One volume profile per day from 1-minute bars — the same maths as the LuxAlgo heatmap.
- **Never trades a zone blindly.** It waits for a closed reaction candle or a three-bar reversal at the zone.
- **Targets the current POC** — and only takes trades with RR ≥ 1.5.
- **Confluence filter:** only zones where POCs of different days line up are traded.
- **Full panel** with every POC zone, the open position, the last trade and the last skipped signal with its reason.

## 🧠 Strategy rules

Based on the LuxAlgo short *"This NEW Volume Profile Indicator Is Actually Accurate"* (Precision Market Entropy Heatmap with POC zones, Gold 5m).

**Zones**
- One volume profile per day (D1 anchor) from 1-minute bars, 50 rows. The POC row (highest volume) of each of the last 10 sessions becomes a zone.
- **Red zone above price** = resistance → short setups. **Teal zone below price** = support → long setups.
- Only zones where at least 2 POCs of different days line up (within 0.3 × ATR) are traded — the presenter's best tip. Set **"Min POC zones lining up" = 1** for the plain video rules.

**Entry — only after a closed reaction at the zone**
- A clear reaction candle (rejection wick ≥ 60 % of the candle, or an engulfing candle), **or**
- A three-bar reversal (the middle bar is the extreme, the last bar closes beyond it).
- Price must come from the other side, and the pattern bar must close back outside the zone.

**Exits & limits**

| | Rule |
|---|---|
| **Stop loss** | Beyond the rejection wick / zone edge + 0.3 × ATR(14) |
| **Take profit** | The **current** profile POC (today's POC) |
| **Minimum RR** | A trade is only taken if RR ≥ 1.5 |
| **Limits** | At most 2 trades per zone and direction, one position at a time |

Signals are read from M5 by the EA itself (input **"Signal timeframe"**), so any chart timeframe gives the same trades.

## 🖥️ Dashboard & chart

The panel shows status, the current POC (target), ATR / spread, the open position, today's result, all POC zones (days ago, range, POC volume, buy / sell dominance, confluence, long / short side), the last trade and the last skipped signal with the reason. The **AUTO TRADING** button switches trading on / off. Tooltips can be switched off in the inputs.

The EA sets the dark video chart theme and restores your chart colours when it is removed.

## 📋 Requirements

- Recommended: **XAUUSD** (as in the video), signal timeframe **M5** — the defaults are set up for this.

## 🛠️ Installation

1. In MT5 open **File → Open Data Folder** and copy `TL POC Reaction Pro.ex5` to `MQL5 → Experts`.
2. Refresh the Navigator and drag the EA onto an XAUUSD chart (any timeframe).
3. Enable **"Algo Trading"**.
4. Optional: enable **"Allow DLL imports"** only for the link buttons (YouTube / RoboForex / WhatsApp / Myfxbook).

## 🙏 Credits

Strategy from the LuxAlgo short *"This NEW Volume Profile Indicator Is Actually Accurate"* (Precision Market Entropy Heatmap with POC zones).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
