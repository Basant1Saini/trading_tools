# 🎯 Trading Strategies Collection — Pine Script v5 (25 Strategies)

## Sab Strategies Ek Nazar Mein

| # | Strategy | Style | Timeframe | Best For | Risk Level | Example Stock |
|---|----------|-------|-----------|----------|------------|---------------|
| 1 | [ORB](1_ORB/) | Intraday Breakout | 5m–15m | Opening range breakout | Medium | Reliance |
| 2 | [MTF](2_MTF/) | Multi-Timeframe | 15m–1H | Higher TF trend + lower TF entry | High | TCS |
| 3 | [RSI Extremes](3_RSI_Extremes/) | Mean Reversion | 5m–Daily | Overbought/oversold reversals | Medium | HDFC Bank |
| 4 | [Slow & Steady](4_Slow_and_Steady/) | Position/Swing | Daily–Weekly | Long-term EMA crossovers | Low | Infosys |
| 5 | [Strong Trending](5_Strong_Trending/) | Trend Following | 15m–Daily | ADX strong trends | Medium | Adani Enterprises |
| 6 | [VWAP Bounce](6_VWAP_Bounce/) | Intraday | 1m–15m | Institutional level bounces | Medium | ICICI Bank |
| 7 | [Scalper](7_Scalper/) | Scalping | 1m–5m | Quick in-out trades | Very High | Tata Motors |
| 8 | [Bollinger Squeeze](8_Bollinger_Squeeze/) | Volatility Breakout | 15m–Daily | Low vol → explosive breakout | Medium-High | Bajaj Finance |
| 9 | [Ichimoku Cloud](9_Ichimoku_Cloud/) | Swing/Positional | 1H–Weekly | Multi-confirmation trend | Medium | Tata Steel |
| 10 | [Fibonacci Pullback](10_Fibonacci_Pullback/) | Swing | 1H–Daily | Golden zone pullback entry | Medium | SBI |
| 11 | [Pivot Points](11_Pivot_Points/) | S/R Trading | 5m–1H | Classic S/R bounce/breakout | Medium | Nifty 50 |
| 12 | [Supertrend](12_Supertrend/) | Trend Following | 5m–Daily | Dynamic trailing stops | Low-Medium | Wipro |
| 13 | [Donchian Channel](13_Donchian_Channel/) | Position Trading | Daily–Weekly | Turtle system breakouts | Medium-High | ITC |
| 14 | [MACD Divergence](14_MACD_Divergence/) | Reversal/Continuation | 15m–Daily | Divergence-based reversals | Medium | Maruti Suzuki |
| 15 | [London Breakout](15_London_Breakout/) | Forex Session | 5m–30m | Asian range → London breakout | High | USD/INR |
| 16 | [Gap and Go](16_Gap_and_Go/) | Intraday Momentum | 5m–15m | Opening gap continuation | Medium-High | HCL Tech |
| 17 | [Heikin Ashi Trend](17_Heikin_Ashi_Trend/) | Swing/Trend | 1H–Daily | Smoothed candle trend following | Low-Medium | L&T |
| 18 | [Inside Bar Breakout](18_Inside_Bar_Breakout/) | Price Action | 1H–Daily | Candle pattern breakout | Medium | Sun Pharma |
| 19 | [EMA Ribbon](19_EMA_Ribbon/) | Trend Following | 1H–Weekly | 6-EMA visual trend alignment | Medium | Asian Paints |
| 20 | [Stochastic RSI](20_Stochastic_RSI/) | Momentum | 15m–4H | Precise OB/OS timing | Medium-High | Kotak Bank |
| 21 | [Chandelier Exit](21_Chandelier_Exit/) | Trailing Stop | Daily–Weekly | ATR-based trend riding | Medium | Titan |
| 22 | [Parabolic SAR](22_Parabolic_SAR/) | Trend/Reversal | 15m–Daily | Dot-based stop and reverse | Medium | Bharti Airtel |
| 23 | [Volume Spike Reversal](23_Volume_Spike_Reversal/) | Reversal | 1H–Daily | Smart money volume detection | High | Power Grid |
| 24 | [Double EMA Crossover](24_Double_EMA_Crossover/) | Classic Swing | 1H–Daily | Golden/death cross | Low | M&M |
| 25 | [NR7 Range Breakout](25_NR7_Range_Breakout/) | Breakout | 1H–Daily | Narrowest range compression | Medium | Dr Reddy's |

---

## 📊 MASTER DECISION FLOWCHART — Kaunsi Strategy Choose Karein?

```
                              ╔═══════════╗
                              ║   START   ║
                              ╚═════╤═════╝
                                    │
                    Tum kya trade karte ho?
                   ╱         │          ╲
              STOCKS     INDICES      FOREX
                 │          │            │
                 │       Nifty/BN?      ✅ #15 London Breakout
                 │          │
                 │     Intraday ya Swing?
                 │       ╱        ╲
                 │   INTRADAY    SWING
                 │      │          │
                 │   ✅ #11       ✅ #9 Ichimoku
                 │   Pivot Points
                 │
        ─────────┘
                 │
        Tumhara TRADING STYLE kya hai?
         ╱       │        │         ╲
     SCALPING  INTRADAY  SWING   POSITIONAL
        │        │        │         │
        │        │        │     Patience hai?
        │        │        │      ╱       ╲
        │        │        │    YES       NO
        │        │        │     │         │
        │        │        │  ✅ #13     ✅ #4
        │        │        │  Donchian   Slow & Steady
        │        │        │
        │        │     Kya approach chahiye?
        │        │    ╱     │      │       ╲
        │        │ PULLBACK TREND  REVERSAL PRICE
        │        │   │    FOLLOW    │     ACTION
        │        │ ✅#10    │     ✅#14    │
        │        │ Fib      │     MACD   Pattern?
        │        │          │     Div    ╱     ╲
        │        │    Complex ya      ✅#18  ✅#25
        │        │    Simple?         Inside  NR7
        │        │     ╱      ╲       Bar
        │        │  COMPLEX  SIMPLE
        │        │    │        │
        │        │  ✅#9    ✅#12
        │        │  Ichimoku Supertrend
        │        │
        │     Kya market condition hai?
        │    ╱      │       │        ╲
        │ TREND   RANGE  VOLATILE   GAP
        │  ING    BOUND  BREAKOUT   OPEN
        │   │       │       │        │
        │   │    ✅#3    ✅#8     ✅#16
        │   │    RSI     Bollinger Gap &
        │   │    Extremes Squeeze   Go
        │   │
        │  Kaunsa intraday approach?
        │  ╱     │      │       ╲
        │ ORB  VWAP  MULTI-TF  SMOOTH
        │  │     │      │        │
        │✅#1  ✅#6   ✅#2    ✅#17
        │ ORB   VWAP   MTF    Heikin
        │       Bounce         Ashi
        │
     Fast execution + tight spread?
        ╱          ╲
      YES          NO
       │            │
    ✅ #7       ⚠️ Scalping avoid karo
    Scalper     #6 VWAP ya #1 ORB better

    ─── TRAILING STOP SYSTEMS ───
        ╱          ╲
      DOTS       LINES
       │            │
     ✅#22       ✅#21
     Parabolic   Chandelier
     SAR         Exit

    ─── INDICATOR BASED ───
     ╱        │         ╲
   VISUAL  MOMENTUM   CLASSIC
     │        │          │
   ✅#19    ✅#20      ✅#24
   EMA      Stoch      Double EMA
   Ribbon   RSI        Crossover

    ─── SPECIAL ───
    Vol spike + reversal? → ✅ #23 Volume Spike Reversal
```

