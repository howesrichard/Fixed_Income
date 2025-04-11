# Australian Interest Rate Market Instruments: Bank Bills, Bank Bill Futures, FRAs, OIS, and OIS Futures

## Introduction

Australia's short-term interest rate market includes several key instruments that facilitate borrowing, lending, and risk management. This document examines five core instruments: Bank Bills, Bank Bill Futures, Forward Rate Agreements (FRAs), Overnight Index Swaps (OIS), and OIS Futures.   It is important to understand the differences in thinking about yield curve construction and more broadly.

## Bank Bills

### Overview
Bank Bills (also known as Bank Accepted Bills or BABs) are short-term debt instruments issued by corporations and accepted by banks, effectively making them bank-guaranteed instruments. They represent a promise to pay a specific amount at a specified future date.

Bank Bills are very actively traded and the price at which they are traded is used to set BBSW, a key reference rate for floating rate borrowings and for interest rate swap markets.

### Key Characteristics

- **Maturity**: Typically range from 30 to 180 days, with 90-day bills being most common
- **Discount Instruments**: Traded at a discount to face value
- **Credit Quality**: High, due to bank acceptance
- **Benchmark Rate**: The Bank Bill Swap Rate (BBSW) is derived from bank bill trading and serves as a key reference rate for Australian financial markets
- **Liquidity**: Highly liquid in the secondary market
- **Primary Users**: Corporations use them for short-term funding; banks and financial institutions use them for liquidity management

### Pricing
Bank Bills are priced on a yield basis, with the rate reflecting:
- Reserve Bank of Australia (RBA) cash rate expectations
- Bank credit risk
- Liquidity conditions
- Market supply and demand

#### Bank Bill Pricing Formula

Bank Bills are discount securities, priced according to the following formula:

$\text{Price} = \text{Face Value} \times \left(1 - \frac{\text{Yield} \times \text{Days to Maturity}}{365 \times 100}\right)$

Where:
- Price = Present value of the Bank Bill
- Face Value = Nominal value at maturity (typically AUD 1,000,000)
- Yield = Annual interest rate (in percentage)
- Days to Maturity = Actual number of days until the bill matures

The yield can be calculated from the price using:

$\text{Yield} = \frac{(\text{Face Value} - \text{Price}) \times 365 \times 100}{\text{Price} \times \text{Days to Maturity}}$

## Bank Bill Futures

### Overview
Bank Bill Futures are standardized, exchange-traded derivatives contracts based on 90-day Bank Bills. They are traded on the Australian Securities Exchange (ASX) and represent the future delivery of a $1,000,000 face value 90-day Bank Bill.

### Key Characteristics

- **Contract Size**: AUD 1,000,000 nominal value
- **Contract Months**: Quarterly cycle (March, June, September, December) with contracts listed up to 20 quarters forward; serial (monthly) contracts were introduced in November 2024
- **Price Quotation**: 100 minus the yield (e.g., a price of 95.50 equals a yield of 4.50%)
- **Minimum Price Movement**: 0.01% (1 basis point) = AUD 25 per contract
- **Last Trading Day**: Second Friday of the contract month
- **Settlement**: Cash settled based on the 90-day BBSW fixing on the last trading day
- **Trading Hours**: 8:30am to 4:30pm and 5:10pm to 7:00am (Sydney time)

### Uses
- Hedging interest rate exposure
- Speculating on future interest rate movements
- Creating synthetic fixed-rate instruments
- Yield curve trading (spread trading between different contract months)

### Market Structure
The ASX 90-Day Bank Bill Futures market is one of Australia's most liquid financial markets, with significant participation from banks, fund managers, and institutional investors.

## Forward Rate Agreements (FRAs)

### Overview
FRAs are over-the-counter (OTC) contracts between two parties to fix an interest rate for a specified period beginning at a future date. They are cash-settled contracts with no exchange of principal.

### Key Characteristics

