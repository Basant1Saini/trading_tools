# MTF — Multi-Time Frame Strategy

## Overview
Ye strategy higher timeframe ka trend check karti hai aur lower timeframe pe entry leti hai. Matlab bade picture ke direction mein hi trade karo — trend ke against nahi.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    START
                      │
        Higher timeframe (Daily/Weekly)
        mein clear trend dikh raha hai?
                 /          \
               YES           NO
                │             │
                │        └──→ ❌ MTF ko clear
                │             HTF trend chahiye.
                │             Sideways mein
                │             kaam nahi karega.
                │
        Lower timeframe pe
        entry dhundh rahe ho?
        (5m, 15m, 1H)
              /        \
            YES         NO
             │           │
             │      └──→ ❌ Sirf Daily pe
             │           trade karna hai toh
             │           Slow & Steady (#4)
             │           ya Supertrend (#12)
             │           dekho.
             │
        Trend ke saath trade
        karna hai (na ki against)?
              /        \
            YES         NO
             │           │
             │      └──→ ❌ Counter-trend
             │           chahiye toh RSI
             │           Extremes (#3) ya
             │           MACD Divergence (#14)
             │           dekho.
             │
     ✅ MTF STRATEGY USE KARO!
     2_MTF.pine chart pe lagao
```

## Kaise Kaam Karta Hai
1. **Higher Timeframe Trend** — Daily chart pe check karo ki close 50-period MA ke upar hai ya neeche.
2. **Lower Timeframe Entry** — Current chart pe fast MA jab slow MA ko cross kare toh entry — lekin sirf HTF trend ki direction mein.
3. **Exit** — ATR-based stop loss aur risk:reward take profit.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Higher Timeframe | Daily | Trend decide karne ke liye timeframe |
| Fast MA Length | 9 | Entry timeframe pe fast moving average |
| Slow MA Length | 21 | Entry timeframe pe slow moving average |
| HTF Trend MA | 50 | Higher timeframe ka MA length |
| MA Type | EMA | EMA ya SMA choose karo |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 5m – 1H chart with Daily as higher timeframe
- **Markets:** NSE large-caps (TCS, Infosys, Reliance), Nifty, BankNifty
- **Style:** Swing aur intraday trend-following

## Setup
1. TradingView kholo → Pine Editor
2. `2_MTF.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Higher Timeframe input set karo (D, W, 4H)

## Example: TCS on 15-Minute Chart with Daily HTF

**Scenario:** TCS Daily chart pe clear uptrend mein hai. 15m chart pe entry dhundh rahe ho.

1. **Daily Timeframe Check**
   - TCS Daily close: ₹3,890
   - 50 EMA on Daily: ₹3,780
   - Daily close > 50 EMA → **HTF = Bullish** (chart background green ho jayega)

2. **15-Minute Chart Entry**
   - 9 EMA: ₹3,875 (pullback ke baad thoda neeche)
   - 21 EMA: ₹3,880
   - **10:30 AM — 9 EMA ne 21 EMA ko upar cross kiya** → Long signal!
   - **Entry:** Long at ₹3,882

3. **Risk Management**
   - ATR(14) on 15m = ₹22, ATR Mult = 2.0
   - **Stop Loss:** ₹3,882 − (₹22 × 2.0) = ₹3,838
   - **Take Profit:** ₹3,882 + (₹44 × 2.0 R:R) = ₹3,970

4. **Next Day — TCS daily trend continue karta hai**
   - Price ₹3,970 hit karta hai → **TP filled**
   - **Result:** +₹88/share (+2.3%)
   - 200 shares pe: **+₹17,600 profit**

**Kyun kaam kiya:** Daily trend clearly bullish tha, toh 15m pullback aur EMA crossover high-probability re-entry tha bade move ki direction mein.

**Dhyan rakho:**
- Agar Daily close 50 EMA ke bilkul paas hai (flat trend), toh signals unreliable honge — clear separation ka wait karo.
- Counter-trend entries automatically filter ho jaati hain.
- IT sector results season mein extra volatile hota hai — SL thoda wider rakho.

## Notes
- Chart background green/red hota hai HTF trend direction dikhane ke liye.
- Triangle markers entry points pe dikhte hain.
- Higher timeframe ke against trades automatically filter ho jaate hain.