---

## 📈 MARKET CONDITION MATRIX — Kaunsi Condition Mein Kaunsi Strategy?

```
╔══════════════════════════════════════════════════════════════════════════╗
║                    MARKET CONDITION vs STRATEGY                        ║
╠════════════════╦═══════╦═══════╦══════════╦══════════╦════════╦════════╣
║  Strategy      ║STRONG ║ WEAK  ║ SIDEWAYS ║VOLATILE  ║ GAP    ║ LOW   ║
║                ║ TREND ║ TREND ║ RANGE    ║BREAKOUT  ║ OPEN   ║ VOL   ║
╠════════════════╬═══════╬═══════╬══════════╬══════════╬════════╬════════╣
║ #1  ORB        ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ⚠️   ║  ❌   ║
║ #2  MTF        ║  ✅   ║  ✅   ║    ⚠️    ║   ✅     ║  ⚠️   ║  ⚠️   ║
║ #3  RSI Ext    ║  ❌   ║  ✅   ║    ✅    ║   ⚠️     ║  ❌   ║  ✅   ║
║ #4  Slow       ║  ✅   ║  ⚠️   ║    ❌    ║   ⚠️     ║  ⚠️   ║  ✅   ║
║ #5  Strong Tr  ║  ✅   ║  ❌   ║    ❌    ║   ✅     ║  ⚠️   ║  ❌   ║
║ #6  VWAP       ║  ✅   ║  ✅   ║    ✅    ║   ⚠️     ║  ⚠️   ║  ❌   ║
║ #7  Scalper    ║  ✅   ║  ✅   ║    ⚠️    ║   ✅     ║  ✅   ║  ❌   ║
║ #8  BB Squeeze ║  ⚠️   ║  ⚠️   ║    ✅    ║   ✅     ║  ❌   ║  ✅   ║
║ #9  Ichimoku   ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ⚠️   ║  ⚠️   ║
║ #10 Fib Pull   ║  ✅   ║  ✅   ║    ❌    ║   ⚠️     ║  ❌   ║  ✅   ║
║ #11 Pivot Pts  ║  ✅   ║  ✅   ║    ✅    ║   ✅     ║  ✅   ║  ⚠️   ║
║ #12 Supertrend ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ⚠️   ║  ❌   ║
║ #13 Donchian   ║  ✅   ║  ❌   ║    ❌    ║   ✅     ║  ⚠️   ║  ⚠️   ║
║ #14 MACD Div   ║  ⚠️   ║  ✅   ║    ✅    ║   ⚠️     ║  ❌   ║  ✅   ║
║ #15 London BO  ║  ✅   ║  ⚠️   ║    ⚠️    ║   ✅     ║  ✅   ║  ❌   ║
║ #16 Gap & Go   ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ✅   ║  ❌   ║
║ #17 Heikin Ash ║  ✅   ║  ⚠️   ║    ❌    ║   ⚠️     ║  ⚠️   ║  ✅   ║
║ #18 Inside Bar ║  ✅   ║  ✅   ║    ✅    ║   ✅     ║  ❌   ║  ✅   ║
║ #19 EMA Ribbon ║  ✅   ║  ❌   ║    ❌    ║   ⚠️     ║  ⚠️   ║  ⚠️   ║
║ #20 Stoch RSI  ║  ⚠️   ║  ✅   ║    ✅    ║   ⚠️     ║  ❌   ║  ✅   ║
║ #21 Chandelier ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ⚠️   ║  ⚠️   ║
║ #22 Parabolic  ║  ✅   ║  ⚠️   ║    ❌    ║   ✅     ║  ⚠️   ║  ❌   ║
║ #23 Vol Spike  ║  ❌   ║  ✅   ║    ✅    ║   ✅     ║  ✅   ║  ❌   ║
║ #24 Dbl EMA    ║  ✅   ║  ⚠️   ║    ❌    ║   ⚠️     ║  ⚠️   ║  ✅   ║
║ #25 NR7        ║  ⚠️   ║  ⚠️   ║    ✅    ║   ✅     ║  ❌   ║  ✅   ║
╚════════════════╩═══════╩═══════╩══════════╩══════════╩════════╩════════╝
  ✅ = Best Fit    ⚠️ = Use Caution    ❌ = Avoid
```

---

## ⏱️ TIMEFRAME SUITABILITY CHART — Kaunsa Timeframe Best Hai?

