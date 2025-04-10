---
marp: true
theme: default
paginate: true
header: "Fixed Income: Time Value of Money"
footer: "© 2025"
style: |
  section {
    font-size: 28px;
  }
  h1 {
    font-size: 42px;
    color: #333;
  }
  h2 {
    font-size: 36px;
    color: #0066cc;
  }
  h3 {
    font-size: 32px;
    color: #006600;
  }
  .small-text {
    font-size: 24px;
  }
  .formula {
    background-color: #f0f0f0;
    padding: 10px;
    border-radius: 5px;
    text-align: center;
  }
---

<!-- Title Slide -->
# Time Value of Money
## Foundational Principles in Finance

---

<!-- Introduction Slide -->
# Introduction

- The time value of money (TVM) is one of the most fundamental concepts in finance
- Money available today is worth more than the same amount in the future
- This principle forms the basis for virtually all financial decisions:
  - Personal savings
  - Investment strategies
  - Corporate finance

---

<!-- Present Value Slide -->
# Present Value (PV)

The present value represents the **current worth** of a future sum of money, given a specified rate of return.

<div class="formula">

$PV = \frac{FV}{(1+r)^n}$

</div>

Where:
- PV = Present Value
- FV = Future Value
- r = Interest rate per period
- n = Number of periods

---

<!-- Present Value Example -->
# Present Value: Example

If you expect to receive $1,000 in 5 years and the interest rate is 5% per year:

<div class="formula">

$PV = \frac{1,000}{(1+0.05)^5} = \frac{1,000}{1.2763} = \$783.53$

</div>

**Key insight**: $1,000 received 5 years from now is equivalent to $783.53 today, given a 5% interest rate.

---

<!-- Future Value Slide -->
# Future Value (FV)

Future value calculates what an investment today will be worth at a future date, given a specific interest rate.

<div class="formula">

$FV = PV \times (1+r)^n$

</div>

Where:
- FV = Future Value
- PV = Present Value
- r = Interest rate per period
- n = Number of periods

---

<!-- Future Value Example -->
# Future Value: Example

If you invest $1,000 today at an annual interest rate of 5% for 5 years:

<div class="formula">

$FV = 1,000 \times (1+0.05)^5 = 1,000 \times 1.2763 = \$1,276.30$

</div>

**Key insight**: $1,000 invested today will grow to $1,276.30 in 5 years at a 5% interest rate.

---

<!-- Present Value of Annuities -->
# Present Value of an Annuity

An annuity is a series of equal payments made at equal intervals.

## Present Value of an Ordinary Annuity
Payments occur at the **end** of each period.

<div class="formula">

$PV_{annuity} = PMT \times \frac{1 - (1+r)^{-n}}{r}$

</div>

Where:
- PMT = Payment per period
- r = Interest rate per period
- n = Number of periods

---

<!-- Present Value of Annuity Example -->
# Present Value of an Ordinary Annuity: Example

The present value of $100 paid at the end of each year for 5 years, with an interest rate of 5% per year:

<div class="formula">

$PV_{annuity} = 100 \times \frac{1 - (1+0.05)^{-5}}{0.05} = 100 \times 4.3295 = \$432.95$

</div>

---

<!-- Present Value of Annuity Due -->
# Present Value of an Annuity Due

Payments occur at the **beginning** of each period.

<div class="formula">

$PV_{annuity\ due} = PMT \times \frac{1 - (1+r)^{-n}}{r} \times (1+r)$

$= PV_{ordinary\ annuity} \times (1+r)$

</div>

**Key insight**: An annuity due is worth more than an ordinary annuity because payments are received earlier.

---

<!-- Future Value of Annuities -->
# Future Value of an Annuity

## Future Value of an Ordinary Annuity

<div class="formula">

$FV_{annuity} = PMT \times \frac{(1+r)^n - 1}{r}$

</div>

**Example**:
If you save $100 at the end of each year for 5 years, earning 5% annually:

<div class="formula">

$FV_{annuity} = 100 \times \frac{(1+0.05)^5 - 1}{0.05} = 100 \times 5.5256 = \$552.56$

</div>

---

<!-- Future Value of Annuity Due -->
# Future Value of an Annuity Due

<div class="formula">

