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
## The Basics

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
# Present Value of an Annuity: Example

The present value of $100 paid at the end of each year for 5 years, with an interest rate of 5% per year:

<div class="formula">

$PV_{annuity} = 100 \times \frac{1 - (1+0.05)^{-5}}{0.05} = 100 \times 4.3295 = \$432.95$

</div>

---

<!-- Future Value of Annuities -->
# Future Value of an Annuity

<div class="formula">

$FV_{annuity} = PMT \times \frac{(1+r)^n - 1}{r}$

</div>

**Example**:
If you save $100 at the end of each year for 5 years, earning 5% annually:

<div class="formula">

$FV_{annuity} = 100 \times \frac{(1+0.05)^5 - 1}{0.05} = 100 \times 5.5256 = \$552.56$

</div>