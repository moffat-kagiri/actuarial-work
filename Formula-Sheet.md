# Actuarial, Statistical, and Financial Formulas Reference Document

---

*Aligned with IFOA Standards*

---

## **1. Financial Mathematics**

### **Time Value of Money**

1. **Compound Interest (Accumulation Factor)**

   $$
   FV = PV \cdot (1 + i)^n \quad \text{or} \quad FV = PV \cdot e^{\delta n}
   $$

   - $i$: Annual effective interest rate.
   - $\delta$: Force of interest ($\delta = \ln(1+i)$).

   $$


   $$
2. **Discount Factor**

   $$
   v = \frac{1}{1+i} = e^{-\delta}
   $$
3. **Present Value (PV) of Annuity-Certain**

   - *Annuity-immediate* (payments at end of period):
     $$
     a_{\angl{n}} = \frac{1 - v^n}{i}
     $$
   - *Annuity-due* (payments at start of period):
     $$
     \ddot{a}_{\angl{n}} = \frac{1 - v^n}{d} \quad \text{where } d = \frac{i}{1+i}
     $$
4. **Future Value (FV) of Annuity-Certain**

   $$
   s_{\angl{n}} = \frac{(1+i)^n - 1}{i}, \quad \ddot{s}_{\angl{n}} = \frac{(1+i)^n - 1}{d}
   $$

---

## **2. Actuarial Mathematics**

### **Life Contingencies**

1. **Present Value of Whole Life Annuity**

   - *Annuity-due* (IFOA notation):
     $$
     \ddot{a}_x = \sum_{k=0}^{\infty} v^k \cdot {}_k p_x
     $$
   - *Continuous annuity*:
     $$
     \bar{a}_x = \int_0^{\infty} v^t \cdot {}_t p_x \, dt
     $$
2. **Present Value of Term Life Insurance**

   $$
   A_{x:\angl{n}}^1 = \sum_{k=0}^{n-1} v^{k+1} \cdot {}_k p_x \cdot q_{x+k}
   $$

   - $q_x$: Probability of death within 1 year for age $x$.
3. **Net Premium Reserve**

   $$
   {}_t V = \ddot{a}_{x+t} - P \cdot \ddot{a}_{x+t:\angl{n-t}}
   $$

   - $P$: Premium payment.
4. **Endowment Insurance**

   $$
   A_{x:\angl{n}} = A_{x:\angl{n}}^1 + v^n \cdot {}_n p_x
   $$
5. **Deferred Life Annuity**

   $$
   {}_m \ddot{a}_x = \sum_{k=m}^{\infty} v^k \cdot {}_k p_x
   $$
6. **Accumulated Cost of Insurance**

   $$
   \bar{A}_x = \int_0^{\infty} v^t \cdot {}_t p_x \cdot \mu_{x+t} \, dt
   $$

---

### **Mortality and Survival Functions**

1. **Survival Probability**

   $$
   {}_t p_x = e^{-\int_0^t \mu_{x+s} \, ds}
   $$

   - $\mu_x$: Force of mortality.

   $$


   $$
2. **Deferred Mortality Probability**

   $$
   {}_t|_u q_x = {}_t p_x \cdot {}_u q_{x+t}
   $$
3. **Complete Expectation of Life**

   $$
   \mathring{e}_x = \int_0^{\infty} {}_t p_x \, dt
   $$
4. **Select Mortality**

   $$
   {}_t p_{[x]+s} = \frac{l_{x+s+t}}{l_{x+s}}
   $$

---

### **Commutation Functions (IFOA)**

1. **Discounted Lives**
   $$
   D_x = v^x l_x
   $$
2. **Accumulated Annuity Factors**
   $$
   N_x = \sum_{k=0}^{\infty} D_{x+k}
   $$
3. **Death Benefit Factors**
   $$
   C_x = v^{x+1} d_x, \quad M_x = \sum_{k=0}^{\infty} C_{x+k}
   $$
4. **Annuity-Due Commutation**
   $$
   \ddot{a}_x = \frac{N_x}{D_x}
   $$
5. **Term Insurance Commutation**
   $$
   A_{x:\angl{n}}^1 = \frac{M_x - M_{x+n}}{D_x}
   $$

---

## **3. Probability and Statistics**

### **Distributions**

1. **Normal Distribution**
   $$
   X \sim N(\mu, \sigma^2) \Rightarrow f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}
   $$
2. **Binomial Distribution**
   $$
   P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}
   $$
3. **Poisson Distribution**
   $$
   P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}
   $$
4. **Exponential Distribution**
   $$
   f(x) = \lambda e^{-\lambda x}, \quad x \geq 0
   $$
5. **Gamma Distribution**
   $$
   f(x) = \frac{\beta^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x}, \quad x \geq 0
   $$

---

### **Expectation and Variance**

1. **Law of Total Expectation**
   $$
   E[X] = E[E[X|Y]]
   $$
2. **Variance Formula**
   $$
   \text{Var}(X) = E[X^2] - (E[X])^2
   $$
3. **Covariance**
   $$
   \text{Cov}(X, Y) = E[XY] - E[X]E[Y]
   $$

---

### **Hypothesis Testing**

1. **Z-Test Statistic**
   $$
   Z = \frac{\bar{X} - \mu}{\sigma/\sqrt{n}}
   $$
2. **Chi-Square Test**
   $$
   \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}
   $$
3. **t-Test Statistic**
   $$
   t = \frac{\bar{X} - \mu}{s/\sqrt{n}}
   $$

---

## **4. Financial Derivatives**

1. **Black-Scholes Option Pricing**
   $$
   C = S_0 N(d_1) - K e^{-rT} N(d_2) $$  
   - $d_1 = \frac{\ln(S_0/K) + (r + \sigma^2/2)T}{\sigma \sqrt{T}}$, $d_2 = d_1 - \sigma \sqrt{T}$.
   $$
2. **Duration and Convexity**
   - *Macaulay Duration*:
     $$
     D = \frac{\sum t \cdot PV(CF_t)}{\text{Price}}
     $$
   - *Convexity*:
     $$
     C = \frac{\sum t(t+1) \cdot PV(CF_t)}{(1+i)^2 \cdot \text{Price}}
     $$

---

## **Additional Actuarial Formulas**

1. **Joint Life Annuity**

   $$
   \ddot{a}_{xy} = \sum_{k=0}^{\infty} v^k \cdot {}_k p_{xy}
   $$
2. **Last Survivor Annuity**

   $\ddot{a}_{\overline{xy}}$ = $\ddot{a}_x + \ddot{a}_y - \ddot{a}_{xy}$
3. **Net Premium for Whole Life Insurance**

   $$
   P_x = \frac{A_x}{\ddot{a}_x}
   $$
4. **Thiele’s Differential Equation**

   $$
   \frac{d}{dt} {}_t V = \delta \cdot {}_t V + P - \mu_{x+t} (S - {}_t V)
   $$
5. **Variance of Present Value**

   $$
   \text{Var}(PV) = E[PV^2] - (E[PV])^2
   $$


Find out what this is.

$$
\ddot{a}_{\overline{xy}}
\ddot{a}_{\overline{xy}}
$$