```
╔══════════════════════════════════════════════════════════════════════════╗
║ Strategy         │ 1m │ 5m │15m │ 1H │ 4H │ Day│ Wk │ BEST TF       ║
╠══════════════════╪════╪════╪════╪════╪════╪════╪════╪═══════════════════╣
║ #1  ORB          │    │ ★★ │ ★★ │    │    │    │    │ 5m (Intraday)  ║
║ #2  MTF          │    │    │ ★★ │ ★★ │    │    │    │ 15m + 1H combo ║
║ #3  RSI Extremes │    │ ★  │ ★★ │ ★★ │ ★  │ ★  │    │ 15m–1H        ║
║ #4  Slow&Steady  │    │    │    │    │    │ ★★ │ ★★ │ Daily          ║
║ #5  Strong Trend │    │    │ ★  │ ★★ │ ★★ │ ★  │    │ 1H            ║
║ #6  VWAP Bounce  │ ★  │ ★★ │ ★★ │    │    │    │    │ 5m            ║
║ #7  Scalper      │ ★★ │ ★★ │    │    │    │    │    │ 1m–3m         ║
║ #8  BB Squeeze   │    │    │ ★  │ ★★ │ ★★ │ ★  │    │ 1H–4H        ║
║ #9  Ichimoku     │    │    │    │ ★  │ ★★ │ ★★ │ ★  │ 4H–Daily      ║
║ #10 Fib Pullback │    │    │    │ ★★ │ ★★ │ ★  │    │ 1H–4H        ║
║ #11 Pivot Points │    │ ★★ │ ★★ │ ★  │    │    │    │ 5m–15m        ║
║ #12 Supertrend   │    │ ★  │ ★★ │ ★★ │ ★  │ ★  │    │ 15m–1H       ║
║ #13 Donchian     │    │    │    │    │    │ ★★ │ ★★ │ Daily–Weekly   ║
║ #14 MACD Diverg  │    │    │ ★  │ ★★ │ ★★ │ ★  │    │ 1H–4H        ║
║ #15 London BO    │    │ ★★ │ ★★ │    │    │    │    │ 15m           ║
║ #16 Gap & Go     │    │ ★★ │ ★★ │    │    │    │    │ 5m            ║
║ #17 Heikin Ashi  │    │    │    │ ★★ │ ★★ │ ★  │    │ 1H–4H        ║
║ #18 Inside Bar   │    │    │    │ ★  │ ★★ │ ★★ │    │ 4H–Daily      ║
║ #19 EMA Ribbon   │    │    │    │ ★  │ ★★ │ ★★ │ ★  │ 4H–Daily      ║
║ #20 Stoch RSI    │    │    │ ★★ │ ★★ │ ★  │    │    │ 15m–1H       ║
║ #21 Chandelier   │    │    │    │    │ ★  │ ★★ │ ★★ │ Daily–Weekly  ║
║ #22 Parabolic    │    │    │ ★  │ ★★ │ ★★ │ ★  │    │ 1H–4H        ║
║ #23 Vol Spike    │    │    │    │ ★  │ ★★ │ ★★ │    │ 4H–Daily      ║
║ #24 Dbl EMA      │    │    │    │ ★  │ ★★ │ ★★ │    │ 4H–Daily      ║
║ #25 NR7          │    │    │    │ ★  │ ★★ │ ★★ │    │ 4H–Daily      ║
╚══════════════════╧════╧════╧════╧════╧════╧════╧════╧═══════════════════╝
  ★★ = Ideal    ★ = Usable    (blank) = Not Recommended
```

---

## 📉 RISK vs REWARD PROFILE — Strategy Personality Samjho

```
  HIGH REWARD ▲
              │
              │   #7 Scalper          #13 Donchian
              │    (High Risk,         (Med Risk,
              │     High Reward)        High Reward)
              │
              │       #8 BB Squeeze      #2 MTF
              │
              │  #16 Gap&Go    #23 Vol Spike   #15 London BO
              │
              │      #1 ORB    #5 Strong Tr    #9 Ichimoku
              │
              │   #25 NR7    #10 Fib   #18 Inside   #21 Chandlr
              │
              │  #20 StochRSI  #14 MACD   #22 SAR   #19 Ribbon
              │
              │      #3 RSI     #6 VWAP    #11 Pivot   #12 Super
              │
              │          #24 Dbl EMA    #17 Heikin Ashi
              │
              │              #4 Slow & Steady
              │                (Low Risk, Steady)
              └──────────────────────────────────────────────► RISK
            LOW                                             HIGH
```

---

## 🕐 TRADE HOLDING PERIOD CHART

```
╔═══════════════════════════════════════════════════════════════════╗
║ SECONDS  │ MINUTES  │ HOURS    │ DAYS     │ WEEKS    │ MONTHS   ║
║ (1-60s)  │ (1-60m)  │ (1-8H)  │ (1-5D)   │ (1-4W)   │ (1-6M)  ║
╠══════════╪══════════╪══════════╪══════════╪══════════╪══════════╣
║          │ #7       │ #1 ORB   │ #5 Str   │ #4 Slow  │ #13     ║
║          │ Scalper  │ #6 VWAP  │ #9 Ichi  │ #13 Don  │ Donch   ║
║          │          │ #11 Pvt  │ #10 Fib  │ #21 Chan │         ║
║          │          │ #15 Ldn  │ #12 Sup  │ #19 Ribn │         ║
║          │          │ #16 Gap  │ #17 HA   │          │         ║
║          │          │ #20 StR  │ #18 IB   │          │         ║
║          │          │          │ #22 SAR  │          │         ║
║          │          │          │ #24 EMA  │          │         ║
║          │          │          │ #25 NR7  │          │         ║
║          │          │          │ #14 MACD │          │         ║
║          │          │          │ #23 Vol  │          │         ║
║          │          │          │ #8 BB Sq │          │         ║
╠══════════╧══════════╧══════════╧══════════╧══════════╧══════════╣
║ ◄── ACTIVE MONITORING ZARURI ────────── SET & CHECK ──────────► ║
╚═════════════════════════════════════════════════════════════════╝
```

---

## 🎯 TRADE FREQUENCY CHART — Kitne Signals Milte Hain?

