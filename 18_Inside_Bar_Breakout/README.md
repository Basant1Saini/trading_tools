# Inside Bar Breakout — Price Action Strategy

## Overview
Ye ek pure price action strategy hai jo inside bar pattern detect karti hai — jab ek candle completely previous candle ke range ke andar ban jaaye. Ye consolidation/indecision dikhata hai aur breakout ke baad strong move aata hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum PRICE ACTION based
        trading karna chahte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Indicator-based chahiye?
                  |       #12 Supertrend ya #19 EMA Ribbon dekho
                  |
     Kya tumhe CONSOLIDATION ke baad
     BREAKOUT trade karna hai?
                /     \
             YES       NO
              |         |
              |    ⚠️ Trending entry chahiye?
              |       #5 Strong Trending ya #17 Heikin Ashi dekho
              |
     Kya chart pe INSIDE BAR pattern
     dikh raha hai (candle within candle)?
                /     \
             YES       NO
              |         |
              |    ⏳ Pattern form hone ka
              |       wait karo — force mat karo
              |
     Kya TREND DIRECTION clear hai
     (EMA filter se)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Both sides breakout possible
              |       trend filter ON karo ya skip
              |
     Kya BREAKOUT pe VOLUME above
     average hai (1.3x+)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Low volume breakout = false
              |       breakout risk — #8 Bollinger Squeeze dekho
              |
    ✅ INSIDE BAR BREAKOUT USE KARO!
    📁 18_Inside_Bar_Breakout.pine
```

## Kaise Kaam Karta Hai
1. **Inside Bar Detection** — Current bar ka high ≤ previous bar ka high AND low ≥ previous bar ka low.
2. **Double Inside Bar** (optional) — 2 consecutive inside bars = stronger compression, bigger breakout.
3. **Breakout Entry** — Mother bar ke high/low ke upar/neeche break pe entry with buffer.
4. **Filters** — EMA trend direction + volume confirmation on breakout.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Double Inside Bars | On | 2 consecutive IB detect karo (stronger) |
| Trend EMA | 50 | Trend direction filter |
| Volume Multiplier | 1.3x | Breakout pe min volume |
| Breakout Buffer | 0.1% | Mother bar high/low ke upar/neeche slack |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 1H – Daily
- **Markets:** Pharma stocks (Sun Pharma, Dr Reddy's, Cipla), any trending market
- **Style:** Breakout trading / swing

## Setup
1. TradingView kholo → Pine Editor
2. `18_Inside_Bar_Breakout.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: Sun Pharma (SUNPHARMA) — Daily Chart

**Scenario:** Sun Pharma FDA approval ka wait kar raha hai. Stock tight range mein consolidate ho raha hai.

1. **Inside Bar Formation**
   - Day 1 (Mother bar): High ₹1,820, Low ₹1,770, Range = ₹50
   - Day 2 (Inside bar 1): High ₹1,810, Low ₹1,778 — **Inside bar!** ✅
   - Day 3 (Inside bar 2): High ₹1,805, Low ₹1,782 — **Double inside bar!** ✅✅
   - Blue background + "IB" diamond marker dikhta hai
   - Compression extreme hai — big move aane wala hai

2. **Day 4 — Breakout!**
   - FDA approval news aati hai evening mein
   - Sun Pharma ₹1,835 pe open, ₹1,842 pe close
   - Mother bar high ₹1,820 + buffer (0.1%) = ₹1,822 → Price uske upar ✅
   - 50 EMA = ₹1,780 → Price upar (trend bullish) ✅
   - Volume = 1.8x average ✅
   - **Entry:** Long at ₹1,842

3. **Risk Management**
   - ATR(14) = ₹32, ATR Mult = 1.5
   - **Stop Loss:** ₹1,842 − (₹32 × 1.5) = ₹1,794
   - **Take Profit:** ₹1,842 + (₹48 × 2.0 R:R) = ₹1,938

4. **Week 2 — Breakout chal gaya**
   - Sun Pharma ₹1,920 tak rally — compressed energy release
   - **Take profit hit at ₹1,938**
   - **Result:** +₹96/share (+5.2%)
   - 100 shares pe: **+₹9,600 profit**

**Kyun kaam kiya:** Double inside bar ne extreme compression dikhaya. FDA approval catalyst ne directional breakout trigger kiya. Volume 1.8x ne confirm kiya ki institutional buying hai.

**Dhyan rakho:**
- Inside bar pattern har timeframe pe kaam karta hai — lekin daily pe sabse reliable.
- Pharma stocks mein FDA news, USFDA inspection results sudden moves laate hain.
- Agar breakout ke baad price wapas mother bar ke andar aa jaaye = false breakout, turant exit karo.
- Double inside bar > single inside bar (tighter compression = stronger breakout).

## Notes
- Blue background inside bar periods highlight karta hai.
- "IB" diamond markers inside bars pe dikhte hain.
- Breakout pending sirf 5 bars tak valid rehta hai — uske baad cancel.
- Volume confirmation false breakouts filter karta hai.