- **Contract Terms**: Customizable, non-standardized
- **Market**: OTC (not exchange-traded)
- **Settlement**: Cash settled based on the difference between the contracted rate and the reference rate (typically BBSW)
- **Notional Amount**: Agreed between counterparties
- **Credit Risk**: Counterparty risk exists as they are bilateral agreements
- **Trading**: Direct negotiation between parties or via brokers

### Uses
- Hedging future borrowing or lending exposure
- Locking in future interest rates without committing to actual borrowing or lending
- Customizing hedge periods more precisely than with futures

## Relationships Between Instruments

### Bank Bills vs Bank Bill Futures

1. **Physical vs Derivative**:
   - Bank Bills are actual debt instruments
   - Bank Bill Futures are derivatives that derive value from anticipated Bank Bill rates

2. **Customization vs Standardization**:
   - Bank Bills can have various maturities and amounts
   - Bank Bill Futures have standardized contract specifications

3. **Credit Risk**:
   - Bank Bills carry bank credit risk
   - Bank Bill Futures have minimal counterparty risk due to being a derivative (no principal exhanged) and due to central clearing

### Bank Bill Futures vs FRAs

1. **Exchange-Traded vs OTC**:
   - Bank Bill Futures are exchange-traded with central clearing
   - FRAs are OTC instruments with bilateral counterparty risk

2. **Standardization vs Customization**:
   - Bank Bill Futures have standardized terms
   - FRAs offer customizable terms for specific hedging needs

3. **Margin vs No Margin**:
   - Bank Bill Futures require initial and variation margin
   - FRAs typically don't require initial margin but may have collateral requirements

4. **Liquidity**:
   - Bank Bill Futures generally have higher liquidity and transparency
   - FRAs may offer better terms for specific date requirements

### Pricing Relationships

1. **Arbitrage Link**:
   The pricing relationship between these instruments is maintained through arbitrage:
   - FRAs should theoretically price close to implied rates from Bank Bill Futures of corresponding maturities
   - Differences may exist due to credit quality, liquidity premiums, convixity (discussed below) and contract specifications

2. **Convexity Adjustment**:
   FRAs and Bank Bill Futures with the same reference period have pricing differences due to convexity bias:

   - **Convexity Difference Explained**: Bank Bill Futures contracts are marked-to-market daily, while FRAs are settled based on rates at a single point in time. This creates a fundamental difference in their risk profiles and expected returns.  The conterparty to a FRA which is recieving fixed and paying BBSW enjoys favourable convexity.   When rates rise, her loss is discounted at higher rates wheras when rates fall, her loss is discounted at lower rates.   As such the PV of potential losses will be lower than the PV of potential gains for symmetric moves.
   
   - **Mathematical Basis**: Futures prices have a linear relationship with yields, while FRA values have a non-linear (convex) relationship. When interest rates are volatile, this convexity creates a systematic bias.
   
   - **Practical Impact**: The convexity adjustment is negative for short-term interest rate futures. This means that the implied forward rate from futures prices is generally higher than the true forward rate by an amount that increases with:
     - Higher interest rate volatility
     - Longer time to expiration
     - Steeper yield curves
   
   - **Quantifying the Adjustment**: The convexity adjustment (CA) can be approximated as:

     $\text{CA} \approx -\frac{1}{2} \times \sigma^2 \times t \times T$

     Where:
     - $\sigma$ = Annualized interest rate volatility
     - $t$ = Time to futures expiration
     - $T$ = Tenor of the underlying rate (e.g., 0.25 for 90-day BABs)
   
   - **In Practice**: For short-dated contracts, this adjustment is often negligible, but it becomes increasingly significant for longer-dated contracts, potentially reaching several basis points.

### Bank Bill Futures Pricing Formula

The price of a Bank Bill Future is quoted as:

$\text{Price} = 100 - \text{Yield}$

Where the yield is expressed in percentage terms.

The dollar value of one basis point (0.01%) movement is:

$\text{DV01} = \text{Face Value} \times 0.0001 \times \frac{\text{Days in Period}}{365}$

For a standard 90-day contract with AUD 1,000,000 face value:

$\text{DV01} = 1,000,000 \times 0.0001 \times \frac{90}{365} \approx \text{AUD } 24.66$

The rounded value of AUD 25 is used as the standard tick value.

### FRA Pricing Formula

The theoretical price of an FRA can be expressed as the present value of the difference between the contract rate and the expected reference rate:

$\text{FRA Payment} = \text{Notional Amount} \times (\text{Reference Rate} - \text{FRA Rate}) \times \frac{\text{Days in Period}}{365}$

This payment is typically discounted to present value:

$\text{PV of FRA} = \frac{\text{FRA Payment}}{(1 + \text{Discount Rate} \times \frac{\text{Days to Settlement}}{365})}$

Where:
- Notional Amount = Principal amount of the agreement
- Reference Rate = The actual reference rate (e.g., BBSW) at settlement
- FRA Rate = The fixed rate agreed in the FRA contract
- Days in Period = Number of days in the interest period
- Discount Rate = Rate used to discount the payment to present value
- Days to Settlement = Days until the FRA settlement date

### Implied Forward Rate Calculation

The implied forward rate between two periods can be calculated using:

$$\text{Forward Rate}_{t_1,t_2} = \left(\frac{DF(t_1)}{DF(t_2)} - 1\right) \times \frac{365}{t_2 - t_1}$$


Where:
- $DF(t_1)$ = the discount factor at $t_1$
- $DF(t_2)$ = the discount factor at $t_2$
- $t_1$ = Number of days to the near date
- $t_2$ = Number of days to the far date

## Overnight Index Swaps (OIS)

### Overview
Overnight Index Swaps (OIS) are interest rate swap contracts where a fixed rate is exchanged for a floating rate based on a compounded overnight interbank cash rate, the Reserve Bank of Australia (RBA) cash rate in Australia's case. OIS has grown in importance as a key benchmark for risk-free rates.

### Key Characteristics

- **Reference Rate**: RBA overnight cash rate (compounded)
- **Tenor**: Range from 1 week to 2 years typically, with longer tenors possible
- **Payment Frequency**: Single payment at maturity (for short tenors)
- **Market Structure**: OTC market with customizable terms
- **Credit Risk**: Minimal, as only interest differentials are exchanged, not principal
- **Calculation Method**: Geometric compounding of the overnight rates over the calculation period

### Uses
- Hedging overnight cash rate exposure
- Speculating on RBA monetary policy decisions
- Deriving market expectations of future RBA cash rate movements
- Funding for financial institutions
- Creating term structures and yield curves of risk-free rates

### Pricing Formula

The fixed rate of an OIS is priced to reflect the expected geometric average of the overnight cash rate over the term of the swap:

$\text{OIS Rate} = \left[\prod_{i=1}^{n}(1 + r_i \times \frac{d_i}{365}) \right]^{\frac{365}{\sum d_i}} - 1$

Where:
- $r_i$ = Overnight cash rate for period $i$
- $d_i$ = Number of days the rate $r_i$ applies
- $n$ = Number of overnight periods

The present value of an OIS can be calculated as:

$\text{PV} = \text{Notional} \times (\text{Fixed Rate} - \text{Realized OIS Rate}) \times \frac{\sum d_i}{365} \times \text{Discount Factor}$

#### Discount Factor Calculation

The Discount Factor in the OIS pricing formula above represents the present value of a future payment and accounts for the time value of money. It can be calculated using the following methods:

1. **Using Zero Rates**:
   $\text{Discount Factor} = \frac{1}{(1 + z \times \frac{t}{365})}$
   
   Where:
   - $z$ = Zero rate for the relevant tenor
   - $t$ = Number of days to payment date

2. **Using OIS Curve**:
   For more accurate pricing, the Discount Factor is derived from the OIS curve itself:
   
   $\text{Discount Factor} = e^{-r_{OIS} \times \frac{t}{365}}$
   
   Where:
   - $r_{OIS}$ = Continuously compounded OIS rate for tenor $t$
   - $t$ = Number of days to payment date