```
╔═══════════════════════════════════════════════════════════════════╗
║ FREQUENCY     │ Strategies                                      ║
╠═══════════════╪═════════════════════════════════════════════════╣
║               │                                                 ║
║ BAHUT ZYADA   │ #7  Scalper ████████████████████ (20-50/day)    ║
║ (20+ / day)   │                                                 ║
║               │                                                 ║
║ ZYADA         │ #1  ORB     ████████████████ (5-15/day)         ║
║ (5-15 / day)  │ #6  VWAP    ████████████████                    ║
║               │ #11 Pivot   ███████████████                     ║
║               │ #15 London  ██████████████ (session based)      ║
║               │ #16 Gap&Go  ██████████████ (morning only)       ║
║               │                                                 ║
║ MODERATE      │ #2  MTF     ██████████ (3-8/day)                ║
║ (3-8 / day)   │ #3  RSI     ██████████                          ║
║               │ #5  Strong  █████████                           ║
║               │ #12 Super   █████████                           ║
║               │ #20 StRSI   █████████                           ║
║               │ #22 SAR     ████████                            ║
║               │                                                 ║
║ KAM           │ #8  BB Sq   ██████ (1-3/day or less)            ║
║ (1-3 / day)   │ #10 Fib     ██████                              ║
║               │ #14 MACD    ██████                              ║
║               │ #17 HA      █████                               ║
║               │ #18 IBar    █████                               ║
║               │ #24 DblEMA  █████                               ║
║               │ #25 NR7     ████                                ║
║               │                                                 ║
║ BAHUT KAM     │ #4  Slow    ███ (1-3/week)                      ║
║ (Weekly)      │ #9  Ichi    ███                                 ║
║               │ #13 Donch   ██                                  ║
║               │ #19 Ribbon  ██                                  ║
║               │ #21 Chand   ██                                  ║
║               │ #23 VolSpk  ██                                  ║
╚═══════════════╧═════════════════════════════════════════════════╝
  NOTE: Frequency depends on timeframe. Ye typical values hain.
  Lower timeframe pe zyada signals milenge.
```

---

## 🧩 INSTRUMENT SUITABILITY — Kahan Use Karein?

```
╔════════════════════╦═════════╦═════════╦═════════╦══════════╦═════════╗
║ Strategy           ║ LARGE   ║ MID/    ║ INDEX   ║ FOREX    ║ CRYPTO  ║
║                    ║ CAP     ║ SMALL   ║ (Nifty) ║ (USD/INR)║         ║
╠════════════════════╬═════════╬═════════╬═════════╬══════════╬═════════╣
║ #1  ORB            ║   ✅    ║   ✅    ║   ✅    ║    ⚠️    ║   ✅    ║
║ #2  MTF            ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #3  RSI Extremes   ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ✅    ║
║ #4  Slow & Steady  ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ⚠️    ║
║ #5  Strong Trend   ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #6  VWAP Bounce    ║   ✅    ║   ⚠️    ║   ✅    ║    ❌    ║   ⚠️    ║
║ #7  Scalper        ║   ✅    ║   ❌    ║   ✅    ║    ✅    ║   ✅    ║
║ #8  BB Squeeze     ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #9  Ichimoku       ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ✅    ║
║ #10 Fib Pullback   ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #11 Pivot Points   ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ✅    ║
║ #12 Supertrend     ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #13 Donchian       ║   ✅    ║   ❌    ║   ✅    ║    ✅    ║   ⚠️    ║
║ #14 MACD Diverg    ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #15 London BO      ║   ❌    ║   ❌    ║   ⚠️    ║    ✅    ║   ⚠️    ║
║ #16 Gap & Go       ║   ✅    ║   ✅    ║   ✅    ║    ❌    ║   ✅    ║
║ #17 Heikin Ashi    ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #18 Inside Bar     ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #19 EMA Ribbon     ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ✅    ║
║ #20 Stoch RSI      ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #21 Chandelier     ║   ✅    ║   ⚠️    ║   ✅    ║    ✅    ║   ✅    ║
║ #22 Parabolic SAR  ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #23 Vol Spike      ║   ✅    ║   ⚠️    ║   ✅    ║    ⚠️    ║   ⚠️    ║
║ #24 Dbl EMA Cross  ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
║ #25 NR7 Breakout   ║   ✅    ║   ✅    ║   ✅    ║    ✅    ║   ✅    ║
╚════════════════════╩═════════╩═════════╩═════════╩══════════╩═════════╝
  ✅ = Excellent    ⚠️ = Caution (low liquidity/spread issues)    ❌ = Avoid

  💡 Large Cap = Reliance, TCS, HDFC Bank, Infosys, ICICI Bank
     Mid/Small = Tata Elxsi, Dixon, Deepak Nitrite, IRCTC, Polycab
     Index     = Nifty 50, Bank Nifty, Nifty IT, Sensex
```

---

## 🔗 STRATEGY COMBO CHART — Strategies Ko Saath Mein Use Karo

