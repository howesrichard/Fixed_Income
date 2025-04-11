# Understanding Yield Curve Bootstrapping

## Introduction

Yield curve bootstrapping is a fundamental technique in financial mathematics used to derive the zero-coupon yield curve (also called the spot rate curve or zero curve) from the observed market prices of fixed income instruments. This process is essential for pricing derivatives, valuing bonds, and risk management in financial institutions.

This document revisits and explains the bootstrapping process as implemented in the `FM_yield_curve` repository, providing both theoretical background and practical implementation details.

## Key Concepts

Before diving into the bootstrapping procedure, it's important to check we understand some key concepts:

### Zero-Coupon Rates

A zero-coupon rate (or spot rate) is the yield on a zero-coupon bond, which is a bond that doesn't pay any coupons and only makes a single payment at maturity. The zero curve represents these rates across different maturities.

### Discount Factors

A discount factor is the present value of 1 unit of currency received at a future date. If $r_t$ is the continuously compounded zero rate for maturity $t$, then the discount factor $D(t)$ is:

$D(t) = e^{-r_t \cdot t}$

Alternatively, with the amount at maturity $A(t) = e^{r_t \cdot t}$, the discount factor is:

$D(t) = \frac{1}{A(t)}$

### Bootstrapping

Bootstrapping is an iterative process that uses market instruments of increasing maturities to build a zero curve step by step. The key idea is to use the information from shorter-term instruments to price and extract rates from longer-term instruments.

## The Bootstrapping Process

The bootstrapping process implemented in this repository follows these steps:

1. **Start with short-term instruments**: Begin with bank bills (or Treasury bills) which are essentially zero-coupon instruments.
2. **Extract discount factors**: For these short-term instruments, extract discount factors directly from their prices.
3. **Proceed to coupon-bearing bonds**: Move to bonds with coupon payments, using the already-determined discount factors for the coupon payments.
4. **Solve for the unknown discount factor**: For each new bond, there will be one unknown discount factor (for its maturity date). Solve for this factor.
5. **Continue the process**: Repeat steps 3-4 for bonds of increasing maturities.

## Implementation in the Repository

The repository implements the bootstrapping process using several Python classes:

### Core Classes

1. **ZeroCurve Class**
   - Stores zero rates, discount factors, and amounts at maturity
   - Provides methods for interpolation between known points
   - Handles conversion between different curve representations

2. **YieldCurve Class** (inherits from ZeroCurve)
   - Implements the bootstrapping algorithm
   - Manages a portfolio of instruments used for bootstrapping

3. **Financial Instruments**
   - `CashFlows`: Base class for handling payment streams
   - `Bank_bill`: Short-term zero-coupon instruments
   - `Bond`: Coupon-bearing bonds
   - `Portfolio`: Collection of financial instruments

### Bootstrapping Algorithm

The actual bootstrapping is implemented in the `bootstrap()` method of the `YieldCurve` class:

```python
def bootstrap(self):
    bank_bills = self.portfolio.get_bank_bills()
    bonds = self.portfolio.get_bonds()
    
    # Start with zero rate at time 0
    self.add_zero_rate(0,0)
    
    # First, extract rates from bank bills (zero-coupon instruments)
    for bank_bill in bank_bills:
        self.add_discount_factor(
            bank_bill.get_maturity(),
            bank_bill.get_price()/bank_bill.get_face_value()
        )
    
    # Then, proceed to coupon-bearing bonds
    for bond in bonds:
        # Calculate the PV of the bond cashflows excluding the maturity cashflow
        pv = 0
        bond_dates = bond.get_maturities()
        bond_amounts = bond.get_amounts()
        
        # Sum all intermediate cash flows (coupons) using known discount factors
        for i in range(1, len(bond_amounts)-1):
            pv += bond_amounts[i]*self.get_discount_factor(bond_dates[i])
        
        # Solve for the discount factor at the bond's maturity
        self.add_discount_factor(
            bond.get_maturity(),
            (bond.get_price()-pv)/bond.get_amounts()[-1]
        )
```

## Step-by-Step Walkthrough of the Process

Let's walk through the bootstrapping process with a concrete example based on the implementation:

### 1. Initial Setup

We start with an empty yield curve and a portfolio of financial instruments sorted by maturity:
- Short-term bank bills (e.g., 3-month, 6-month)
- Bonds of increasing maturities (e.g., 1-year, 2-year, etc.)

### 2. Adding Bank Bills

For each bank bill, we directly compute its discount factor from the price:

```
Discount Factor = Price / Face Value
```

For a 3-month (0.25-year) bank bill with a face value of 100 and a price of 98.75:
```
Discount Factor(0.25) = 98.75 / 100 = 0.9875
```

We can then convert this to a zero rate:
```
Zero Rate(0.25) = -ln(0.9875) / 0.25 = 0.0503 or 5.03%
```

### 3. Adding Bonds

For a 1-year bond with semi-annual coupons of 3% (1.5% per period) and a face value of 100:

1. We already know the discount factors for times ≤ 0.5 years from our bank bills
2. We can discount all cash flows except the final one:
   ```
   PV(coupons) = 1.5 * DF(0.5)
   ```
3. The remaining value must be the final cash flow times its discount factor:
   ```
   Price - PV(coupons) = (1.5 + 100) * DF(1)
   ```
4. We solve for DF(1):
   ```
   DF(1) = (Price - PV(coupons)) / 101.5
   ```
5. We convert this discount factor to a zero rate:
   ```
   Zero Rate(1) = -ln(DF(1)) / 1
   ```

### 4. Continuing the Process

We continue this process for bonds of increasing maturities, always using the discount factors we've already calculated to value the known cash flows, and then solving for the one remaining unknown discount factor.

## Interpolation for Missing Points

In practice, we don't have instruments for every possible maturity. The repository implements exponential interpolation to fill in gaps:

```python
def exp_interp(xs, ys, x):
    """
    Interpolates using continuously compounded rates.
    """
    # Find the interval [x0, x1] where x0 <= x <= x1
    idx = np.searchsorted(xs, x) - 1
    x0, x1 = xs[idx], xs[idx + 1]
    y0, y1 = ys[idx], ys[idx + 1]
    
    # Calculate the continuously compounded rate
    rate = (np.log(y1) - np.log(y0)) / (x1 - x0)
    
    # Interpolate the y value for the given x
    y = y0 * np.exp(rate * (x - x0))
    
    return y
```

This ensures that the interpolated values are consistent with continuous compounding.

## Applications of the Bootstrapped Yield Curve

Once constructed, the zero curve can be used for:

1. **Pricing fixed income securities**: By discounting cash flows using the appropriate zero rates
2. **Constructing forward curves**: To determine implied future interest rates
3. **Valuing interest rate derivatives**: Such as swaps, caps, and floors
4. **Risk management**: For analyzing duration, convexity, and other interest rate risk measures
5. **Policy analysis**: For central banks and market analysts to interpret market expectations

## Limitations and Considerations

While bootstrapping is a powerful technique, it has some limitations:

1. **Data availability**: Requires a sufficient number of liquid instruments across the yield curve
2. **Interpolation errors**: The choice of interpolation method can affect the results
3. **Market microstructure issues**: Bid-ask spreads, liquidity premiums, and other factors can distort prices
4. **Consistency with other curves**: May need to ensure consistency with forward rates and par yield curves

## Conclusion

Yield curve bootstrapping is a fundamental technique that allows financial practitioners to extract zero-coupon rates and discount factors from market-observable instruments.   By understanding this process, financial analysts can better interpret interest rate structures, price complex securities, and manage interest rate risk.