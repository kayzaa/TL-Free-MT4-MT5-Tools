<div align="center">

# ⚡ TL Gold Levels Liquidity Pro

**GLD gamma levels, bond (ZN) context and a live spread-liquidity monitor for gold.**

![version](https://img.shields.io/badge/version-v1.00-00e5ff?style=for-the-badge) ![type](https://img.shields.io/badge/type-Indicator-ffc400?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT4-0d1117?style=for-the-badge) ![platform](https://img.shields.io/badge/platform-MT5-0d1117?style=for-the-badge) ![price](https://img.shields.io/badge/price-FREE-2ea043?style=for-the-badge) ![license](https://img.shields.io/badge/license-no_lock_·_no_expiry-8957e5?style=for-the-badge)

</div>

<p align="center"><img src="screenshots/TL_GoldLevelsLiquidityPro_screenshot.png" alt="TL Gold Levels Liquidity Pro" width="100%"></p>

## 📥 Download

| Platform | File |
|---|---|
| **MT4** | [`TL Gold Levels Liquidity Pro.ex4`](MT4/TL%20Gold%20Levels%20Liquidity%20Pro.ex4) |
| **MT5** | [`TL Gold Levels Liquidity Pro.ex5`](MT5/TL%20Gold%20Levels%20Liquidity%20Pro.ex5) |

> Compiled build only — source code is not published.

## ✨ Highlights

- **Options-market levels on your gold chart** — call wall, put wall, gamma flip, max pain and key strikes from the free GLD option chain.
- **Bond-market direction filter** — 10Y T-Note (ZN) trend decides LONG ONLY, SHORT ONLY or no entries.
- **Live liquidity monitor** — spots moments when the bid/ask spread blows out and liquidity is pulled from the book.
- **Thread-style entries** — liquidity sweep + liquidity event + bond direction + EMA 20 reclaim → BUY / SELL arrow, on closed candles.
- **Manual levels** — type in your own levels, e.g. the ones posted in the thread.
- **EA-ready buffers** for iCustom.

## 🧠 How it works

### 1. Levels from the options market

Dealer gamma of the **GLD option chain** (CBOE, 15 min delayed, free), mapped to gold with the XAU / GLD ratio at the GLD close:

| Level | Definition | Meaning |
|---|---|---|
| **CALL WALL** | Largest call gamma above price | Resistance / pin |
| **PUT WALL** | Largest put gamma below price | Support |
| **GAMMA FLIP** | Price where total dealer gamma changes sign | Above = positive gamma (mean reversion), below = negative gamma (trend) |
| **MAX PAIN** | Strike with the smallest option payout of the main expiry | — |
| **Key strikes** | Strikes with the largest net gamma | — |

You can also type your own levels (inputs `Manual: ...`).

### 2. Direction from the bond market (10Y T-Note)

Bonds up = yields down = gold up. Source: your broker's bond symbol (auto-detected) or the 10Y T-Note futures **ZN=F** (5 min) from the web.

| Bond state | Rule | Bias |
|---|---|---|
| **BONDS UP** | EMA 20 above EMA 50 + bullish break of structure | LONG ONLY |
| **BONDS DOWN** | Mirror image | SHORT ONLY |
| **MIXED** | — | No entries (input) |

### 3. Liquidity monitor (the "liquid indicator")

Measures the bid/ask spread tick by tick. When the spread stays above **2× its average** (last 100 ticks) for **30 seconds**, liquidity was pulled from the book → **orange dot** on the chart. It is not directional — use it at your levels. MT5 rebuilds the last 72 h from the tick history; MT4 records live (saved to a file, survives restarts).

### 4. Entry (thread rules)

> **Liquidity taken** (H1 swing high / low or previous day high / low) **+ liquidity event** around the sweep **+ bond direction + candle closes back over / under EMA 20** → BUY / SELL arrow.
>
> **Stop:** beyond the sweep (or beyond EMA 50). **Target:** next liquidity level (min 1R, else 2R).

Signals use closed candles only — no repaint. The thread trades M1 for entries.

## 🖥️ Dashboard & chart

Click **X** to close the dashboard to a small pill, click the pill to open it again, and drag the header or the pill to move it. Hover over any section for an explanation (tooltips can be switched off).

## 🔌 Buffers (for EAs / iCustom)

| Buffer | Content |
|---|---|
| 0 | EMA fast |
| 1 | EMA mid |
| 2 | EMA slow |
| 3 | Buy signal (entry price) |
| 4 | Sell signal |
| 5 | Liquidity event (price) |
| 6 | Bias (+1 long only, −1 short only, 2 both, 0 none) |

## 📋 Requirements

- An **XAUUSD** chart.
- **"Allow DLL imports"** (Common tab) is **required** — for the web data (GLD option chain, ZN futures) and the buttons. WebRequest is not allowed inside indicators, so the indicator downloads via Windows' wininet.dll — no URL whitelist needed.

## 🛠️ Installation

1. **MT5:** copy `TL Gold Levels Liquidity Pro.ex5` to `File → Open Data Folder → MQL5 → Indicators`.
   **MT4:** copy `TL Gold Levels Liquidity Pro.ex4` to `File → Open Data Folder → MQL4 → Indicators`.
2. Restart the terminal, or right-click the Navigator → **Refresh**.
3. Drag the indicator onto an XAUUSD chart.
4. Tick **"Allow DLL imports"** on the Common tab.

## ⚠️ Notes

- The thread uses gold **futures** options (QuikStrike). GLD is the free public proxy he also uses on expiry days — levels can differ.
- Spread behaviour depends on your broker: if you see too many or too few orange dots, adjust **"Liquidity: trigger"** / **"spread must stay above ... seconds"**.
- No indicator is a trading system — test on demo first. No profit is promised.

## 🙏 Credits

Inspired by the Forex Factory thread **"Gold Levels"** by **Asylum1**. This is an independent rebuild by trader.lifestyle — not the original indicator (its calculation was never published).

---

<div align="center">

**Built by [trader.lifestyle](https://www.youtube.com/@traderlifestyle)** · [Forex Factory thread](https://www.forexfactory.com/thread/1428808-free-eas-indicators-strategies-mt4) · [YouTube](https://www.youtube.com/@traderlifestyle) · [WhatsApp](https://wa.me/18585003724)

### ✨ CREATED WITH [INDICATORGENIUS.COM](https://indicatorgenius.com) ✨

<sub>Trading involves substantial risk. This tool is provided free and as-is for education. Test on a demo account first. Past behaviour is no guarantee of future results.</sub>

</div>
