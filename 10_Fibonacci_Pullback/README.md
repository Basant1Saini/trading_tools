# Fibonacci Pullback Strategy

## Overview
Ye strategy tab entry leti hai jab established trend mein price Fibonacci "golden zone" (38.2%–61.8%) tak pullback kare. Swing aur position traders ka classic approach hai ye.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya stock mein recent STRONG
        MOVE aaya hai (up ya down)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ No trend = no Fib levels
                  |       #8 Bollinger Squeeze ya #3 RSI Extremes dekho
                  |
     Kya ab PULLBACK aa raha hai
     us move ke baad?
                /     \
             YES       NO
              |         |
              |    ⏳ Pullback ka wait karo —
              |       trending mein #5 Strong Trending use karo
              |
     Kya price GOLDEN ZONE (38.2%–61.8%)
     mein aaya hai?
                /     \
             YES       NO
              |         |
              |    ⏳ Abhi 23.6% pe hai?
              |       Golden zone tak aane do ya skip karo
              |
     Kya trend direction mein BULLISH/BEARISH
     candle bani hai golden zone mein?
                /     \
             YES       NO
              |         |
              |    ⚠️ Weak candle (doji)?
              |       Strong close ka wait karo
              |
     Kya EMA trend filter confirm
     kar raha hai + RSI neutral zone mein?
                /     \
             YES       NO
              |         |
              |    ⚠️ RSI extreme hai?
              |       #3 RSI Extremes better hoga
              |
    ✅ FIBONACCI PULLBACK USE KARO!
    📁 10_Fibonacci_Pullback.pine
