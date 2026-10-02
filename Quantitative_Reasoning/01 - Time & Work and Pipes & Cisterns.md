---
title: "01 - Time & Work and Pipes & Cisterns"
tags:
  - aptitude
  - quantitative-reasoning
  - time-and-work
  - pipes-and-cisterns
  - speed-shortcuts
created: 2026-10-02
track: "Quantitative Reasoning"
---

# ⏱️ 01 - Time & Work and Pipes & Cisterns

> [!TIP]
> **The Golden Rule:**  
> Never use school fractions ($\frac{1}{10} + \frac{1}{15}$).  
> Always convert the job into **Total Work = LCM of days (Total Chocolates)**.

---

## ⚡ Master Formula & Shortcut Cheatsheet

| Concept | The 10-Second Shortcut Formula | Meaning & Core Invariant |
| :--- | :--- | :--- |
| **Total Work** | $\mathbf{\text{Total Work} = \text{LCM}(T_1, T_2, \dots)}$ | Treats the entire job as a discrete quantity of units (chocolates). |
| **Daily Efficiency** | $\mathbf{\text{Efficiency} = \frac{\text{Total Work}}{\text{Total Days}}}$ | Units completed per single day/hour. |
| **Combined Time** | $\mathbf{\text{Time} = \frac{\text{Total Work}}{\sum \text{Efficiencies}}}$ | Total units divided by combined daily units. |
| **Inverse Law** | $\mathbf{\text{Efficiency} \propto \frac{1}{\text{Time}}}$ | If ratio of time is $a:b$, ratio of efficiency is $b:a$. |
| **Chain Rule (MDH/W)** | $\mathbf{\frac{M_1 \cdot D_1 \cdot H_1}{W_1} = \frac{M_2 \cdot D_2 \cdot H_2}{W_2}}$ | Men $\times$ Days $\times$ Hours divided by Work output is always constant. |
| **Wage Distribution** | $\mathbf{\text{Wage Ratio} = \text{Work Done Ratio}}$ | If working together for the same duration, wages split in the ratio of **Efficiencies**. |
| **Pipes & Cisterns** | $\mathbf{\text{Net Rate} = \text{Inlet Rate} - \text{Leak Rate}}$ | Inlets perform positive work ($+$); leaks/outlets perform negative work ($-$). |

---

## 🎯 Model 1: Basic Combined Work (A & B Together)

### 💡 Theory & Method
Assume Total Work $= \text{LCM}(\text{Time}_A, \text{Time}_B)$. Compute daily units for each, add them up, and divide total work by combined daily units.

### ❓ Sample Question
> Worker A can finish a project in **12 days**, while Worker B can finish the same project in **18 days**. If they work together, in how many days will the project be completed?

### 📝 Step-by-Step Solution
1. **Total Work:** $\text{LCM}(12, 18) = \mathbf{36 \text{ units}}$
2. **Efficiencies (Units/Day):**
   * $\text{Efficiency of A} = \frac{36}{12} = \mathbf{3 \text{ units/day}}$
   * $\text{Efficiency of B} = \frac{36}{18} = \mathbf{2 \text{ units/day}}$
3. **Combined Rate:** $3 + 2 = \mathbf{5 \text{ units/day}}$
4. **Time Taken:**
   $$\text{Days} = \frac{36}{5} = \mathbf{7.2 \text{ days}} \quad \left(\text{or } 7 \frac{1}{5} \text{ days}\right)$$

---

## 🎯 Model 2: Worker Leaves or Joins Midway

### 💡 Theory & Method
1. Calculate work done during the shared days: $\text{Days} \times (\text{Combined Rate})$.
2. Subtract from Total Work to find **Remaining Work**.
3. Divide remaining work by the remaining person's individual efficiency.

### ❓ Sample Question
> A can complete a job in **20 days** and B in **30 days**. They start the job together, but after **6 days**, A leaves. In how many more days will B finish the remaining work?

