# RSI Extremes — Mean Reversion

## Overview
Ye ek mean-reversion strategy hai jo tab entry leti hai jab RSI extreme overbought/oversold levels pe pahunch jaaye aur wapas aane lage. Optional RSI divergence confirmation ke liye bhi hai.

## Kya Ye Strategy Tumhare Liye Hai? (Decision Flowchart)

```
                    START
                      │
          Stock mein bada sell-off
          ya rally aayi hai recently?
                 /          \
               YES           NO
                │             │
                │        └──→ ❌ RSI Extremes ko
                │             extreme move chahiye.
                │             Trending market mein
                │             MTF (#2) ya
                │             Supertrend (#12) dekho.
                │
          RSI 25 ke neeche (oversold)
          ya 75 ke upar (overbought)
          pahunch gaya hai?
                /          \
              YES           NO
               │             │
               │        └──→ ⏳ Abhi extreme
               │             nahi hai. Wait karo
               │             jab tak RSI extreme
               │             zone mein na aaye.
               │
          Stock large-cap /
          blue-chip hai?
          (HDFC, Reliance, TCS)
               /          \
             YES           NO
              │             │
              │        └──→ ⚠️ Small-caps mein
              │             mean reversion
              │             kaam nahi karta.
              │             Bahut risky hai.
              │
         RSI wapas aane laga?
         (Divergence ya extreme
         se recover ho raha?)
               /        \
             YES         NO
              │           │
              │      └──→ ⏳ Abhi wait karo.
              │           "Falling knife"
              │           mat pakdo. RSI ko
              │           wapas aane do.
              │
      ✅ RSI EXTREMES USE KARO!
      3_RSI_Extremes.pine lagao
```

## Kaise Kaam Karta Hai
1. **RSI Extreme Detection** — RSI ko monitor karti hai oversold (≤25) ya overbought (≥75) zones ke liye, deeper extremes 15 aur 85 pe.
2. **Reversal Entry** — Long tab jab RSI oversold se wapas upar aaye; Short tab jab RSI overbought se neeche aaye.
3. **Divergence Filter** (optional) — Bullish/bearish RSI divergence se confirm karti hai.
4. **Trend Filter** (optional) — 200 SMA filter ensure karta hai ki longs MA ke upar liye jaayein.

## Key Inputs
| Parameter | Default | Description |
|-----------|---------|-------------|
| RSI Length | 14 | RSI calculation period |
| Overbought | 75 | Standard overbought threshold |
| Oversold | 25 | Standard oversold threshold |
| Extreme OB | 85 | Deep overbought level |
| Extreme OS | 15 | Deep oversold level |
| Divergence | On | RSI divergence confirmation |
| Trend Filter MA | 200 | SMA length trend direction ke liye |
| ATR Multiplier | 2.0 | Stop loss distance |
| Risk:Reward | 2.0 | Take profit ratio |

## Best Used On
- **Timeframe:** 15m – Daily
- **Markets:** Large-cap stocks jo mean revert karti hain (HDFC Bank, Reliance, ITC, Kotak)
- **Style:** Counter-trend / mean reversion

## Setup
1. TradingView kholo → Pine Editor
2. `3_RSI_Extremes.pine` ka code paste karo
3. **Add to Chart** pe click karo
4. OB/OS levels apne stock ke hisaab se tune karo

## Example: HDFC Bank (HDFCBANK) — Daily Chart

**Scenario:** HDFC Bank mein FII selling ke chalte achanak bada sell-off aa gaya.

1. **Day 1–3 — Sell-off**
   - HDFC Bank ₹1,680 se gir ke ₹1,580 aa gaya 3 din mein
   - RSI(14) gir ke **17** pe aa gaya (Extreme OS 15 ke neeche → deep oversold)
   - 200 SMA = ₹1,540 → Price abhi bhi uske upar hai (trend filter OK)
   - Background green ho gaya (extreme oversold zone)

2. **Day 4 — RSI recover hona shuru hua**
   - HDFC Bank ₹1,595 pe close, RSI wapas 25 ke upar cross kiya
   - Price ne lower low banaya, lekin RSI ne higher low → **Bullish divergence confirmed!**
   - **Entry:** Long at ₹1,595

3. **Risk Management**
   - ATR(14) = ₹35, ATR Mult = 2.0
   - **Stop Loss:** ₹1,595 − (₹35 × 2.0) = ₹1,525
   - **Take Profit:** ₹1,595 + (₹70 × 2.0 R:R) = ₹1,735

4. **Day 10 — Mean reversion kaam kiya**
   - HDFC Bank recover hokar ₹1,720 pe, buyers ne support pe buy kiya
   - **Take profit hit at ₹1,735**
   - **Result:** +₹140/share (+8.8%)
   - 100 shares pe: **+₹14,000 profit**

**Kyun kaam kiya:** HDFC Bank jaisi large-cap banking stocks extreme RSI ke baad mean revert karti hain. Divergence ne "falling knife" filter kar diya.

**Dhyan rakho:**
- Small-cap/penny stocks pe mat use karo — wo extreme RSI pe bhi girte reh sakte hain.
- RSI 15 ke neeche 3-4 din bina divergence ke = trend breakdown ho sakta hai.
- Banking stocks mein RBI policy se pehle RSI extreme signals zyada aate hain — event risk dhyan mein rakho.

## Notes
- RSI extreme zones mein background green/red highlight hota hai.
- Diamond markers entry signals pe dikhte hain.
- Divergence filter off karne se zyada signals aayenge but selectivity kam hogi.
