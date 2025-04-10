# Macaulay Modified Duration: Dual Interpretations in Bond Analysis

## Bond Valuation

Recall that a bond's value is the present value of all future cash flows, including coupon payments and the face value at maturity.

**Formula:**
$P = \sum_{t=1}^{n} \frac{C}{(1+r)^t} + \frac{F}{(1+r)^n}$

Where:
- P = Bond price
- C = Coupon payment
- F = Face value (par value)
- r = Required yield (market interest rate)
- n = Number of periods to maturity

For bonds with semiannual coupon payments (common in the US), the formula becomes:

$P = \sum_{t=1}^{2n} \frac{C/2}{(1+r/2)^t} + \frac{F}{(1+r/2)^{2n}}$## The Formula

The Macaulay Modified Duration is:

$$D_{mod} = \frac{D_{mac}}{1+y/m}$$

Where:
- $D_{mod}$ is the Modified Duration
- $D_{mac}$ is the Macaulay Duration
- $y$ is the yield-to-maturity (YTM)
- $m$ is the number of compounding periods per year

The Macaulay Duration itself is defined as:

$$D_{mac} = \frac{\sum_{t=1}^{n} t \times CF_t \times (1+y/m)^{-t}}{\sum_{t=1}^{n} CF_t \times (1+y/m)^{-t}} = \frac{\sum_{t=1}^{n} t \times CF_t \times (1+y/m)^{-t}}{P}$$

Where:
- $CF_t$ is the cash flow at time $t$
- $P$ is the price of the bond
- $n$ is the total number of periods

## Derivation and Weighted Average Interpretation

### Macaulay Duration as a Weighted Average

The Macaulay Duration represents the weighted average time until cash flows are received, with weights proportional to the present value of each cash flow. This can be seen directly from the formula:

1. Each time period $t$ is weighted by: $\frac{CF_t \times (1+y/m)^{-t}}{P}$
2. These weights sum to 1 since $P = \sum_{t=1}^{n} CF_t \times (1+y/m)^{-t}$
3. The weighted sum $\sum_{t=1}^{n} t \times \frac{CF_t \times (1+y/m)^{-t}}{P}$ gives us the average time, weighted by present value

Intuitively, this measures how long, on average, you must wait to receive the bond's payments. Cash flows that contribute more to the bond's present value (larger or earlier payments) have greater influence on this average.

### Derivation of Modified Duration from Macaulay Duration

To derive Modified Duration, we start by examining how a bond's price changes with respect to yield:

1. First, we take the price function of a bond: $P = \sum_{t=1}^{n} CF_t \times (1+y/m)^{-t}$

2. Differentiating with respect to $y$:
   $$\frac{dP}{dy} = \sum_{t=1}^{n} CF_t \times (-t) \times (1+y/m)^{-t-1} \times \frac{1}{m}$$

3. Rearranging:
   $$\frac{dP}{dy} = -\frac{1}{m} \times \sum_{t=1}^{n} t \times CF_t \times (1+y/m)^{-t} \times \frac{1}{1+y/m}$$

4. Factoring out $P$ and $D_{mac}$:
   $$\frac{dP}{dy} = -\frac{P \times D_{mac}}{1+y/m} \times \frac{1}{m}$$

5. The percentage change in price is:
   $$\frac{1}{P} \times \frac{dP}{dy} = -\frac{D_{mac}}{1+y/m} \times \frac{1}{m} = -\frac{D_{mod}}{m}$$

This gives us the Modified Duration: $D_{mod} = \frac{D_{mac}}{1+y/m}$

## Price Sensitivity Interpretation

The Modified Duration directly measures the sensitivity of a bond's price to changes in yield:

$$\frac{\Delta P}{P} \approx -D_{mod} \times \Delta y$$

Where:
- $\frac{\Delta P}{P}$ is the percentage change in price
- $\Delta y$ is the change in yield (in decimal form)

For example, if a bond has a Modified Duration of 5 and yields increase by 0.01 (1%), the bond's price will decrease by approximately 5%.

## Reconciling the Two Interpretations

These two interpretations—weighted average time and price sensitivity—seem different at first glance, but they're intrinsically connected:

1. **Time value of money**: The longer you must wait for cash flows, the more their present value is affected by discount rate changes. Cash flows further in the future are more sensitive to yield changes.

2. **Compounding effect**: When yields rise, the discount factor $(1+y/m)^{-t}$ falls more dramatically for distant cash flows. This is why longer-term bonds generally have greater price sensitivity.

3. **Mathematical connection**: The price sensitivity interpretation comes directly from calculus (taking the derivative), while the weighted average interpretation comes from the original formula's structure.

The reconciliation boils down to this insight: The longer the weighted average time until receipt of cash flows (Macaulay Duration), the more sensitive a bond's price will be to yield changes, because distant cash flows are more affected by discounting changes.

When adjusted for the current yield environment (dividing by $1+y/m$), we get Modified Duration, which directly quantifies this price sensitivity.