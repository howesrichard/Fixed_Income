# Bond Basis Trading Strategy for ASX Bond Futures

## Introduction to Bond Basis Trading

Bond basis trading for ASX bond futures is a specialized arbitrage strategy that exploits pricing inefficiencies between ASX bond futures contracts and their underlying basket of physical bonds. Unlike many international bond futures that use physical delivery with a cheapest-to-deliver (CTD) mechanism, ASX bond futures use cash settlement based on a yield curve derived from a basket of bonds. This creates unique trading opportunities focused on the relationship between the futures contract and the entire basket of bonds.

## Key Concepts

### 1. The Australian Bond Futures Basis

For ASX bond futures, the "basis" refers to the difference between:
1. The actual market yield curve derived from the underlying basket of bonds
2. The implied yield curve from the futures contract

Unlike traditional bond futures markets where the basis focuses on a single cheapest-to-deliver bond, the ASX basis considers the entire basket of bonds and the YCAS (Yield Curve Adjustment Settlement) methodology.

### 2. YCAS Settlement Mechanism

The ASX uses the YCAS methodology for settlement, which:
- Takes quotations from designated market makers for all bonds in the relevant basket
- Constructs a smoothed yield curve from these quotations
- Determines the settlement yield from the relevant point on this curve (3-year, 10-year, or 20-year)
- Converts this yield to a price using: Settlement Price = 100 - Settlement Yield

### 3. Net Basis

The net basis incorporates carrying costs (funding costs minus coupon income), expressed in yield terms:

```
Net Basis = Futures Implied Yield - Actual Yield at Maturity Point - Annualized Cost of Carry
```

### 3. Net Basis

The net basis incorporates carrying costs (funding costs minus coupon income):

```
Net Basis = Basis - Carrying Cost
```

## Bond Basis Trading Strategies

### 1. Long Basis Trade

- **Position**: Long physical bond + Short futures contract
- **Profit Scenario**: When the basis widens (becomes more positive)
- **Risk**: Basis narrows (becomes more negative)

### 2. Short Basis Trade

- **Position**: Short physical bond + Long futures contract
- **Profit Scenario**: When the basis narrows (becomes more negative)
- **Risk**: Basis widens (becomes more positive)

## Worked Example with 10-Year ASX Bond Futures

Let's walk through a complete example of a bond basis trade using the 10-Year ASX Bond Futures and its constituent basket.

### Step 1: Identify the Current Bond Basket

From the 10-Year Bond Futures basket:

| Bond | Maturity Date | Coupon (%) | Bloomberg Code | Conversion Factor |
|------|--------------|------------|---------------|-------------------|
| ACGB 2.75% | 21 Nov 2032 | 2.75 | GT178093 Corp | 0.8127 |
| ACGB 3.25% | 21 Apr 2033 | 3.25 | GT182095 Corp | 0.8436 |
| ACGB 3.75% | 21 Apr 2034 | 3.75 | GT186061 Corp | 0.8752 |
| ACGB 4.25% | 21 Nov 2034 | 4.25 | GT189072 Corp | 0.9064 |
| ACGB 3.00% | 21 Nov 2035 | 3.00 | GT194087 Corp | 0.8291 |

### Step 2: Gather Current Market Data

For this worked example, we'll use the June 2025 contract with the following actual bond basket as specified for the ASX 10-Year Treasury Bond Futures contract:

- ASX 10-Year Futures Price (June 2025 contract): 95.880 (yield of 4.12%)
- Settlement Date: 15 Jun 2025
- Current Date: 11 Apr 2025
- 3-month bank bill swap rate: 4.30%

Current 10-Year Bond Basket for June 2025 Contract:

| Bond | Maturity Date | Coupon (%) | Current Price | Current Yield (%) |
|------|--------------|------------|--------------|-----------------|
| ACGB 3.75% | 21 May 2034 | 3.75 | 96.53 | 4.28 |
| ACGB 3.50% | 21 Dec 2034 | 3.50 | 95.12 | 4.31 |
| ACGB 2.75% | 21 Jun 2035 | 2.75 | 89.23 | 4.33 |
| ACGB 4.25% | 21 Dec 2035 | 4.25 | 99.56 | 4.35 |
| ACGB 3.75% | 21 Apr 2037 | 3.75 | 95.04 | 4.38 |

Accrued interest:
- ACGB 3.75% May 2034: 1.6233
- ACGB 3.50% Dec 2034: 1.3151
- ACGB 2.75% Jun 2035: 0.9075
- ACGB 4.25% Dec 2035: 1.5953
- ACGB 3.75% Apr 2037: 1.7260

### Step 3: Calculate the Implied Yield Curve

Using the current bond prices and yields, we can construct the implied 10-year yield curve:

| Bond | Maturity (years) | Yield (%) |
|------|-----------------|-----------|
| ACGB 3.75% May 2034 | 9.11 | 4.28 |
| ACGB 3.50% Dec 2034 | 9.70 | 4.31 |
| ACGB 2.75% Jun 2035 | 10.20 | 4.33 |
| ACGB 4.25% Dec 2035 | 10.70 | 4.35 |
| ACGB 3.75% Apr 2037 | 12.03 | 4.38 |

Since we need the 10-year yield (exactly 10 years from now, April 2035), we can interpolate between the May 2034 and June 2035 bonds:

10-year yield = 4.28% + (10.00 - 9.11) / (10.20 - 9.11) × (4.33% - 4.28%) = 4.32%

### Step 4: Calculate the Basis

For ASX bond futures, the basis is defined as the difference between the implied futures yield and the actual yield curve at the corresponding maturity point:

```
Basis (in yield terms) = Futures Implied Yield - Actual Yield at Maturity Point
```

Futures Implied Yield = 100 - Futures Price = 100 - 95.880 = 4.12%
Actual 10-Year Yield (from our curve) = 4.32%

Basis = 4.12% - 4.32% = -0.20% (20 basis points)

A negative basis of 20 basis points means the futures contract is trading at a higher price (lower yield) than what the physical bond basket implies.

### Step 5: Calculate Carrying Costs for a Basket-Based Strategy

For ASX bond futures, a typical basis trade involves acquiring a weighted basket of bonds that approximates the YCAS settlement methodology. We'll calculate carrying costs for a portfolio weighted to match the 10-year point on the yield curve:

Portfolio Construction:
- Weighted towards bonds closest to the 10-year maturity
- Total portfolio value: $10 million face value

Bond Allocation:
- ACGB 3.75% May 2034: 25% ($2.5 million)
- ACGB 3.50% Dec 2034: 30% ($3 million)
- ACGB 2.75% Jun 2035: 25% ($2.5 million)
- ACGB 4.25% Dec 2035: 15% ($1.5 million)
- ACGB 3.75% Apr 2037: 5% ($0.5 million)

Weighted Average Portfolio Statistics:
- Weighted Price: 94.23
- Weighted Accrued Interest: 1.3374
- Weighted Yield: 4.32%
- Weighted Coupon: 3.41%
- Weighted Modified Duration: 8.25

Funding Cost:
- Portfolio Investment: $10 million × (94.23 + 1.3374)/100 = $9,556,740
- Funding Period: 2 months (0.1667 years)
- Bank Bill Swap Rate: 4.30%
- Funding Cost = $9,556,740 × 4.30% × 0.1667 = $68,488

Coupon Income:
- Weighted Annual Coupon = 3.41%
- Income for 2 months = 3.41% × 0.1667 × $10 million = $56,845

Net Carrying Cost = Funding Cost - Coupon Income = $68,488 - $56,845 = $11,643

### Step 6: Calculate the Net Basis

For ASX bond futures, we express the net basis in yield terms, adjusting for the cost of carry:

```
Net Basis (yield terms) = Basis - Annualized Cost of Carry
```

Annualized Cost of Carry = ($11,643 / $9,556,740) × 6 = 0.73%

Net Basis = -0.20% - 0.73% = -0.93%

The significantly negative net basis indicates potential profitability in a short basis trade (buy futures, sell bonds).

### Step 7: Implement the Trade

Since we have a significant negative net basis, we would implement a short basis trade:

1. Sell the weighted basket of bonds totaling $10 million face value
2. Buy ASX 10-Year Bond Futures (June 2025) at 95.880

### Step 8: Calculate Hedge Ratio

For ASX bond futures, the hedge ratio calculation needs to account for the basket approach:

```
Hedge Ratio = (Bond Portfolio DV01) / (Futures DV01)
```

Assuming:
- Weighted Portfolio DV01: $82.50 per $100,000 face value (based on modified duration of 8.25)
- Futures DV01: $50.20 per contract
- Bond Position: $10 million face value

Hedge Ratio = ($10,000,000 × $82.50/$100,000) / $50.20 = 164.34

So we would buy 164 futures contracts to hedge our $10 million bond basket position.

### Step 9: Profit/Loss Scenarios

**Scenario 1: Basis Converges to Zero at Expiry**
- Initial Basis: -0.20% (20 basis points)
- Final Basis: 0
- Portfolio Modified Duration: 8.25
- Profit on Physical Bond Portfolio: -20bp × 8.25 = -1.65 points = -$165,000
- Profit on Futures: 20bp × 164 contracts × $50.20/bp = $164,656
- Net Loss: -$344
- Less Carrying Cost: -$11,643
- Total Loss: -$11,987