### 📝 Step-by-Step Solution
1. **Total Work:** $\text{LCM}(20, 30) = \mathbf{60 \text{ units}}$
2. **Individual Efficiencies:**
   * $\text{Rate of A} = \frac{60}{20} = \mathbf{3 \text{ units/day}}$
   * $\text{Rate of B} = \frac{60}{30} = \mathbf{2 \text{ units/day}}$
   * $\text{Combined Rate} = 3 + 2 = \mathbf{5 \text{ units/day}}$
3. **Work Completed in First 6 Days:**
   $$\text{Work Done} = 6 \text{ days} \times 5 \text{ units/day} = \mathbf{30 \text{ units}}$$
4. **Remaining Work:**
   $$\text{Remaining} = 60 - 30 = \mathbf{30 \text{ units}}$$
5. **Time for B to Finish Remaining:**
   $$\text{Additional Days for B} = \frac{30 \text{ units}}{2 \text{ units/day}} = \mathbf{15 \text{ days}}$$
   *(Total project duration $= 6 + 15 = 21$ days).*

---

## 🎯 Model 3: Efficiency & Ratio-Based Problems

### 💡 Theory & Method
Remember the **Inverse Ratio Law**:
$$\text{Efficiency Ratio } (A : B) = k : 1 \implies \text{Time Ratio } (A : B) = 1 : k$$
Set the unit difference equal to the given day difference to find the real day values.

### ❓ Sample Question
> A is **3 times as efficient as B**, and is therefore able to finish a job in **40 days less** than B. Working together, in how many days can they complete the work?

### 📝 Step-by-Step Solution
1. **Ratios:**
   * $\text{Efficiency Ratio } (A : B) = 3 : 1$
   * $\text{Time Ratio } (A : B) = 1 : 3$
2. **Unit Difference in Time:**
   $$3 \text{ units} - 1 \text{ unit} = 2 \text{ units}$$
   $$2 \text{ units} = 40 \text{ days} \implies 1 \text{ unit} = \mathbf{20 \text{ days}}$$
3. **Actual Days Taken:**
   * A takes $1 \text{ unit} = \mathbf{20 \text{ days}}$
   * B takes $3 \text{ units} = \mathbf{60 \text{ days}}$
4. **Total Work:** $\text{LCM}(20, 60) = \mathbf{60 \text{ units}}$
   * $\text{Rate of A} = 3 \text{ units/day}$, $\text{Rate of B} = 1 \text{ unit/day}$
   * $\text{Combined Rate} = 3 + 1 = \mathbf{4 \text{ units/day}}$
5. **Combined Time:**
   $$\text{Time} = \frac{60}{4} = \mathbf{15 \text{ days}}$$

---

## 🎯 Model 4: Alternate Day Work

### 💡 Theory & Method
Group two alternate days into **1 Cycle (2 days)**. Calculate work done per cycle, find how many full cycles fit inside the total work, and handle the remaining fractional units on the final turn.

### ❓ Sample Question
> A can do a piece of work in **12 days** and B in **16 days**. They work on alternate days, starting with **A on Day 1**. On which day and in how many total days will the work be completed?

### 📝 Step-by-Step Solution
1. **Total Work:** $\text{LCM}(12, 16) = \mathbf{48 \text{ units}}$
2. **Efficiencies:**
   * Rate of A $= \frac{48}{12} = \mathbf{4 \text{ units/day}}$
   * Rate of B $= \frac{48}{16} = \mathbf{3 \text{ units/day}}$
3. **Work Done in 1 Full Cycle (2 Days):**
   $$\text{Day 1 (A)} + \text{Day 2 (B)} = 4 + 3 = \mathbf{7 \text{ units in 2 days}}$$
4. **Multiply Cycles to Approach 48 Units:**
   * $6 \text{ cycles} \times 7 \text{ units} = \mathbf{42 \text{ units}}$
   * $6 \text{ cycles} = 6 \times 2 = \mathbf{12 \text{ days elapsed}}$.
5. **Remaining Work:**
   $$\text{Remaining} = 48 - 42 = \mathbf{6 \text{ units}}$$