```
╔═══════════════════════════════════════════════════════════════════════╗
║                    POWERFUL STRATEGY COMBINATIONS                    ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  COMBO 1: "Trend Confirmation Stack"                                ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #5 Strong  │───►│ #12 Super  │───►│ #21 Chand  │                ║
║  │ Trending   │    │ trend      │    │ Exit       │                ║
║  │ (Identify) │    │ (Enter)    │    │ (Trail)    │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 Pehle #5 se trend confirm karo, #12 se entry lo,               ║
║     #21 se trailing stop lagao                                      ║
║                                                                     ║
║  COMBO 2: "Reversal Hunter"                                        ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #23 Vol    │───►│ #3 RSI     │───►│ #14 MACD   │                ║
║  │ Spike      │    │ Extreme    │    │ Divergence │                ║
║  │ (Alert)    │    │ (Confirm)  │    │ (Validate) │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 Volume spike dikhe → RSI extreme check → MACD divergence       ║
║     confirm kare toh hi entry                                       ║
║                                                                     ║
║  COMBO 3: "Breakout Master"                                        ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #8 BB      │───►│ #25 NR7    │───►│ #1 ORB     │                ║
║  │ Squeeze    │    │ Narrow     │    │ Breakout   │                ║
║  │ (Setup)    │    │ (Trigger)  │    │ (Execute)  │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 BB squeeze detect karo → NR7 bar aaye → ORB style              ║
║     breakout trade karo                                             ║
║                                                                     ║
║  COMBO 4: "Intraday Pro"                                           ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #6 VWAP    │───►│ #11 Pivot  │───►│ #20 Stoch  │                ║
║  │ Bounce     │    │ Points     │    │ RSI        │                ║
║  │ (S/R Level)│    │ (Target)   │    │ (Timing)   │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 VWAP pe support/resistance check → Pivot levels se             ║
║     target set → StochRSI se precise entry timing                   ║
║                                                                     ║
║  COMBO 5: "Swing Trader's Toolkit"                                 ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #19 EMA    │───►│ #10 Fib    │───►│ #22 SAR    │                ║
║  │ Ribbon     │    │ Pullback   │    │ Trailing   │                ║
║  │ (Trend Dir)│    │ (Entry)    │    │ (Exit)     │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 EMA Ribbon se trend direction → Fib pullback pe entry           ║
║     → Parabolic SAR se trailing stop                                ║
║                                                                     ║
║  COMBO 6: "Position Builder"                                       ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #9 Ichi    │───►│ #13 Donch  │───►│ #4 Slow    │                ║
║  │ Cloud      │    │ Channel    │    │ & Steady   │                ║
║  │ (Direction)│    │ (Breakout) │    │ (Hold)     │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 Ichimoku se overall direction → Donchian breakout pe           ║
║     entry → Slow&Steady style hold                                  ║
║                                                                     ║
║  COMBO 7: "Morning Session Express"                                ║
║  ┌────────────┐    ┌────────────┐    ┌────────────┐                 ║
║  │ #16 Gap    │───►│ #1 ORB     │───►│ #7 Scalper │                ║
║  │ & Go       │    │ Breakout   │    │            │                ║
║  │ (9:15 Gap) │    │ (9:30 BO)  │    │ (Quick $)  │                ║
║  └────────────┘    └────────────┘    └────────────┘                 ║
║  📝 Gap open check → ORB form hone do → Scalp quick moves          ║
║                                                                     ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 📐 STRATEGY FEATURES COMPARISON

```
╔════════════════════╦═════╦═════╦══════╦══════╦══════╦═══════╗
║ Strategy           ║ ATR ║Trail║ R:R  ║Trend ║ Vol  ║ Long+ ║
║                    ║ SL  ║Stop ║Target║Filter║Filter║ Short ║
╠════════════════════╬═════╬═════╬══════╬══════╬══════╬═══════╣
║ #1  ORB            ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
║ #2  MTF            ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #3  RSI Extremes   ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #4  Slow & Steady  ║  ✅ ║     ║  ✅  ║      ║      ║  L+S  ║
║ #5  Strong Trend   ║  ✅ ║  ✅ ║      ║  ✅  ║  ✅  ║  L+S  ║
║ #6  VWAP Bounce    ║  ✅ ║     ║  ✅  ║      ║  ✅  ║  L+S  ║
║ #7  Scalper        ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #8  BB Squeeze     ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
║ #9  Ichimoku       ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #10 Fib Pullback   ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #11 Pivot Points   ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #12 Supertrend     ║  ✅ ║  ✅ ║      ║      ║  ✅  ║  L+S  ║
║ #13 Donchian       ║  ✅ ║  ✅ ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #14 MACD Diverg    ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
║ #15 London BO      ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #16 Gap & Go       ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
║ #17 Heikin Ashi    ║  ✅ ║  ✅ ║      ║  ✅  ║      ║  L+S  ║
║ #18 Inside Bar     ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
║ #19 EMA Ribbon     ║  ✅ ║  ✅ ║      ║      ║      ║  L+S  ║
║ #20 Stoch RSI      ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #21 Chandelier     ║  ✅ ║  ✅ ║      ║  ✅  ║      ║  L+S  ║
║ #22 Parabolic SAR  ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #23 Vol Spike Rev  ║  ✅ ║     ║  ✅  ║      ║  ✅  ║  L+S  ║
║ #24 Dbl EMA Cross  ║  ✅ ║     ║  ✅  ║  ✅  ║      ║  L+S  ║
║ #25 NR7 Breakout   ║  ✅ ║     ║  ✅  ║  ✅  ║  ✅  ║  L+S  ║
╚════════════════════╩═════╩═════╩══════╩══════╩══════╩═══════╝
  ATR SL = ATR-based stop loss    Trail = Dynamic trailing stop
  R:R = Fixed Risk:Reward target  L+S = Both Long and Short
```

---

## 🎓 LEARNING PATH — Beginner Se Expert Tak Ka Raasta

```
╔═══════════════════════════════════════════════════════════════════════╗
║                     TRADING STRATEGY LEARNING PATH                   ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  MONTH 1-2: "FOUNDATION" (Paper Trading)                            ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #24 Double EMA Crossover      │ ← Sabse simple        ║
║  │ Week 3-4: #12 Supertrend                │ ← One indicator       ║
║  │ Week 5-6: #4  Slow & Steady             │ ← Patience seekho     ║
║  │ Week 7-8: #22 Parabolic SAR             │ ← Visual dots         ║
║  └───────────────────────┬─────────────────┘                        ║
║                          ▼                                          ║
║  MONTH 3-4: "INTRADAY BASICS" (Small Capital)                      ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #1  ORB                       │ ← Morning strategy    ║
║  │ Week 3-4: #6  VWAP Bounce               │ ← Institutional S/R   ║
║  │ Week 5-6: #11 Pivot Points              │ ← Classic S/R         ║
║  │ Week 7-8: #16 Gap and Go                │ ← Gap trading         ║
║  └───────────────────────┬─────────────────┘                        ║
║                          ▼                                          ║
║  MONTH 5-6: "INDICATOR MASTERY" (Build Edge)                       ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #5  Strong Trending (ADX)     │ ← Trend strength      ║
║  │ Week 3-4: #3  RSI Extremes              │ ← Mean reversion      ║
║  │ Week 5-6: #14 MACD Divergence           │ ← Divergence          ║
║  │ Week 7-8: #20 Stochastic RSI            │ ← Precision timing    ║
║  └───────────────────────┬─────────────────┘                        ║
║                          ▼                                          ║
║  MONTH 7-8: "PRICE ACTION & PATTERNS" (Refine)                    ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #18 Inside Bar Breakout       │ ← Pure price action   ║
║  │ Week 3-4: #25 NR7 Range Breakout        │ ← Range compression   ║
║  │ Week 5-6: #10 Fibonacci Pullback        │ ← Golden zone         ║
║  │ Week 7-8: #17 Heikin Ashi Trend         │ ← Smoothed candles    ║
║  └───────────────────────┬─────────────────┘                        ║
║                          ▼                                          ║
║  MONTH 9-10: "ADVANCED SYSTEMS" (Scale Up)                         ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #8  Bollinger Squeeze         │ ← Volatility          ║
║  │ Week 3-4: #9  Ichimoku Cloud            │ ← Multi-component     ║
║  │ Week 5-6: #2  MTF Analysis              │ ← Multi-timeframe     ║
║  │ Week 7-8: #19 EMA Ribbon                │ ← Visual trend        ║
║  └───────────────────────┬─────────────────┘                        ║
║                          ▼                                          ║
║  MONTH 11-12: "MASTER CLASS" (Pro Level)                           ║
║  ┌─────────────────────────────────────────┐                        ║
║  │ Week 1-2: #13 Donchian (Turtle)         │ ← Position trading    ║
║  │ Week 3-4: #21 Chandelier Exit           │ ← ATR trailing        ║
║  │ Week 5-6: #23 Volume Spike Reversal     │ ← Smart money         ║
║  │ Week 7-8: #7  Scalper                   │ ← Speed execution     ║
║  │           #15 London Breakout           │ ← Forex sessions      ║
║  └─────────────────────────────────────────┘                        ║
║                                                                     ║
║  ⚠️  Har stage mein minimum 50 paper trades karo before moving on   ║
║  ⚠️  Journal rakho — entry reason, exit reason, P&L, emotion        ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 💰 CAPITAL & BROKERAGE SUITABILITY