3. **Bootstrapping Method**:
   For longer tenors, Discount Factors are often calculated through bootstrapping, where shorter tenor Discount Factors are used to derive longer tenor ones recursively from observed market rates.

The choice of method depends on market convention, available data, and the specific application of the OIS valuation.

## ASX 30-Day Interbank Cash Rate Futures (OIS Futures)

### Overview
The ASX 30-Day Interbank Cash Rate Futures contracts are exchange-traded derivatives based on the average RBA cash rate over a calendar month. These are effectively futures on the compounded overnight cash rate.

### Key Characteristics

- **Contract Size**: AUD 3,000,000 nominal value
- **Contract Months**: Monthly, up to 18 months forward
- **Price Quotation**: 100 minus the average cash rate (e.g., a price of 97.00 equals a rate of 3.00%)
- **Minimum Price Movement**: 0.01% (1 basis point) = AUD 24.66 per contract (rounded to AUD 25)
- **Last Trading Day**: First business day after the last business day of the contract month
- **Settlement**: Cash settled based on the monthly average of the RBA overnight cash rate
- **Trading Hours**: 8:30am to 4:30pm and 5:10pm to 7:00am (Sydney time)

### Uses
- Hedging overnight rate exposure
- Trading RBA monetary policy expectations
- Creating synthetic fixed-rate instruments
- Spread trading against Bank Bill Futures

### Pricing Formula

The price of an OIS Future is quoted as:

$\text{Price} = 100 - \text{Expected Average Cash Rate}$

Where the expected average cash rate is the anticipated geometric average of the RBA cash rate over the contract month.

The final settlement price is determined by:

$\text{Settlement Price} = 100 - \left[\frac{100}{n} \times \sum_{i=1}^{n} r_i \right]$

Where:
- $r_i$ = Official RBA cash rate on day $i$
- $n$ = Number of days in the calculation period (calendar month)

## Relationships Between All Instruments

### OIS vs Bank Bill Rates

1. **Credit Risk Difference**:
   - OIS rates reflect near risk-free rates (minimal credit risk)
   - Bank Bill rates incorporate bank credit risk
   - The spread between BBSW and OIS rates (known as the "BBSW-OIS spread") is a key indicator of banking sector stress

2. **Use as Benchmarks**:
   - OIS rates serve as risk-free rate benchmarks
   - BBSW serves as the bank credit-based benchmark rate

### OIS Futures vs Bank Bill Futures

1. **Underlying Rate**:
   - OIS Futures are based on the RBA cash rate
   - Bank Bill Futures are based on BBSW

2. **Term Structure**:
   - OIS Futures typically focus on shorter-term rates
   - Bank Bill Futures extend further along the curve

3. **Risk Profiles**:
   - OIS Futures have minimal credit risk component
   - Bank Bill Futures incorporate bank credit risk

4. **Contract Specifications**:
   - OIS Futures are based on monthly averages of daily rates
   - Bank Bill Futures are based on the 90-day rate on a specific day

### Forward Rate Agreements vs OIS

1. **Reference Rate**:
   - FRAs typically reference BBSW
   - OIS references the RBA cash rate

2. **Risk Profile**:
   - FRAs incorporate credit risk
   - OIS has minimal credit risk

3. **Term Structure**:
   - FRAs typically target specific forward periods
   - OIS can be structured for various terms but is most liquid in shorter tenors

## Conclusion

These five instruments—Bank Bills, Bank Bill Futures, FRAs, OIS, and OIS Futures—form a comprehensive ecosystem for short-term interest rate risk management in Australia. Market participants choose between them based on specific needs related to credit risk profiles, standardization, liquidity, and customization requirements.

Bank Bill Futures serve as the primary exchange-traded credit-based interest rate benchmark in Australia, while OIS and OIS Futures provide the risk-free rate benchmark. FRAs offer customizable OTC solutions, and Bank Bills provide the underlying physical market that anchors the credit-based derivatives marketplace.

Understanding the relationships and pricing differences between these instruments is crucial for effective interest rate risk management and for developing appropriate trading and hedging strategies in the Australian financial market.