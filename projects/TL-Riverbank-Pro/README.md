<div align="center">

# ⚡ TL Riverbank Pro

**Inthebox's "Waiting at the Riverbank" gold method — session, HTF level, sweep, BOS and engulf entry.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Expert_Advisor-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_RiverbankPro_FF.png" alt="TL Riverbank Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Riverbank Pro.ex4`](MT4/TL%20Riverbank%20Pro.ex4) |
| **MT5** | [`TL Riverbank Pro.ex5`](MT5/TL%20Riverbank%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Inthebox's "Waiting at the Riverbank" method** as a full EA for MT4 and MT5 — written from scratch by trader.lifestyle.
- **6-condition SOP, graded A / B / C** — session, HTF key level, premium / discount, liquidity sweep, break of structure and the right-shoulder sweep.
- **Engulf entry** — enters as price comes back out of the impulse leg's engulf zone (breakout or half / half entry as options).
- **Structured management** — stop at the head, HTF targets, 50 % partial at +1R with break-even, optional ATR trailing.
- **Guards built in** — session limit, daily trade cap, daily loss limit, spread filter, high-impact news filter and Friday stop.
- **Animated quant panel** with the 6 conditions as traffic lights and the live phase of the setup.

## 🐊 The idea — "let price come to us, we don't chase it"

A crocodile waits at the riverbank where the animals come to drink. The EA waits at the **HTF key level** during a market session and only acts when the **LTF Riverbank pattern** confirms it.

## 🧠 Strategy rules

### The 6 conditions (SOP from post #1)

**3 main conditions**

| Condition | Rule |
|---|---|
| Market session | Entry within the first 3 h after the Tokyo, London or New York open (DST-aware, broker GMT auto) |
| HTF key level | The head or the right shoulder touches an HTF level: H4 / D1 engulf zones, Malaysian SnR (A / V close-open levels incl. flipped ones), previous day / week high + low, day + week open |
| Premium / discount | Buy below / sell above 50 % of the leg or of today's range |

**3 conditions of the LTF confirmation entry (the Riverbank pattern)**

| Condition | Rule |
|---|---|
| Liquidity sweep | Price trades beyond a fractal swing point and closes back inside = the **HEAD** |
| Break of structure | A candle **closes** beyond the last swing point before the head |
| Sweep beyond the BOS | The pullback comes back beyond the broken level = the **RIGHT SHOULDER** |

**Grades:** A = 6, B = 5, C = 4 conditions. The minimum grade is an input.

### Entry

- **Default:** after the pullback into the engulf zone of the impulse leg, the first candle that closes back out of the engulf (thread: *"candle that closes above the engulf when coming out of engulf"*).
- **Options:** breakout entry at the BOS close, or "both" (half / half).
- **Trend filter:** price above / below the 200 EMA (Inthebox's simple model), or the higher-timeframe EMA, or HTF HH / HL structure.

### Stop, target, management

- **Stop** at the HEAD (default) or at the right shoulder, + ATR buffer.
- **Target:** next HTF level / swing (1.2 – 3 R), fixed R:R or fixed pips.
- **Partial close 50 % at +1R + break-even** (*"40 pips = 1st partial TP, if you don't take it, put BE on"*) — optional ATR trailing.
- Optional exit after 1 or 2 candle closes beyond the engulf (thread SL rule).
- Max 1 trade per session, max trades per day, daily loss limit, spread filter, high-impact news filter (MT5 calendar, live), Friday stop.

### Design choices in this version

- **Entry timeframe input, default M15** (Inthebox: *"experiment to use m15 only"*) — on M5 the pattern fires much more often and is more exposed to noise and spread.
- **Stop at the head** instead of the right shoulder by default.
- **Equal risk per trade** by default — the PDF's 3 / 2 / 1 unit sizing by grade is available as an option (OFF).
- Only the 3 nearest HTF levels above / below are drawn (*"at most 3 HTF SnR"*).
- News filter, daily guard, broker clock / DST handling for the sessions.

## 🖥️ Dashboard & chart

- **Riverbank SOP:** trend pill, the 6 conditions as traffic lights with their values, grade gauge C / B / A, head / BOS / engulf levels, and the phase (WAITING AT THE RIVERBANK / SWEPT / BOS / IN THE ENGULF / ENTRY).
- **HTF key levels:** the 2 nearest above + below with distance in ATR; session clock Tokyo / London / New York with countdown; news.
- Signal track record on your chart history, auto trading on / off, close EA trades, daily guard, live statistics.
- **X** closes the panel to a pill; drag the header to move it.
- **Chart:** session boxes (like the thread's charts), LS / BOS marks, engulf zone boxes, HTF levels, 200 EMA, entry arrows with R result tags.

## 🛠️ Installation

1. Open `File → Open Data Folder`.
   - **MT4:** copy `TL Riverbank Pro.ex4` into `MQL4 → Experts`.
   - **MT5:** copy `TL Riverbank Pro.ex5` into `MQL5 → Experts`.
2. Refresh the Navigator and attach the EA to **XAUUSD** (any chart timeframe — the entry timeframe is an input, default M15).
3. Allow algo trading.
4. **Broker clock:** "Auto" assumes a New-York-close broker (GMT+2 winter / GMT+3 summer, e.g. RoboForex, IC Markets). Other brokers: set the offset manually. The session clock in the panel shows the server times.
5. Optional: **Allow DLL imports** is only needed for the link buttons (YouTube / RoboForex / WhatsApp / Forex Factory).

## 🙏 Credits

- Trading method by **Inthebox** — Forex Factory thread [Waiting at the Riverbank](https://www.forexfactory.com/thread/1359156-waiting-at-the-riverband). The full thread, his PDF "Waiting at the Riverbank", the 91-page "Rules" PDF and his later "simplified 3 steps model" were studied for this EA. Big thanks to Inthebox for sharing it for free.
- The code itself is independently written by trader.lifestyle.

## ⚠️ Notes

- The signal track record and R tags on the chart are a visual review of your chart history, not a promise. Test on a demo account first.

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