6. **Next Turns:**
   * **Day 13 (A's turn):** A completes $4 \text{ units}$. Work left $= 6 - 4 = \mathbf{2 \text{ units}}$.
   * **Day 14 (B's turn):** B has a rate of $3 \text{ units/day}$. To finish 2 units, B needs $\mathbf{\frac{2}{3} \text{ of a day}}$.
7. **Total Time:**
   $$\text{Total Days} = 12 + 1 + \frac{2}{3} = \mathbf{13 \frac{2}{3} \text{ days}}$$

---

## 🎯 Model 5: Pipes & Cisterns with Negative Work (Leaks)

### 💡 Theory & Method
Treat the tank capacity as $\text{LCM}(\text{hours})$. Filling pipes have a **positive rate (+)**; emptying leaks have a **negative rate (-)**.

### ❓ Sample Question
> Pipe A fills a tank in **15 hours**, and Pipe B fills it in **20 hours**. Due to a leak C at the bottom, it takes **30 hours** to fill the tank when all three are open. How many hours would leak C alone take to completely empty a full tank?

### 📝 Step-by-Step Solution
1. **Tank Capacity:** $\text{LCM}(15, 20, 30) = \mathbf{60 \text{ liters}}$
2. **Determine Rates:**
   * $\text{Rate of A} = \frac{60}{15} = \mathbf{+4 \text{ L/hr}}$
   * $\text{Rate of B} = \frac{60}{20} = \mathbf{+3 \text{ L/hr}}$
   * $\text{Net Rate } (A + B - C) = \frac{60}{30} = \mathbf{+2 \text{ L/hr}}$
3. **Solve for Leak C:**
   $$(+4) + (+3) - C = +2$$
   $$7 - C = 2 \implies C = \mathbf{5 \text{ L/hr}}$$
4. **Time for Leak C to Empty Full Tank:**
   $$\text{Time} = \frac{60 \text{ liters}}{5 \text{ L/hr}} = \mathbf{12 \text{ hours}}$$

---

## 🎯 Model 6: Men, Days, Hours Formula ($M_1 D_1 H_1 / W_1 = M_2 D_2 H_2 / W_2$)

### 💡 Theory & Method
Work is directly proportional to $(\text{Men} \times \text{Days} \times \text{Hours})$. Set up the ratio equation and cross-multiply:
$$\frac{M_1 \cdot D_1 \cdot H_1}{W_1} = \frac{M_2 \cdot D_2 \cdot H_2}{W_2}$$

### ❓ Sample Question
> If **15 men** working **8 hours a day** can build a **120-meter road** in **10 days**, how many men working **6 hours a day** are required to build a **360-meter road** in **20 days**?

### 📝 Step-by-Step Solution
1. **Identify Variables:**
   * $M_1 = 15, \quad D_1 = 10, \quad H_1 = 8, \quad W_1 = 120$
   * $M_2 = ?, \quad D_2 = 20, \quad H_2 = 6, \quad W_2 = 360$
2. **Apply the Master Formula:**
   $$\frac{15 \times 10 \times 8}{120} = \frac{M_2 \times 20 \times 6}{360}$$
3. **Simplify Step-by-Step:**
   * Left Hand Side: $\frac{1200}{120} = \mathbf{10}$
   * Right Hand Side: $\frac{M_2 \times 120}{360} = \mathbf{\frac{M_2}{3}}$
4. **Solve for $M_2$:**
   $$10 = \frac{M_2}{3} \implies M_2 = 10 \times 3 = \mathbf{30 \text{ men}}$$

---

## ⚡ 10-Second High-Frequency Exam Traps

| Trap Scenario | Common Mistake | The Instant Correct Rule |
| :--- | :--- | :--- |
| **Wage Distribution** | Splitting wages equally or by days worked. | Wages split strictly according to **Work Done** (or ratio of efficiencies if days are equal). |
| **Men & Women conversion** | Adding men and women directly ($2M + 3W = 5$ workers). | Convert everyone to a single gender using the given efficiency equivalence (e.g. $1M = 2W$). |
| **Alternate day finish** | Dividing remaining work by 2-day cycle. | Once cycles end, step through Day 1 (Person A) and Day 2 (Person B) **individually**. |