$FV_{annuity\ due} = PMT \times \frac{(1+r)^n - 1}{r} \times (1+r)$

$= FV_{ordinary\ annuity} \times (1+r)$

</div>

**Key insight**: An annuity due results in a higher future value than an ordinary annuity because payments are invested earlier.

---

<!-- Bond Valuation Slide -->
# Bond Valuation

A bond's value is the present value of all future cash flows:
- Coupon payments
- Face value at maturity

<div class="formula">

$P = \sum_{t=1}^{n} \frac{C}{(1+r)^t} + \frac{F}{(1+r)^n}$

</div>

Where:
- P = Bond price
- C = Coupon payment
- F = Face value (par value)
- r = Required yield (market interest rate)
- n = Number of periods to maturity

---

<!-- Semiannual Bond Valuation -->
# Semiannual Bond Coupon Payments

For bonds with semiannual coupon payments (common in the US):

<div class="formula" class="small-text">

$P = \sum_{t=1}^{2n} \frac{C/2}{(1+r/2)^t} + \frac{F}{(1+r/2)^{2n}}$

</div>

**Key adjustments**:
- Coupon payment (C) is divided by 2
- Interest rate (r) is divided by 2
- Number of periods (n) is multiplied by 2

---

<!-- Compounding Periods -->
# Compounding Periods

The frequency of compounding affects the effective annual rate (EAR) and the future value of investments.

## Effective Annual Rate (EAR)

<div class="formula">

$EAR = \left(1 + \frac{r}{m}\right)^m - 1$

</div>

Where:
- r = Nominal annual interest rate
- m = Number of compounding periods per year

---

<!-- Future Value with Periodic Compounding -->
# Future Value with Periodic Compounding

<div class="formula">

$FV = PV \times \left(1 + \frac{r}{m}\right)^{m \times n}$

</div>

Common compounding periods:
- Annual (m=1): $FV = PV \times (1 + r)^n$
- Semiannual (m=2): $FV = PV \times \left(1 + \frac{r}{2}\right)^{2n}$
- Quarterly (m=4): $FV = PV \times \left(1 + \frac{r}{4}\right)^{4n}$
- Monthly (m=12): $FV = PV \times \left(1 + \frac{r}{12}\right)^{12n}$
- Daily (m=365): $FV = PV \times \left(1 + \frac{r}{365}\right)^{365n}$

---

<!-- Continuous Compounding -->
# Continuous Compounding

Continuous compounding represents the theoretical limit as the number of compounding periods approaches infinity.

<div class="formula">

$FV = PV \times e^{rt}$

</div>

Where:
- e = Mathematical constant (≈ 2.71828)
- r = Nominal annual interest rate
- t = Time in years

---

<!-- Continuous Compounding Example -->
# Continuous Compounding: Example

$1,000 invested for 5 years at a nominal rate of 5% with continuous compounding:

<div class="formula">

$FV = 1,000 \times e^{0.05 \times 5} = 1,000 \times e^{0.25} = 1,000 \times 1.2840 = \$1,284.00$

</div>

Compare this to annual compounding: 
$1,000 \times (1+0.05)^5 = \$1,276.30$

**Key insight**: Continuous compounding provides the highest possible future value.

---

<!-- Effective Annual Rate with Continuous Compounding -->
# Effective Annual Rate with Continuous Compounding

<div class="formula">

$EAR = e^r - 1$

</div>

**Example**:
For a nominal rate of 5% with continuous compounding:

<div class="formula">

$EAR = e^{0.05} - 1 = 1.0513 - 1 = 0.0513 = 5.13\%$

</div>

---

<!-- Practical Applications -->
# Practical Applications

These time value of money principles apply to numerous financial decisions:

1. Investment evaluation (NPV, IRR)
2. Loan amortization
3. Retirement planning
4. Insurance premium calculations
5. Real estate valuation
6. Corporate financial planning

---

<!-- Closing Slide -->
# Key Takeaways

- Money has a time value – a dollar today is worth more than a dollar tomorrow
- Present value discounts future cash flows to their current worth
- Future value grows current amounts to their worth at a future date
- Annuities simplify calculations for equal periodic payments
- Compounding frequency affects investment growth
- These principles form the foundation of all financial analysis

---

<!-- Thank You Slide -->
# Thank You

## Questions?
