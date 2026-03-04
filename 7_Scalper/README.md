# Scalper — Quick Strike

## Overview
Ye ek fast-paced scalping strategy hai jo triple EMA alignment se trend direction pakadti hai aur Stochastic oscillator se precise entry timing leti hai. Chhote chhote quick trades ke liye — tight stops ke saath.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum FAST trades chahte ho
        (seconds se minutes)?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Slow style chahiye?
                  |       #4 Slow & Steady ya #9 Ichimoku dekho
                  |
     Kya tumhara EXECUTION fast hai
     (low latency, quick order placement)?
                /     \
             YES       NO
              |         |
              |    ❌ Scalping mein slow execution
              |       = slippage losses — #6 VWAP ya #1 ORB dekho
              |
     Kya stock TIGHT SPREAD hai
     (Tata Motors, SBIN jaise liquid)?
                /     \
             YES       NO
              |         |
              |    ❌ Wide spread scalping profit
              |       kha jaayega — #8 Bollinger Squeeze dekho
              |
     Kya tum BROKERAGE costs handle
     kar sakte ho (frequent trades)?
                /     \
             YES       NO
              |         |
              |    ⚠️ Kam trades chahiye?
              |       #2 MTF ya #6 VWAP Bounce dekho
              |
     Kya market TRENDING hai
     (clear direction, na choppy)?
                /     \
             YES       NO
              |         |
              |    ⏳ Wait karo — range-bound
              |       mein scalping = death by 1000 cuts
              |
    ✅ SCALPER USE KARO!
    📁 7_Scalper.pine
```

## Kaise Kaam Karta Hai
1. **EMA Alignment** — Teeno EMAs (5/13/34) stacked hone chahiye trend confirm karne ke liye.
2. **Stochastic Trigger** — Stochastic K jab D ko cross kare trend direction mein favorable zone se.
3. **Quick Exits** — Tight ATR stops with 1.5:1 R:R ratio for fast profit-taking.
4. **Trade Limiter** — Max trades per day cap hai overtrading se bachne ke liye.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Fast / Med / Slow EMA | 5, 13, 34 | Triple EMA trend ke liye |
| Stochastic K / D | 14, 3 | Stochastic oscillator settings |
| OB / OS Levels | 80 / 20 | Stochastic extremes |
| ATR Multiplier | 1.0 | Tight stop loss |
| Risk:Reward | 1.5 | Quick take profit |
| Max Trades/Day | 10 | Overtrading protection |

## Best Used On
- **Timeframe:** 1m – 5m
- **Markets:** Liquid NSE stocks (Tata Motors, SBIN, ICICI Bank), BankNifty futures
- **Style:** Scalping (seconds se minutes per trade)

## Setup
1. TradingView kholo → Pine Editor
2. `7_Scalper.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Session time adjust karo (09:20–15:25 safe window hai)

## Example: Tata Motors (TATAMOTORS) — 1 Minute Chart

**Scenario:** Tata Motors morning session mein trend kar raha hai upar. Quick scalps chahiye.

1. **09:35 AM — EMA Alignment**
   - 5 EMA: ₹785.40
   - 13 EMA: ₹784.80
   - 34 EMA: ₹783.50
   - **5 > 13 > 34** → Bull alignment confirmed

2. **09:37 AM — Stochastic Trigger**
   - Stochastic K 28 pe tha (small pullback ke baad oversold zone ke paas)
   - K ne D ko 32 pe upar cross kiya (favorable zone <50)
   - Tata Motors close = ₹785.60 (5 EMA ke upar)
   - **Entry:** Long at ₹785.60

3. **Risk Management**
   - ATR(10) on 1m = ₹1.80, ATR Mult = 1.0
   - **Stop Loss:** ₹785.60 − ₹1.80 = ₹783.80
   - **Take Profit:** ₹785.60 + (₹1.80 × 1.5 R:R) = ₹788.30

4. **09:40 AM — Quick TP hit!**
   - Tata Motors push karta hai ₹788.50 tak
   - **Take profit filled at ₹788.30**
   - **Result:** +₹2.70/share (+0.34%) ~3 minutes mein
   - Trade count: 1 of 10 max

5. **Pura session summary**
   - 11 AM tak: 4 trades liye, 3 winners, 1 stopped out
   - **Net: +₹6.20/share across 4 trades**
   - 500 shares pe: **+₹3,100 net profit**

**Kyun kaam kiya:** Tata Motors liquid hai, tight spread hai — scalping ke liye perfect. Triple EMA ne direction diya, Stochastic ne micro-pullback pe timing.

**Dhyan rakho:**
- Opening ke pehle 5 min (09:15–09:20) mein scalp mat karo — spread wide aur erratic hota hai.
- Agar Tata Motors ₹3 range mein stuck hai, ATR compress ho jayega — skip karo.
- 10 trade limit lagi? Ruk jao. Overtrading scalper ka #1 dushman hai.
- Brokerage charges ka dhyan rakho — per trade ₹20 bhi bada impact dalta hai frequent trades mein.

## Notes
- 1x ATR stops tight hain — liquid markets aur fast execution zaroori hai.
- Daily trade limiter har session reset hota hai.
- Low-volume periods aur major news events ke time avoid karo.