```
╔═══════════════════════════════════════════════════════════════════════╗
║                    CAPITAL REQUIREMENT GUIDE                         ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  ₹10,000 – ₹50,000 (Beginner / Small Account)                      ║
║  ├── #24 Double EMA Crossover (Cash market, swing)                  ║
║  ├── #4  Slow & Steady (Low frequency, low brokerage)               ║
║  ├── #12 Supertrend (Simple, fewer trades)                          ║
║  └── #17 Heikin Ashi (Swing hold, low cost)                         ║
║                                                                     ║
║  ₹50,000 – ₹2,00,000 (Intermediate Account)                        ║
║  ├── #1  ORB (Intraday, need margin)                                ║
║  ├── #5  Strong Trending (Moderate frequency)                       ║
║  ├── #6  VWAP Bounce (Intraday, margin required)                    ║
║  ├── #8  Bollinger Squeeze (Swing, moderate capital)                ║
║  ├── #10 Fibonacci Pullback (Swing)                                 ║
║  ├── #11 Pivot Points (Intraday)                                    ║
║  ├── #14 MACD Divergence (Swing)                                    ║
║  ├── #18 Inside Bar (Swing/positional)                              ║
║  ├── #20 Stochastic RSI (Intraday/swing)                            ║
║  ├── #22 Parabolic SAR (Swing)                                      ║
║  ├── #25 NR7 (Swing)                                                ║
║  └── #16 Gap and Go (Intraday, need quick execution)                ║
║                                                                     ║
║  ₹2,00,000 – ₹10,00,000 (Serious Trader)                           ║
║  ├── #2  MTF (Multiple positions possible)                          ║
║  ├── #3  RSI Extremes (Counter-trend needs buffer)                  ║
║  ├── #9  Ichimoku (Positional, larger stops)                        ║
║  ├── #13 Donchian (Weeks hold, drawdown buffer needed)              ║
║  ├── #15 London Breakout (Forex margin)                             ║
║  ├── #19 EMA Ribbon (Positional)                                    ║
║  ├── #21 Chandelier (Wide ATR stops need capital)                   ║
║  └── #23 Volume Spike Reversal (Counter-trend needs room)           ║
║                                                                     ║
║  ₹10,00,000+ (Professional)                                        ║
║  ├── #7  Scalper (High brokerage cost, need volume discount)        ║
║  └── #13 Donchian with Pyramiding (Multiple position adds)          ║
║                                                                     ║
║  💡 Rule of Thumb:                                                   ║
║     • Intraday = Min 2x margin requirement                          ║
║     • Swing    = Min 3x largest position size                       ║
║     • Position = Min 5x largest position (drawdown buffer)          ║
║     • Scalping = Min 10x per-trade risk (brokerage eats profit)     ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 🕐 INDIAN MARKET SESSION GUIDE — Kab Kaunsi Strategy?

```
╔═══════════════════════════════════════════════════════════════════════╗
║                  NSE/BSE TRADING DAY TIMELINE                        ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  9:00  ┊ PRE-MARKET ORDER SESSION                                   ║
║        ┊  └── Gap analysis karo: #16 Gap and Go ready rakho         ║
║        ┊                                                            ║
║  9:15  ┊ ★★★ MARKET OPENS ★★★                                      ║
║   ↓    ┊  ├── #16 Gap and Go → First 5 min gap direction check      ║
║  9:30  ┊  ├── #1  ORB → Opening Range form hone do (15-30 min)      ║
║        ┊  └── #7  Scalper → First volatility burst scalp            ║
║        ┊                                                            ║
║  9:30  ┊ OPENING RANGE COMPLETE (for 15m ORB)                       ║
║   ↓    ┊  ├── #1  ORB → Range breakout trade!                       ║
║  10:00 ┊  ├── #6  VWAP → VWAP establish hua, bounce/cross trade     ║
║        ┊  └── #11 Pivot → Pivot levels active, S/R bounce           ║
║        ┊                                                            ║
║  10:00 ┊ MID-MORNING (Trend establishes)                            ║
║   ↓    ┊  ├── #5  Strong Trending → ADX > 25 toh trend follow       ║
║  11:30 ┊  ├── #12 Supertrend → Green/red flip trade                 ║
║        ┊  ├── #2  MTF → Higher TF trend + lower TF entry            ║
║        ┊  └── #20 StochRSI → OB/OS timing for entries               ║
║        ┊                                                            ║
║  11:30 ┊ LUNCH LULL (Low volatility)                                ║
║   ↓    ┊  ├── ⚠️  Most intraday strategies AVOID this window        ║
║  13:00 ┊  ├── #8  BB Squeeze → Squeeze setup detect (build-up)      ║
║        ┊  ├── #25 NR7 → Narrow range bars forming                   ║
║        ┊  └── #18 Inside Bar → Pattern formation zone               ║
║        ┊                                                            ║
║  13:00 ┊ AFTERNOON SESSION (Volatility returns)                     ║
║   ↓    ┊  ├── #8  BB Squeeze → Breakout from lunch squeeze          ║
║  14:30 ┊  ├── #5  Strong Trending → New trend moves                 ║
║        ┊  ├── #14 MACD → Divergences develop                        ║
║        ┊  └── #3  RSI Extremes → Mean reversion setups              ║
║        ┊                                                            ║
║  14:30 ┊ CLOSING HOUR (Strong moves, position squaring)             ║
║   ↓    ┊  ├── #23 Vol Spike → Smart money volume spikes!            ║
║  15:15 ┊  ├── #22 SAR → SAR flip for next-day position              ║
║        ┊  ├── #17 HA → Heikin Ashi close for swing signal           ║
║        ┊  └── ⚠️  New intraday entries AVOID after 14:45            ║
║        ┊                                                            ║
║  15:15 ┊ AFTER MARKET                                               ║
║        ┊  └── Analysis: #9 Ichimoku, #19 EMA Ribbon, #21 Chandlr   ║
║        ┊      #10 Fib, #13 Donchian → Swing/positional planning     ║
║                                                                     ║
║  ⏰ BEST WINDOWS:                                                    ║
║     9:15-10:30  → Maximum volatility → Scalp, ORB, Gap, VWAP       ║
║     13:30-15:00 → Second wind → Breakouts, Trend, Reversals         ║
║     11:30-13:00 → Avoid intraday → Setup detection only             ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 🔄 Quick Decision Guide — Situation Ke Hisaab Se