```

## Kaise Kaam Karta Hai
1. **Swing Detection** — Recent swing high aur low identify karta hai configurable lookback pe.
2. **Fib Levels** — 38.2%, 50%, aur 61.8% retracement levels draw karta hai.
3. **Golden Zone Entry** — Price jab 38.2–61.8% zone mein aaye aur trend direction mein candle bane.
4. **Filters** — EMA trend direction ke liye + RSI extreme conditions avoid karne ke liye.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Swing Length | 20 | Swing high/low detection ka lookback |
| Fib Levels | 38.2 / 50 / 61.8 | Standard Fibonacci ratios |
| Fib Zone Buffer | 0.5% | Fib levels ke around slack |
| Trend EMA | 50 | Trend direction filter |
| RSI Length | 14 | RSI momentum filter ke liye |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.5 | Take profit ratio |

## Best Used On
- **Timeframe:** 1H – Daily
- **Markets:** NSE banking/financial stocks (SBI, ICICI, Kotak), Nifty
- **Style:** Swing trading / pullback entries

## Setup
1. TradingView kholo → Pine Editor
2. `10_Fibonacci_Pullback.pine` ka code paste karo
3. **Add to Chart** pe click karo

## Example: SBI (SBIN) — 4-Hour Chart

**Scenario:** SBI rally kar ke ₹620 se ₹680 tak gaya credit growth numbers ke baad. Ab pullback aa raha hai.

1. **Swing Detection & Fib Levels**
   - Swing Low: ₹620 (2 hafte pehle)
   - Swing High: ₹680 (recent high)
   - Range = ₹60
   - **38.2% retracement:** ₹680 − (₹60 × 0.382) = ₹657
   - **50.0% retracement:** ₹680 − (₹60 × 0.500) = ₹650
   - **61.8% retracement:** ₹680 − (₹60 × 0.618) = ₹643
   - **Golden Zone: ₹643 – ₹657**

2. **Pullback Golden Zone mein aaya**
   - SBI 3 din mein ₹680 se ₹648 tak pull back kiya
   - Price ₹648 → Golden zone ke andar ✅
   - 50 EMA = ₹635 → Price uske upar (uptrend confirmed) ✅
   - RSI = 44 (na overbought, na oversold) ✅
   - Bullish candle: close ₹653 > open ₹648 ✅
   - **Entry:** Long at ₹653

3. **Risk Management**
   - ATR(14) on 4H = ₹8.50, ATR Mult = 2.0
   - **Stop Loss:** ₹653 − (₹8.50 × 2.0) = ₹636
   - **Take Profit:** ₹653 + (₹17 × 2.5 R:R) = ₹695.50

4. **Week 2 — SBI uptrend resume karta hai**
   - Price golden zone se bounce karke ₹680 (previous high) ke upar gaya
   - **Take profit hit at ₹695.50** (new swing high)
   - **Result:** +₹42.50/share (+6.5%)
   - 500 shares pe: **+₹21,250 profit**

**Kyun kaam kiya:** 50% Fib level (₹650) sabse common retracement level hai. SBI ne wahi pe bounce kiya bullish candle ke saath — buyers step in kar rahe the. TP ne original high ke baad extension target kiya.

**Dhyan rakho:**
- Agar price 61.8% level ko bina ruke slice kar jaaye, toh trend reverse ho sakta hai — falling knife mat pakdo.
- Best setups mein Fib levels doosre support ke saath overlap karte hain (previous resistance, round numbers jaise ₹650).
- Golden zone mein weak candle (doji, spinning top) = indecision — strong close ka wait karo.
- PSU bank stocks mein government policy changes ka bada impact hota hai — budget, election news dhyan mein rakho.

## Notes
- Fib levels chart pe dynamically plot hote hain.
- Golden zone (38.2%–61.8%) sabse zyada probability wala S/R zone hai.
- Doosre confluence (S/R levels, trendlines, volume) ke saath best kaam karta hai.
- Higher R:R (2.5:1) swing extension target karta hai original high/low ke baad.

---

## 📊 Quick Stats

```
╔══════════════════════════════════════════════════╗
║  Difficulty:   🟡 Intermediate                  ║
║  Risk Level:   Medium                           ║
║  Timeframe:    1H-4H (best)                    ║
║  Frequency:    1-3 signals/day                  ║
║  Hold Time:    Days                             ║
║  Capital Need: ₹50,000+ (swing trading)         ║
╚══════════════════════════════════════════════════╝
```

## ✅ Kab Use Karo / ❌ Kab Avoid Karo

```
✅ USE KARO:                        ❌ AVOID KARO:
├── Trending market (pullback)      ├── Sideways/no clear swing
├── Clear swing high/low exists     ├── Gap opening days
├── Price at 0.5-0.618 zone         ├── No volume on bounce
├── Weak trend pullback             ├── V-shape reversal (no PB)
├── EMA support near fib level      ├── Overextended moves
└── Higher TF trend intact          └── Penny/illiquid stocks
```

## 🔗 Best Strategy Combinations
- **#10 Fib + #5 Strong Trending** → ADX confirms trend, Fib gives entry level
- **#10 Fib + #19 EMA Ribbon** → EMA Ribbon direction + Fib pullback entry
- **#10 Fib + #22 Parabolic SAR** → SAR trailing stop after Fib entry

## ⚠️ Common Mistakes
1. **Wrong swing points select karna** → Recent clear swing use karo, random nahi
2. **Sirf 0.382 pe entry** → 0.5-0.618 (golden zone) better hai — deeper pullback = stronger
3. **Trend direction ignore karna** → Uptrend mein sirf long Fib, downtrend mein sirf short
4. **SBI mein results ke din Fib trade** → Major events se pehle Fib levels unreliable
5. **Every pullback trade karna** → Fib + EMA + volume confluence = trade, akela Fib weak

## 💡 Pro Tips
- 0.618 + 50 EMA confluence = strongest pullback entry point
- SBI/banking stocks mein RBI policy ke around Fib levels very well respected hote hain
- Higher TF Fib level + lower TF entry = best approach
- Fib extension 1.618 level as target use karo — very common take-profit level
- Volume dry up on pullback + volume spike on bounce = classic institutional buying
