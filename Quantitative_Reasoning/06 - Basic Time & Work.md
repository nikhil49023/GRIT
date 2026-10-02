---
title: "01 - Time & Work and Pipes & Cisterns (Zero to Mastery)"
tags:
  - aptitude
  - quantitative-reasoning
  - time-and-work
  - pipes-and-cisterns
  - zero-to-hero
created: 2026-10-02
track: "Quantitative Reasoning"
---

# ⏱️ 01 - Time & Work and Pipes & Cisterns

> [!TIP]
> **The Core Secret (From Zero to Hero):**  
> Forget all school formulas and fractions ($\frac{1}{10} + \frac{1}{15}$).  
> Work is never an "abstract 1". **Work is simply a box of cookies.**  
> If you can divide cookies among friends, you can solve 100% of these problems in your head.

---

## 🧠 Part 1: The Foundation (Assume You Know Nothing)

### 1. What Actually is "Work"?
In physics, work is energy. In aptitude tests, "work" is just an assignment:
* Painting a fence
* Digging a trench
* Filling a water tank
* Baking cookies

### 2. Why Did School Math Make You Hate This Topic?
In school, teachers said:
> *"If Alice takes 10 days to paint a house, in 1 day she paints $\frac{1}{10}$ of the house. If Bob takes 15 days, in 1 day he paints $\frac{1}{15}$ of the house... Now find a common denominator: $\frac{1}{10} + \frac{1}{15} = \frac{3+2}{30} = \frac{5}{30} = \frac{1}{6}$... so 6 days."*

This is slow, clumsy, and terrifying under exam pressure. Why? Because **human brains hate fractions with different denominators**.

---

### 3. The "Cookie" Mental Model (The LCM Shortcut)
Instead of imagining 1 giant abstract house, **let's imagine a box of cookies**:

1. **How big is the box?**  
   Pick a number of cookies that **both people's days can divide into cleanly** with zero decimals! That magic number is called the **LCM (Lowest Common Multiple)**.
2. **What is "Efficiency"?**  
   Efficiency is simply **how many cookies a person eats in 1 single day**:
   $$\mathbf{\text{Daily Speed (Efficiency)} = \frac{\text{Total Cookies in Box}}{\text{Days taken to finish}}}$$
3. **What happens when they work together?**  
   Add their daily eating speeds together, and see how fast the box empties:
   $$\mathbf{\text{Total Days Together} = \frac{\text{Total Cookies in Box}}{\text{Combined Daily Speed}}}$$

---

### 4. A 10-Second Warm-up Example
* **Alice takes 10 days.**
* **Bob takes 15 days.**

