# VWAP Bounce & Cross

## Overview
Ye ek intraday strategy hai jo VWAP (Volume Weighted Average Price) ke around trade karti hai — VWAP institutional traders ka benchmark hota hai. Price jab VWAP pe aake bounce kare ya cross kare, tab entry leti hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    [START]
                      |
        Kya tum INTRADAY trade karte ho?
                    /     \
                 YES       NO
                  |         |
                  |    ❌ Skip — Swing ke liye
                  |       #10 Fibonacci ya #9 Ichimoku dekho
                  |
     Kya stock LIQUID hai (ICICI Bank,
     Reliance, BankNifty jaise)?
                /     \
             YES       NO
              |         |
              |    ❌ Illiquid stocks mein
              |       VWAP unreliable hai — #5 Strong Trending dekho
              |
     Kya tum INSTITUTIONAL levels
     ke around trade karna chahte ho?
                /     \
             YES       NO
              |         |
              |    ⚠️ Simple approach chahiye?
              |       #1 ORB ya #7 Scalper dekho
              |
     Kya price VWAP ke paas aa rahi hai
     ya cross kar rahi hai?
                /     \
             YES       NO
              |         |
              |    ⏳ Wait karo — price VWAP
              |       se door hai, bounce nahi milega
              |
     Kya trend filter (EMA) direction
     confirm kar raha hai?
                /     \
             YES       NO
              |         |
              |    ⚠️ Choppy market —
              |       "Cross" mode try karo ya wait karo
              |
    ✅ VWAP BOUNCE USE KARO!
    📁 6_VWAP_Bounce.pine
```

## Kaise Kaam Karta Hai
1. **VWAP Anchor** — Session ka VWAP calculate hota hai with 1x aur 2x standard deviation bands.
2. **Bounce Mode** — Price VWAP tak gire aur wapas upar close kare toh Long; upar jaake neeche close kare toh Short.
3. **Cross Mode** — Clean crossover/crossunder pe entry.
4. **Filters** — Optional EMA trend filter aur session time window.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| Entry Mode | Bounce | Bounce, Cross, ya Both |
| Bounce Buffer | 0.1% | VWAP se kitna paas aana chahiye |
| Trend Filter EMA | 20 | Directional bias ke liye EMA |
| Band 1 / Band 2 | 1.0 / 2.0 | VWAP band widths |
| ATR Multiplier | 1.5 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 1m – 15m
- **Markets:** NSE liquid stocks (ICICI Bank, HDFC, Reliance), Nifty/BankNifty futures
- **Style:** Intraday institutional-level trading

## Setup
1. TradingView kholo → Pine Editor
2. `6_VWAP_Bounce.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. Session time Indian market ke liye adjust karo (09:15–15:30)

## Example: ICICI Bank (ICICIBANK) — 5 Minute Chart

**Scenario:** ICICI Bank morning mein strong open hua. VWAP se bounce entry dhundh rahe ho.

1. **Market Open**
   - ICICI Bank open: ₹1,245, rally karke ₹1,268 tak pehle 30 min mein
   - VWAP form ho raha hai ₹1,255 pe
   - 20 EMA on 5m = ₹1,258 → Price EMA ke upar (trend filter bullish)

2. **10:20 AM — Pullback VWAP tak**
   - ICICI Bank pullback karta hai ₹1,268 se ₹1,256 tak
   - VWAP = ₹1,255, Bounce Buffer = 0.1%
   - Low ₹1,254 touch kiya (VWAP ke buffer mein), candle close ₹1,258 (VWAP ke upar)
   - **Entry:** Long at ₹1,258 (VWAP bounce)

3. **Risk Management**
   - ATR(14) on 5m = ₹5.50, ATR Mult = 1.5
   - **Stop Loss:** ₹1,258 − (₹5.50 × 1.5) = ₹1,250
   - **Take Profit:** ₹1,258 + (₹8 × 2.0 R:R) = ₹1,274

4. **11:15 AM — Bounce kaam kiya**
   - Institutional buyers ne VWAP pe support diya, price ₹1,276 tak gaya
   - **Take profit hit at ₹1,274**
   - **Result:** +₹16/share (+1.3%)
   - 500 shares pe: **+₹8,000 profit**

**Kyun kaam kiya:** VWAP institutional order flow ka magnet hota hai. ICICI Bank uptrend mein tha aur VWAP pe large funds ne apne orders fill kiye — classic bounce.

**Dhyan rakho:**
- Agar price VWAP ke aas paas bina direction ke chop kar raha hai, toh "Cross" mode use karo ya wait karo.
- Din ka pehla VWAP bounce sabse strong hota hai — baad ke bounces weak hote hain.
- BankNifty expiry day pe VWAP bounces unreliable ho sakte hain — extra volume filter lagao.

## Notes
- VWAP har session reset hota hai — purely intraday tool hai.
- VWAP bands overextended price identify karne mein madad karte hain.
- Session end pe sab positions close ho jaati hain.