### 📈 "Market strong trend mein hai"
→ **#5 Strong Trending** (ADX), **#12 Supertrend** (simple), **#9 Ichimoku** (advanced), **#19 EMA Ribbon** (visual)

### 📉 "Stock bahut gir/chad gaya hai, reversal aayega"
→ **#3 RSI Extremes** (quick), **#14 MACD Divergence** (confirmed), **#23 Volume Spike Reversal** (smart money)

### 📊 "Stock tight range mein stuck hai"
→ **#8 Bollinger Squeeze** (breakout wait), **#25 NR7** (narrowest range), **#18 Inside Bar** (pattern)

### ⏰ "Market abhi khula hai, opening trade chahiye"
→ **#1 ORB** (range breakout) ya **#16 Gap and Go** (gap open hua toh)

### 🏦 "Institutional level pe trade karna hai"
→ **#6 VWAP Bounce** (VWAP pe bounce/cross) ya **#11 Pivot Points** (classic S/R)

### 🔄 "Pullback pe entry chahiye trending stock mein"
→ **#10 Fibonacci Pullback** (golden zone) ya **#2 MTF** (multi-timeframe)

### ⚡ "Bahut quick trades chahiye, seconds mein"
→ **#7 Scalper** (triple EMA + Stochastic, 1m–5m)

### 🐢 "Long-term systematic trading, weeks/months hold"
→ **#13 Donchian Channel** (Turtle system), **#4 Slow & Steady** (EMA crossover)

### 💱 "Forex trading — USD/INR, EUR/INR"
→ **#15 London Breakout** (Asian range breakout on London open)

### 🔥 "Volatility compress hai, bada move aane wala hai"
→ **#8 Bollinger Squeeze** (squeeze detect), **#25 NR7** (narrowest range bar)

### 🕳️ "Stock gap up/down open hua hai"
→ **#16 Gap and Go** (gap direction mein momentum, first 30 min)

### 🎯 "Price action patterns trade karna hai (no indicators)"
→ **#18 Inside Bar Breakout** (candle within candle), **#25 NR7** (narrowest range)

### 🧈 "Smooth trend chahiye, noise nahi chahiye"
→ **#17 Heikin Ashi Trend** (smoothed candles), **#19 EMA Ribbon** (6-EMA visual)

### 📡 "Smart money/institutional activity detect karna hai"
→ **#23 Volume Spike Reversal** (2.5x volume + reversal candle)

### 🔴 "Trailing stop system chahiye (let profits run)"
→ **#21 Chandelier Exit** (ATR trailing), **#22 Parabolic SAR** (dot-based trailing)

### 🏁 "Beginner hoon, simple start karna hai"
→ **#24 Double EMA Crossover** (golden/death cross), **#12 Supertrend** (green/red signals)

### 🎯 "Precise entry timing chahiye (OB/OS zones)"
→ **#20 Stochastic RSI** (double-smoothed, very sensitive)

### 💼 "Capital kam hai, low brokerage mein karna hai"
→ **#4 Slow & Steady** (few trades), **#24 Double EMA** (simple swing), **#17 Heikin Ashi** (hold longer)