**Scenario 2: Basis Widens by 10 basis points**
- Change in Basis: -0.20% to -0.30% (additional 10bp)
- Profit on Physical Bond Portfolio: +10bp × 8.25 = +0.825 points = +$82,500
- Loss on Futures: -10bp × 164 contracts × $50.20/bp = -$82,328
- Net Profit: $172
- Less Carrying Cost: -$11,643
- Total Loss: -$11,471

**Scenario 3: Basis Narrows to Zero**
- Change in Basis: -0.20% to 0% (narrowing by 20bp)
- Loss on Physical Bond Portfolio: -20bp × 8.25 = -1.65 points = -$165,000
- Profit on Futures: +20bp × 164 contracts × $50.20/bp = +$164,656
- Net Loss: -$344
- Less Carrying Cost: -$11,643
- Total Loss: -$11,987

**Scenario 4: Basis Narrows and Inverts to +10bp**
- Change in Basis: -0.20% to +0.10% (narrowing by 30bp)
- Loss on Physical Bond Portfolio: -30bp × 8.25 = -2.475 points = -$247,500
- Profit on Futures: +30bp × 164 contracts × $50.20/bp = +$246,984
- Net Loss: -$516
- Less Carrying Cost: -$11,643
- Total Loss: -$12,159

**Scenario 5: Basis Widens Significantly to -60bp**
- Change in Basis: -0.20% to -0.60% (widening by 40bp)
- Profit on Physical Bond Portfolio: +40bp × 8.25 = +3.30 points = +$330,000
- Loss on Futures: -40bp × 164 contracts × $50.20/bp = -$329,312
- Net Profit: $688
- Less Carrying Cost: -$11,643
- Total Loss: -$10,955

In this example, the relatively large negative basis (-20bp) is not quite enough to overcome the carrying costs for a 2-month holding period. However, if the trade were held for a shorter period or if the basis were to widen further, the strategy could become profitable.

In practice, basis traders would typically look for more extreme basis levels or expect significant widening before implementing the trade. Alternatively, they might employ financing strategies (such as repo agreements) to reduce carrying costs and improve the profitability of the trade.

## Risk Factors in ASX Bond Basis Trading

### 1. YCAS Methodology Risk

The ASX YCAS settlement methodology introduces unique risks as it uses a curve-fitting approach rather than physical delivery of a specific bond. Market participants may have different interpretations of how the YCAS will derive the final settlement yield.

### 2. Yield Curve Risk

Non-parallel shifts in the yield curve can affect different bonds in the basket differently, potentially changing the settlement yield in unexpected ways. Since the ASX settlement is based on the entire curve, this risk is more pronounced than in physical delivery futures markets.

### 3. Funding Risk

Changes in short-term interest rates can affect the carrying cost and profitability of the trade.

### 4. Liquidity Risk

Reduced liquidity in either the physical bond or futures market can widen bid-ask spreads and impact execution.

### 5. Basket Composition Risk

The specific bonds included in the YCAS basket can change over time as new bonds are issued and older ones approach maturity, potentially altering the basis relationship.

## Bond Basis Trading in Practice for ASX Futures

### Market Conditions Favorable for ASX Basis Trading

1. **Yield Curve Distortions**: When specific points on the yield curve become distorted relative to the smooth curve used in YCAS settlement.
2. **Supply/Demand Imbalances**: When there is strong demand for futures relative to the physical bonds or vice versa.
3. **Central Bank Operations**: Reserve Bank of Australia interventions can create distortions in the relative pricing.
4. **Quarter-End Effects**: The ASX futures roll periods often create temporary dislocations in pricing.
5. **Issuance Cycles**: New bond issuance can temporarily distort the yield curve and create basis trading opportunities.

### Key Success Factors

1. **Yield Curve Expertise**: Deep understanding of the Australian government bond yield curve and YCAS methodology.
2. **Portfolio Construction**: Ability to create and manage a basket of bonds that closely mimics the YCAS settlement process.
3. **Efficient Execution**: Minimizing transaction costs through efficient execution across multiple bonds.
4. **Appropriate Hedging**: Proper risk management through accurate hedge ratios for the entire bond basket.
5. **Market Timing**: Understanding seasonal patterns in the basis, particularly around futures expiry periods.

## Conclusion

ASX bond basis trading differs significantly from basis trading in physical delivery markets like US Treasury futures. The ASX cash settlement mechanism based on the YCAS methodology creates unique opportunities and risks. Successful ASX basis traders focus on understanding the entire yield curve rather than just identifying a single cheapest-to-deliver bond.

This strategy requires sophisticated yield curve analysis, careful portfolio construction, and understanding of the YCAS settlement process. When executed properly, it can provide consistent returns with limited directional risk. The strategy is particularly attractive to market participants with natural advantages in Australian dollar funding costs or bond inventory, such as Australian banks, primary dealers, and fixed income asset managers specializing in Australian markets.