* **Step 1: Pick the cookie box (LCM of 10 and 15):**  
  Count by 15s: $15$ (doesn't divide by 10), $30$ (divides by 10!).  
  $\implies \mathbf{30 \text{ cookies in the box}}$.
* **Step 2: Find daily eating speed:**  
  * Alice eats: $30 \div 10 = \mathbf{3 \text{ cookies/day}}$
  * Bob eats: $30 \div 15 = \mathbf{2 \text{ cookies/day}}$
* **Step 3: Put them at the same table:**  
  Together they eat: $3 + 2 = \mathbf{5 \text{ cookies/day}}$.
* **Step 4: How long until the 30 cookies are gone?**  
  $$30 \text{ cookies} \div 5 \text{ cookies/day} = \mathbf{6 \text{ days}}!$$

No fractions. No pencil. Clean mental math.

---

## 🎯 Model 1: Basic Combined Work (Two Friends Working Together)

### ❓ The Problem
> Worker A can paint a wall in **12 days**, while Worker B can paint the same wall in **18 days**. If they work together, in how many days will the wall be completed?

### 🧩 First-Principles Walkthrough
* **Step 1: Find the Total Work (The Cookie Box).**  
  We need a number that both 12 and 18 divide into.  
  Look at the bigger number (18):  
  * $18 \times 1 = 18$ (12 cannot divide 18).
  * $18 \times 2 = 36$ (12 divides 36 cleanly! $12 \times 3 = 36$).  
  $\implies \mathbf{\text{Total Work} = 36 \text{ units (cookies)}}$.

* **Step 2: Find each worker's daily speed.**  
  * Worker A: $\frac{36}{12} = \mathbf{3 \text{ units/day}}$
  * Worker B: $\frac{36}{18} = \mathbf{2 \text{ units/day}}$

* **Step 3: Combine their power.**  
  Working together, every day they finish:
  $$3 + 2 = \mathbf{5 \text{ units/day}}$$

* **Step 4: Calculate total time.**  
  $$\text{Time Taken} = \frac{\text{Total Work}}{\text{Combined Speed}} = \frac{36}{5} = \mathbf{7.2 \text{ days}} \quad \left(\text{or } 7 \frac{1}{5} \text{ days}\right)$$

> [!NOTE]
> **Sanity Check:** If Worker A alone takes 12 days, working with a helper *must* take less than 12 days. 7.2 days makes complete sense!

---

## 🎯 Model 2: Worker Leaves Midway (The Abandonment)

### ❓ The Problem
> A can complete a job in **20 days** and B in **30 days**. They start the job together, but after **6 days**, A walks away. In how many more days will B finish the remaining work alone?

### 🧩 First-Principles Walkthrough
Think of this as a story in two chapters:  
* **Chapter 1:** A and B work together for 6 days.  
* **Chapter 2:** B is left alone to finish whatever is left in the box.

* **Step 1: Find Total Work.**  
  $\text{LCM}(20, 30) = \mathbf{60 \text{ cookies}}$.

* **Step 2: Find daily speeds.**  
  * Speed of A $= \frac{60}{20} = \mathbf{3 \text{ cookies/day}}$  
  * Speed of B $= \frac{60}{30} = \mathbf{2 \text{ cookies/day}}$  
  * Combined Speed $= 3 + 2 = \mathbf{5 \text{ cookies/day}}$

* **Step 3: Play Chapter 1 (The first 6 days).**  
  They worked together for 6 days at 5 cookies per day:
  $$\text{Cookies Eaten} = 6 \text{ days} \times 5 \text{ cookies/day} = \mathbf{30 \text{ cookies}}$$

* **Step 4: How many cookies are left on the table?**  
  $$\text{Remaining Cookies} = 60 \text{ (Total)} - 30 \text{ (Done)} = \mathbf{30 \text{ cookies left}}$$

* **Step 5: Play Chapter 2 (B finishes alone).**  
  A has left. Only B is eating. B eats at a speed of **2 cookies per day**:
  $$\text{Extra Days for B} = \frac{30 \text{ cookies left}}{2 \text{ cookies/day}} = \mathbf{15 \text{ more days}}!$$

*(If the question asks for **Total Time** of the project: $6 \text{ days together} + 15 \text{ days alone} = \mathbf{21 \text{ total days}}$).*

---

## 🎯 Model 3: Efficiency & Ratios (The Super-Worker)

### 💡 The Core Intuition: The Seesaw Law
If you work **faster**, you take **fewer days**.  
$$\mathbf{\text{Speed (Efficiency)} \text{ is the exact opposite of } \text{Time}}$$
* If John is **2 times as fast** as Mike, John takes **half the time** of Mike.
* If Speed ratio is $3 : 1$, Time ratio is **$1 : 3$**.

---

### ❓ The Problem
> A is **3 times as efficient as B**, and is therefore able to finish a job in **40 days less** than B. Working together, in how many days can they complete the work?

### 🧩 First-Principles Walkthrough
* **Step 1: Write down the ratios.**  
  * Efficiency Ratio $(A : B) = 3 : 1$ (A eats 3 cookies while B eats 1).  
  * Flip it to get the Time Ratio:  
    $$\text{Time Ratio } (A : B) = \mathbf{1 \text{ unit} : 3 \text{ units}}$$

* **Step 2: Compare the time difference.**  
  According to our ratio:  
  * A takes 1 unit of time.  
  * B takes 3 units of time.  
  * The difference between them is: $3 - 1 = \mathbf{2 \text{ units}}$.

* **Step 3: Match ratio units to real-world days.**  
  The question says the difference is **40 days**:
  $$2 \text{ units} = 40 \text{ days}$$
  $$1 \text{ unit} = \frac{40}{2} = \mathbf{20 \text{ days}}$$

* **Step 4: Find their actual individual times.**  
  * A takes $1 \text{ unit} = \mathbf{20 \text{ days}}$
  * B takes $3 \text{ units} = 3 \times 20 = \mathbf{60 \text{ days}}$

* **Step 5: Now solve as a normal Model 1 problem!**  
  * Total Work $= \text{LCM}(20, 60) = \mathbf{60 \text{ cookies}}$  
  * Speed of A $= 60 \div 20 = \mathbf{3 \text{ cookies/day}}$  
  * Speed of B $= 60 \div 60 = \mathbf{1 \text{ cookie/day}}$  
  * Together they eat: $3 + 1 = \mathbf{4 \text{ cookies/day}}$  
  $$\text{Combined Days} = \frac{60}{4} = \mathbf{15 \text{ days}}!$$

---

## 🎯 Model 4: Alternate Day Work (Taking Turns)

### ❓ The Problem
> A can do a piece of work in **12 days** and B in **16 days**. They work on alternate days, starting with **A on Day 1**. In how many total days will the work be completed?

### 🧩 First-Principles Walkthrough
They are taking turns. You cannot add their speeds into 1 single day because they never work at the same time!  
Instead, **group 2 days into a single "Round" (Cycle)**:
* Day 1: A works
* Day 2: B works
* $\implies$ **1 Cycle = 2 Days**

* **Step 1: Total Work (LCM).**  
  $\text{LCM}(12, 16) = \mathbf{48 \text{ cookies}}$.

* **Step 2: Find daily speeds.**  
  * Speed of A $= 48 \div 12 = \mathbf{4 \text{ cookies/day}}$
  * Speed of B $= 48 \div 16 = \mathbf{3 \text{ cookies/day}}$

* **Step 3: How much work is done in 1 Cycle (2 days)?**  
  $$\text{Day 1 (A: 4)} + \text{Day 2 (B: 3)} = \mathbf{7 \text{ cookies in 1 cycle (2 days)}}$$

* **Step 4: How many full cycles can we run without exceeding 48?**  
  Divide $48$ by $7$:
  $$48 \div 7 = \mathbf{6 \text{ full cycles}} \quad (\text{with a remainder of } 6 \text{ cookies})$$
  * How many cookies eaten so far? $6 \text{ cycles} \times 7 = \mathbf{42 \text{ cookies}}$.
  * How many days have passed? $6 \text{ cycles} \times 2 \text{ days} = \mathbf{12 \text{ days}}$.

* **Step 5: Finish the remaining 6 cookies step-by-step.**  
  * **Day 13 (A's turn):** A steps up and eats **4 cookies**.  
    Cookies left $= 6 - 4 = \mathbf{2 \text{ cookies left}}$.
  * **Day 14 (B's turn):** B steps up. B eats at a speed of **3 cookies per day**, but only needs to eat **2 cookies**!  
    Time needed by B $= \mathbf{\frac{2}{3} \text{ of a day}}$.

* **Step 6: Add all the days together:**  
  $$\text{Total Time} = 12 \text{ days} + 1 \text{ day} + \frac{2}{3} \text{ day} = \mathbf{13 \frac{2}{3} \text{ days}}!$$

---

## 🎯 Model 5: Pipes & Cisterns (The Leaking Bucket)

### 💡 The Only Difference: Negative Work!
Pipes and Cisterns is 100% identical to Time & Work, with one single twist:
* **Inlet Pipe (Tap):** Adds water $\implies$ **Positive Speed (+)**
* **Outlet Pipe (Leak):** Removes water $\implies$ **Negative Speed (-)**

---

### ❓ The Problem
> Pipe A fills a tank in **15 hours**, and Pipe B fills it in **20 hours**. Due to a leak C at the bottom, it takes **30 hours** to fill the tank when all three are open. How many hours would leak C alone take to completely empty a full tank?

### 🧩 First-Principles Walkthrough
* **Step 1: Find Tank Capacity (LCM of 15, 20, 30).**  
  $\text{LCM}(15, 20, 30) = \mathbf{60 \text{ liters}}$.

* **Step 2: Find hourly speeds.**  
  * Pipe A adds: $60 \div 15 = \mathbf{+4 \text{ liters/hour}}$
  * Pipe B adds: $60 \div 20 = \mathbf{+3 \text{ liters/hour}}$
  * Net Speed of all three $(A + B - C) = 60 \div 30 = \mathbf{+2 \text{ liters/hour}}$

* **Step 3: Set up the simple balance equation.**  
  $$\text{Pipe A} + \text{Pipe B} - \text{Leak C} = \text{Net Speed}$$
  $$(+4) + (+3) - C = +2$$
  $$7 - C = 2 \implies C = \mathbf{5 \text{ liters/hour}}$$
  *(Leak C drains 5 liters of water every hour).*

* **Step 4: How long does Leak C take to drain the whole 60-liter tank?**  
  $$\text{Time to Empty} = \frac{60 \text{ liters}}{5 \text{ liters/hour}} = \mathbf{12 \text{ hours}}!$$

---

## 🎯 Model 6: The Master Construction Formula ($M_1 D_1 H_1 / W_1$)

### 💡 Why Does This Formula Exist?
Imagine a construction site. If you hire **more men**, you get **more work done**. If they work **more days**, they do **more work**. If they work **more hours**, they do **more work**.  
Therefore, the **Total Human Effort** put into a job is:
$$\text{Effort} = \text{Men} \times \text{Days} \times \text{Hours}$$

Since effort produces work, the ratio of **Effort spent per unit of Work produced** never changes:
$$\mathbf{\frac{M_1 \times D_1 \times H_1}{W_1} = \frac{M_2 \times D_2 \times H_2}{W_2}}$$

---

### ❓ The Problem
> If **15 men** working **8 hours a day** can build a **120-meter road** in **10 days**, how many men working **6 hours a day** are required to build a **360-meter road** in **20 days**?

### 🧩 First-Principles Walkthrough
* **Step 1: Match the given numbers to our labels:**  
  * **Team 1:**  
    $M_1 = 15 \text{ men}, \quad D_1 = 10 \text{ days}, \quad H_1 = 8 \text{ hours}, \quad W_1 = 120 \text{ meters}$
  * **Team 2:**  
    $M_2 = ? \text{ (what we want)}, \quad D_2 = 20 \text{ days}, \quad H_2 = 6 \text{ hours}, \quad W_2 = 360 \text{ meters}$

* **Step 2: Plug directly into the formula:**  
  $$\frac{15 \times 10 \times 8}{120} = \frac{M_2 \times 20 \times 6}{360}$$

* **Step 3: Simplify both sides cleanly (Zero panic):**  
  * Look at the left side:  
    $15 \times 10 \times 8 = 1200$  
    $\frac{1200}{120} = \mathbf{10}$
  * Look at the right side:  
    $20 \times 6 = 120$  
    $\frac{M_2 \times 120}{360} = \mathbf{\frac{M_2}{3}}$ (since $120/360 = 1/3$)

* **Step 4: Solve for $M_2$:**  
  $$10 = \frac{M_2}{3}$$
  $$M_2 = 10 \times 3 = \mathbf{30 \text{ men}}!$$

---

## ⚡ The 3-Second Exam Decision Table

Whenever a Time & Work question appears on your screen, use this decision tree:

| If the question looks like... | Your Instant Strategy |
| :--- | :--- |
| **"A takes X days, B takes Y days, together?"** | $\text{LCM} \div (\text{Rate A} + \text{Rate B})$. |
| **"Someone leaves midway"** | Calculate work done before leaving $\to$ subtract $\to$ divide remainder by remaining person. |
| **"A is 3 times as good as B"** | Invert the ratio ($3:1 \implies 1:3$), match the difference to days, then find actual days. |
| **"Working on alternate days"** | Bundle 2 days into 1 cycle $\to$ multiply cycles $\to$ step through remainder individually. |
| **"Taps and Leaks"** | Inlets are $(+)$, leaks are $(-)$. Subtract leak rate from inlet rates. |
| **"Men, days, hours, food, or walls"** | Set up $\frac{M_1 D_1 H_1}{W_1} = \frac{M_2 D_2 H_2}{W_2}$ and cross-multiply. |