### 🔬 "Multiple confirmations chahiye, false signals kam"
→ **Combo 1** (#5+#12+#21), **Combo 2** (#23+#3+#14), ya **#9 Ichimoku** (5 built-in confirmations)

---

## ⚠️ COMMON MISTAKES CHART — Ye Galtiyan Mat Karna!

```
╔═══════════════════════════════════════════════════════════════════════╗
║                        COMMON MISTAKES                               ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  ❌ MISTAKE                          │ ✅ SOLUTION                   ║
║  ─────────────────────────────────── │ ──────────────────────────── ║
║  Sideways market mein trend          │ Pehle #5 ADX check karo     ║
║  strategy use karna                  │ ADX < 20 = NO trend trade   ║
║                                      │                              ║
║  Stop loss nahi lagana               │ Har strategy mein ATR SL    ║
║                                      │ built-in hai — USE IT       ║
║                                      │                              ║
║  Ek saath 5-6 strategies run         │ Max 2-3 strategies at once  ║
║  karna (signal confusion)            │ Ek per category enough      ║
║                                      │                              ║
║  Backtesting skip karna              │ Min 6 months backtest on    ║
║                                      │ TradingView before live     ║
║                                      │                              ║
║  Wrong timeframe pe strategy         │ ⏱️ Timeframe Chart dekho     ║
║  use karna                           │ ★★ wala TF use karo         ║
║                                      │                              ║
║  Scalper strategy ko daily           │ #7 Scalper = 1m-5m ONLY     ║
║  chart pe lagana                     │ Each strategy ka TF fixed   ║
║                                      │                              ║
║  Full capital ek trade mein          │ Max 2% risk per trade       ║
║  lagana                              │ Position sizing use karo    ║
║                                      │                              ║
║  Losing streak mein revenge          │ 3 consecutive loss ke baad  ║
║  trading karna                       │ STOP. Next day fresh start  ║
║                                      │                              ║
║  Indicator change karte rehna        │ Ek strategy ko 50+ trades   ║
║  (strategy hopping)                  │ do before switching         ║
║                                      │                              ║
║  News time pe trade karna            │ RBI policy, Budget, Results ║
║  (high impact events)                │ ke din intraday AVOID       ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 📋 PRE-TRADE CHECKLIST — Har Trade Se Pehle Check Karo

```
╔═══════════════════════════════════════════════════════════════════════╗
║                      PRE-TRADE CHECKLIST ✓                           ║
╠═══════════════════════════════════════════════════════════════════════╣
║                                                                     ║
║  □ 1. Market condition identify kiya?                               ║
║       (Trending / Ranging / Volatile → Market Matrix dekho)         ║
║                                                                     ║
║  □ 2. Strategy market condition ke saath match karti hai?            ║
║       (Market Condition Matrix mein ✅ hai?)                         ║
║                                                                     ║
║  □ 3. Sahi timeframe pe hai?                                        ║
║       (Timeframe Chart mein ★★ hai?)                                ║
║                                                                     ║
║  □ 4. Sahi instrument pe hai?                                       ║
║       (Instrument Chart mein ✅ hai?)                                ║
║                                                                     ║
║  □ 5. Stop loss set hai?                                            ║
║       (Strategy ka ATR-based SL automatic hai)                      ║
║                                                                     ║
║  □ 6. Position size sahi hai?                                       ║
║       (Max 1-2% capital risk per trade)                             ║
║                                                                     ║
║  □ 7. Koi major news/event toh nahi hai?                            ║
║       (RBI policy, quarterly results, budget day check)             ║
║                                                                     ║
║  □ 8. Trading session sahi hai?                                     ║
║       (Session Guide dekho — lunch time avoid for intraday)         ║
║                                                                     ║
║  □ 9. Backtesting/paper trade kiya is strategy ka?                  ║
║       (Min 50 paper trades before real money)                       ║
║                                                                     ║
║  □ 10. Emotionally stable ho?                                       ║
║        (Revenge trading / FOMO / Fear = DO NOT TRADE)               ║
║                                                                     ║
║  ✅ Sab checked? → TRADE!                                           ║
║  ❌ Kuch miss? → WAIT. Setup dubara aayega.                         ║
╚═══════════════════════════════════════════════════════════════════════╝
```

---

## 📊 Strategies by Difficulty Level

### 🟢 Beginner Friendly (Start Yahan Se)
- **#24 Double EMA Crossover** — Classic golden/death cross, sabse simple concept
- **#12 Supertrend** — One indicator, green/red signals, no confusion
- **#4 Slow & Steady** — EMA crossover, daily chart, kam trades
- **#1 ORB** — Simple range breakout, clear rules
- **#22 Parabolic SAR** — Visual dots, easy to read

### 🟡 Intermediate (Thoda Experience Ke Baad)
- **#5 Strong Trending** — ADX + EMA, thoda indicator knowledge chahiye
- **#6 VWAP Bounce** — VWAP samajhna zaroori, intraday focus
- **#3 RSI Extremes** — RSI + divergence concepts
- **#10 Fibonacci Pullback** — Fib retracement samajhna padega
- **#11 Pivot Points** — S/R concept clear hona chahiye
- **#14 MACD Divergence** — Divergence spotting practice chahiye
- **#16 Gap and Go** — Gap trading concept + volume analysis
- **#17 Heikin Ashi Trend** — HA candle concept samajhna padega
- **#18 Inside Bar Breakout** — Price action pattern recognition
- **#20 Stochastic RSI** — Double-smoothed oscillator, noisy but precise
- **#25 NR7 Range Breakout** — Narrow range concept + breakout mechanics

### 🔴 Advanced (Expert Level)
- **#7 Scalper** — Fast execution, discipline, brokerage management
- **#2 MTF** — Multiple timeframes simultaneously analyze karna
- **#8 Bollinger Squeeze** — BB + KC + momentum + volume analysis
- **#9 Ichimoku Cloud** — 5 components samajhne padenge
- **#13 Donchian Channel** — Pyramiding risk, weeks hold karna
- **#15 London Breakout** — Forex session timing, RBI dynamics
- **#19 EMA Ribbon** — 6 EMAs simultaneously track karna
- **#21 Chandelier Exit** — ATR trailing system, position management
- **#23 Volume Spike Reversal** — Volume + RSI + candle pattern confluence

---

## 🗂️ Strategies by Category

### 🟦 Trend Following
`#5 Strong Trending` → `#12 Supertrend` → `#9 Ichimoku` → `#19 EMA Ribbon` → `#17 Heikin Ashi` → `#4 Slow & Steady` → `#13 Donchian`

### 🟥 Reversal / Mean Reversion
`#3 RSI Extremes` → `#14 MACD Divergence` → `#23 Volume Spike Reversal` → `#20 Stochastic RSI`

### 🟨 Breakout / Volatility
`#1 ORB` → `#8 Bollinger Squeeze` → `#18 Inside Bar` → `#25 NR7` → `#16 Gap and Go` → `#15 London Breakout`

### 🟩 Support / Resistance
`#6 VWAP Bounce` → `#11 Pivot Points` → `#10 Fibonacci Pullback`

### 🟪 Trailing Stop Systems
`#12 Supertrend` → `#22 Parabolic SAR` → `#21 Chandelier Exit`

### ⬜ Classic / Crossover
`#24 Double EMA Crossover` → `#4 Slow & Steady` → `#2 MTF`

### ⚡ Scalping / Quick
`#7 Scalper` → `#16 Gap and Go` → `#1 ORB`

---

## 🛠️ Setup (Sabke Liye Same)
1. **TradingView** kholo → Pine Editor tab
2. Strategy folder mein jaake `.pine` file ka code copy karo
3. Pine Editor mein paste karo → **Add to Chart**
4. Settings ⚙️ mein apne stock/timeframe ke hisaab se inputs adjust karo
5. **Strategy Tester** tab mein backtest results dekho
6. Har strategy ka **README.md** padho — example, flowchart aur tips diye hain

---

## ⚠️ Disclaimer
Ye strategies **educational purpose** ke liye hain. Real money lagane se pehle:
- Paper trading / backtesting karo (minimum 50 trades)
- Apna risk management samjho (max 1-2% per trade)
- Capital ka sirf wo amount use karo jo lose karne pe affect na kare
- Koi bhi strategy 100% accurate nahi hoti — losses part of the game hai
- Past performance future results guarantee nahi karta
