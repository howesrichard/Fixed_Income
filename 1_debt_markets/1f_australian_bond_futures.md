# ASX Bond Futures Contracts

## Overview

ASX Bond Futures are standardized derivative contracts that enable market participants to manage interest rate risk, speculate on interest rate movements, and implement various trading strategies in the Australian fixed income market. These contracts are based on Australian government bonds (Commonwealth Government Securities) and are among the most liquid interest rate derivatives in the Asia-Pacific region.

## Contract Specifications

Below is a table of the key contract specifications for the main ASX Bond Futures contracts:

| Feature | 3-Year Bond Futures | 10-Year Bond Futures | 20-Year Bond Futures |
|---------|-------------------|---------------------|---------------------|
| **ASX Code** | YT | XT | LL |
| **Underlying** | Commonwealth Government Treasury Bond with a face value of A$100,000 and a coupon rate of 6% p.a. | Commonwealth Government Treasury Bond with a face value of A$100,000 and a coupon rate of 6% p.a. | Commonwealth Government Treasury Bond with a face value of A$100,000 and a coupon rate of 4% p.a. |
| **Contract Unit** | A$100,000 face value | A$100,000 face value | A$100,000 face value |
| **Contract Months** | March, June, September, December (up to 6 quarters ahead) | March, June, September, December (up to 6 quarters ahead) | March, June, September, December (up to 6 quarters ahead) |
| **Price Quotation** | Yield to maturity expressed as 100 minus yield (e.g., a yield of 4.5% = price of 95.5) | Yield to maturity expressed as 100 minus yield (e.g., a yield of 4.5% = price of 95.5) | Yield to maturity expressed as 100 minus yield (e.g., a yield of 4.5% = price of 95.5) |
| **Minimum Price Movement** | 0.005 (0.5 basis points) = A$15.00 | 0.005 (0.5 basis points) = A$24.90 approx. | 0.005 (0.5 basis points) = A$39.15 approx. |
| **Trading Hours** | 8:30am - 4:30pm (AEST/AEDT) | 8:30am - 4:30pm (AEST/AEDT) | 8:30am - 4:30pm (AEST/AEDT) |
| **Last Trading Day** | 12:00pm on the business day prior to settlement day | 12:00pm on the business day prior to settlement day | 12:00pm on the business day prior to settlement day |
| **Settlement Day** | The first business day after the last trading day | The first business day after the last trading day | The first business day after the last trading day |
| **Settlement Method** | Cash settled | Cash settled | Cash settled |

## Pricing and Valuation

ASX Bond Futures are quoted in terms of yield, with the price being expressed as 100 minus the yield. The conversion between price and dollar value requires understanding bond mathematics.

### Pricing Formula

The pricing of ASX Bond Futures involves converting the futures price (expressed as 100 minus yield) to a dollar value. The key steps are:

1. Convert futures price to yield:
   ```
   Yield = 100 - Futures Price
   ```

2. Calculate the cash settlement price using the bond pricing formula:
   ```
   Cash Price = Face Value × [c(1 - (1 + y)^(-n))/y + (1 + y)^(-n)]
   ```
   
   Where:
   - c = Coupon rate (e.g., 0.06 for 6%)
   - y = Yield to maturity (semi-annual) / 2
   - n = Number of semi-annual periods (e.g., 6 for 3-year bond)
   - Face Value = A$100,000

3. Calculate the futures contract dollar value:
   ```
   Dollar Value = Cash Price + Accrued Interest
   ```

### Price Factor (Conversion Factor)

The ASX uses standardized conversion factors for each contract, which accounts for the difference between the standardized 6% coupon of the futures contract and the actual coupon rates of deliverable bonds.

### Duration and DV01

The dollar value of a basis point (DV01) is an important risk measure:

- 3-Year Bond Futures: Approximately A$30.00 per basis point per contract
- 10-Year Bond Futures: Approximately A$49.80 per basis point per contract
- 20-Year Bond Futures: Approximately A$78.30 per basis point per contract

## Uses and Applications

ASX Bond Futures serve several important functions in financial markets:

### 1. Risk Management (Hedging)

- **Interest Rate Risk**: Financial institutions use bond futures to hedge against adverse interest rate movements in their fixed-income portfolios.
- **Asset-Liability Management**: Pension funds and insurance companies use these contracts to match the duration of their assets with their liabilities.
- **Mortgage Pipeline Hedging**: Mortgage originators use bond futures to hedge interest rate risk during the loan origination process.

### 2. Speculation

- Traders take directional positions on interest rates based on their macroeconomic outlook.
- The high liquidity and leverage available make these contracts attractive for speculative trading.

### 3. Relative Value Trading

- **Yield Curve Trades**: Spread trades between different tenor bond futures (e.g., 3s/10s spread) to capitalize on expected changes in the yield curve.
- **Basis Trading**: Trading the spread between bond futures and physical bonds to exploit pricing inefficiencies.

### 4. Investment Strategy Implementation

- **Duration Management**: Active portfolio managers adjust their portfolio duration using bond futures.
- **Asset Allocation**: Strategic and tactical asset allocation shifts between fixed income and other asset classes.

## Settlement Process

ASX Bond Futures are cash-settled contracts, meaning there is no physical delivery of the underlying bonds. Instead, they are settled in cash based on the difference between the contract price and the settlement price.

### Settlement Rate Determination

The settlement rate for ASX Bond Futures is determined through a sophisticated process:

1. **YCAS Methodology**: The settlement price is determined using the ASX Yield Curve Adjustment Settlement (YCAS) methodology.

2. **Calculation Process**:
   - On the last trading day, the ASX takes a sample of quotations from designated market makers for specific Commonwealth Government Securities.
   - These quotations are collected for a basket of bonds within the relevant maturity range.
   - For 3-Year Bond Futures, bonds with maturities between 2.5 and 3.5 years are sampled.
   - For 10-Year Bond Futures, bonds with maturities between 9 and 11 years are sampled.
   - For 20-Year Bond Futures, bonds with maturities between 15 and 25 years are sampled.

3. **Yield Curve Construction**:
   - A yield curve is constructed from these quotations.
   - The YCAS methodology applies statistical techniques to fit a smoothed yield curve.
   - For the 3-Year contract, the 3-year point on this curve becomes the settlement yield.
   - For the 10-Year contract, the 10-year point on this curve becomes the settlement yield.
   - For the 20-Year contract, the 20-year point on this curve becomes the settlement yield.

4. **Final Settlement Price**:
   - The settlement yield is converted to a price using the formula: Settlement Price = 100 - Settlement Yield.
   - This price is used for cash settlement of all open positions.

### Settlement Timing

- The final settlement price is announced by the ASX on the afternoon of the last trading day.
- Cash settlement occurs on the next business day.
- Market participants with open positions have their accounts automatically debited or credited based on their positions and the settlement price.

## Current Bond Baskets and Bloomberg Codes

The ASX bond futures contracts are based on baskets of Australian Commonwealth Government Securities (ACGS). Below are recent but not current bond baskets for each contract with their respective Bloomberg codes:

### 3-Year Bond Futures Basket

| Bond | Maturity Date | Coupon (%) | Bloomberg Code |
|------|--------------|------------|---------------|
| ACGB 4.25% | 21 Apr 2026 | 4.25 | GT126268 Corp |
| ACGB 3.25% | 21 Nov 2026 | 3.25 | GT131178 Corp |
| ACGB 2.75% | 21 Apr 2027 | 2.75 | GT142164 Corp |
| ACGB 4.75% | 21 Nov 2027 | 4.75 | GT146158 Corp |
| ACGB 3.00% | 21 Apr 2028 | 3.00 | GT153147 Corp |

### 10-Year Bond Futures Basket

| Bond | Maturity Date | Coupon (%) | Bloomberg Code |
|------|--------------|------------|---------------|
| ACGB 2.75% | 21 Nov 2032 | 2.75 | GT178093 Corp |
| ACGB 3.25% | 21 Apr 2033 | 3.25 | GT182095 Corp |
| ACGB 3.75% | 21 Apr 2034 | 3.75 | GT186061 Corp |
| ACGB 4.25% | 21 Nov 2034 | 4.25 | GT189072 Corp |
| ACGB 3.00% | 21 Nov 2035 | 3.00 | GT194087 Corp |

### 20-Year Bond Futures Basket

| Bond | Maturity Date | Coupon (%) | Bloomberg Code |
|------|--------------|------------|---------------|
| ACGB 3.25% | 21 Apr 2039 | 3.25 | GT217064 Corp |
| ACGB 3.75% | 21 Apr 2041 | 3.75 | GT223045 Corp |
| ACGB 2.75% | 21 Nov 2042 | 2.75 | GT231036 Corp |
| ACGB 3.50% | 21 Apr 2044 | 3.50 | GT237033 Corp |
| ACGB 4.75% | 21 Apr 2047 | 4.75 | GT245056 Corp |
| ACGB 3.75% | 21 Apr 2050 | 3.75 | GT249058 Corp |

### Conversion Factors

Each bond in the basket has a conversion factor that adjusts for the difference between the bond's actual coupon and the notional coupon of the futures contract (6% for 3-year and 10-year, 4% for 20-year). These conversion factors are published by the ASX and updated quarterly.

## Market Participants

Various market participants engage in ASX Bond Futures trading:

- **Banks and Financial Institutions**: For proprietary trading and client facilitation
- **Hedge Funds**: For directional and relative value strategies
- **Asset Managers**: For portfolio hedging and yield enhancement
- **Insurance Companies and Pension Funds**: For liability-driven investment strategies
- **Corporate Treasuries**: For interest rate risk management

## Advantages of ASX Bond Futures

- **Liquidity**: The ASX Bond Futures market is highly liquid, allowing for easy entry and exit.
- **Capital Efficiency**: Trading futures requires less capital than dealing in the physical bond market.
- **Standardization**: Standardized contracts simplify trading and risk assessment.
- **Central Clearing**: ASX Clear (Futures) acts as the central counterparty, eliminating counterparty risk.
- **Transparent Pricing**: Futures prices provide a transparent benchmark for interest rates.

## Regulatory Framework

ASX Bond Futures are regulated by the Australian Securities and Investments Commission (ASIC) and operate under the rules of the ASX. The market is supervised to ensure fair and orderly trading, with various safeguards in place to maintain market integrity, including position limits and margin requirements.

## Historical Context

Bond futures were introduced on the ASX (then the Sydney Futures Exchange) in 1979 with the 10-Year Treasury Bond Futures contract. The 3-Year Treasury Bond Futures were added in 1986, and the 20-Year Treasury Bond Futures were launched in 2003. These contracts have grown to become key benchmarks for Australian interest rates and essential tools for managing interest rate risk.