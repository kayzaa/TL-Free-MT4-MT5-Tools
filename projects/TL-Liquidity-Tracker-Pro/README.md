<div align="center">

# ⚡ TL Liquidity Tracker Pro

**Liquidity sweep-and-run EA from the "Liquidity Tracker" video, with full multi-column panel.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_Liquidity_Tracker_Pro_shot_H4_prev.png" alt="TL Liquidity Tracker Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT5** | [`TL Liquidity Tracker Pro.ex5`](MT5/TL%20Liquidity%20Tracker%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- 💧 **Every liquidity pool on one chart** — monthly, weekly, daily, swing, equal highs/lows and session ranges.
- 🔄 **Two trade models from the video** — the Liquidity **Sweep** (grab and reverse) and the Liquidity **Run** (break and continue), coded as rules.
- 🌊 **WaveTrend + Volume Explosion** — both sub-window indicators are embedded in the EA.
- ✅ **Setup checklist** — every condition from the video checked live in the panel.
- 🖥️ **Panel that always fits** — liquidity map, mini charts, checklist, trade box, alerts and statistics; splits into 2–3 columns or scales down on small charts.
- 🔓 **No account lock, no broker lock, no expiry** — runs with any broker.

## 🧠 How it works

Built from the video **"How to Find Liquidity & Then Trade It"**. Every setting of the original TradingView indicator was read from the video frame by frame and rebuilt for MT5, plus the two trades shown in the video as rules.

### Part 1 — Liquidity levels (price chart)

| Level | Meaning | Style |
|---|---|---|
| **PMH / PML** | Previous monthly high / low | Pink, width 2 |
| **PWH / PWL** | Previous weekly high / low | Orange, width 2 |
| **PDH / PDL** | Previous daily high / low | Teal |
| **PSH / PSL** | Previous swing high / low (pivot 30 left / 3 right, major swings) | Lime |
| **EQH / EQL** | Equal highs / lows | White dotted, off by default |
| **NYH/NYL, LONH/LONL, ASIAH/ASIAL** | Session ranges, only below H2 | — |

Sessions: New York 09:30–16:00 NY time, London 08:00–16:00 London time, Asia 09:00–15:00 Tokyo time — daylight saving handled automatically. Labels such as "PWH 4697.07" sit in a gap of the line, with equal prices side by side. Older periods are dashed and only drawn over the period they were live. All 7 settings groups of the original (General, Sessions, Swing, Equal highs/lows, Day, Week, Month) are inputs 1–7 with the same defaults.

### Part 2 — WaveTrend (sub-window)

- Blue wave rising = buying pressure, falling = selling pressure.
- Area: **BLUE** = money flowing in, **PURPLE** = money flowing out.
- Dots = momentum change. **Big red dot** above +60 = extreme / overbought. **Big green dot** below -60 = extreme / oversold.

### Volume Explosion (sub-window)

Volume grouped over several bars (you see the trend, not single bars), with a grey inner band and yellow SURGE lines on either side (Bollinger style). Bars through the yellow line = volume explosion (yellow dot). The original formula is not published — this is a rebuild of the behaviour shown in the video.

## 🎯 Strategy rules

When price reaches liquidity it does one of two things:

**1. Liquidity Sweep — grab and reverse** *(video trade #1, gold H4)*

> Level broken → closes back inside within 18 bars → checklist (extreme WaveTrend dot, money flow turned, volume against the break, weak break / Monday, waves turned) → **trigger:** close through the day low (PDL) / day high (PDH) → **stop** above the sweep extreme, **target 2R**.

**2. Liquidity Run — break and continue** *(video trade #2, gold H4)*

> Candle closes through the level → checklist (money flow side and curve, volume through the surge line, Tue–Thu, expansive candles, no extreme dot against it, smaller level already broken) → **entry:** AT THE BREAK (default) with the stop just behind the broken level, or **FVG 50 % LIMIT** (the "line in the sand" from the video) → **target 4R**.

Monday is treated as quiet (no RUN breaks on Monday); Wednesday / Thursday are shown as peak days — both from the video.

## 🔔 Alerts

1. **Approaching Zone** — price within X % (default 0.25 %) of a weekly / monthly level: "a trade is fast approaching".
2. **Zone Broken** — a candle closed through the level.

Popup, sound and push notification, with setup and trade alerts on top.

## 🖥️ Dashboard & chart

Liquidity map (nearest pools above / below, distance in % and ATR), WaveTrend + volume mini charts, the setup checklist, trade box, alerts and statistics. Hover any box for the explanation from the video. On a small chart the panel is split into 2–3 columns or scaled down — nothing is cut off.

## ⚙️ Key inputs

| Input | What it does |
|---|---|
| Trade mode | `OFF` = indicator + alerts only |
| Risk % per trade (default 1 %) | Or fixed lot / lot per balance |
| Max lot, max spread, max trades per week | Exposure limits |
| Break-even, swing trailing, time exit, Friday close | Trade management |
| Settings groups 1–7 | General, Sessions, Swing, Equal highs/lows, Day, Week, Month — same defaults as the original |

- If the minimum lot would risk more than 1.5× your planned risk (very wide stop, small account), the trade is skipped.
- Entries that fall into the gold daily break (market closed) are queued and sent at the reopen.

## 🛠️ Installation

1. Copy `TL Liquidity Tracker Pro.ex5` to `File → Open Data Folder → MQL5 → Experts`. The two sub-window indicators are embedded.
2. `Tools → Options → Expert Advisors`: allow **Algo Trading**. **Allow DLL imports** is only used by the 3 panel buttons to open links.
3. Drag the EA onto a chart. The video trades **GOLD (XAUUSD) on H4**. Want only the indicator + alerts? Set Trade mode = `OFF`.
4. Push alerts to your phone: `Tools → Options → Notifications → MetaQuotes ID`.

## ⚠️ Notes

- MT5 only. Built around gold H4 as in the video; other symbols and timeframes need their own judgement.
- The Volume Explosion formula is a rebuild from the video, as the original is not published.
- Trading involves risk. Test on a demo account first.

## 🙏 Credits

- Strategy and original TradingView indicator: video [How to Find Liquidity & Then Trade It](https://www.youtube.com/watch?v=1tdbd0SFR_8) by the YouTube channel *Bulls, Bears and Backtests*.
- MT5 rebuild, rules and panel: trader.lifestyle.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
