# 07 — Permutations, Combinations & Probability

> **Track:** Quantitative Reasoning Level 1  
> **Syllabus Module:** 07 — Permutations, Combinations & Probability  
> **Format:** Formula Cheatsheet + Core Behavioral Mechanics + 10 Fully Solved Model Archetypes  
> **Target Velocity:** 90 Seconds per MCQ  

---

## 🧭 The Core Mental Model: Arrangement vs. Selection

Every single problem in this domain reduces to one foundational question: **Does the order of items matter?**

```
                         Total Elements (n), Choose (r)
                                       │
            ┌──────────────────────────┴──────────────────────────┐
            ▼                                                     ▼
      ORDER MATTERS                                      ORDER DOES NOT MATTER
   Permutation: P(n, r)                                   Combination: C(n, r)
     ⁿPᵣ = n! / (n - r)!                                   ⁿCᵣ = n! / [r! (n - r)!]
            │                                                     │
   • Forming words / numbers                             • Selecting committees / teams
   • Seating in a row / ranks                            • Drawing balls from a bag
   • Assigning unique roles                              • Handshakes & Geometry lines
```

---

## ⚡ Master Formula & Speed Cheatsheet

| Scenario | Condition / Type | Formula / Rapid Shortcut | High-Frequency Exam Trap |
| :--- | :--- | :--- | :--- |
| **Permutation** | Order matters, no repetition | ${}^n P_r = \frac{n!}{(n - r)!}$ | Don't divide by $r!$ when roles/positions differ. |
| **Combination** | Order does NOT matter | ${}^n C_r = \frac{n!}{r!(n - r)!}$ | Use symmetry: ${}^n C_r = {}^n C_{n-r}$ (e.g. ${}^{10}C_8 = {}^{10}C_2 = 45$). |
| **Repetitive Letters**| $n$ items, items repeat $p, q, r$ times | $\text{Arrangements} = \frac{n!}{p! \cdot q! \cdot r!}$ | Must divide by factorials of identical elements. |
| **Items Always Together** | $k$ items must sit together | Treat $k$ items as **1 entity** $\to (n - k + 1)! \times k!$ | Always multiply by internal arrangement of bundle ($k!$). |
| **Items Never Together** | $k$ items must never sit together | **Gap Method:** Arrange others first, place in gaps | Do not subtract if constraints are complex; use gaps. |
| **Circular Permutation** | $n$ distinct persons at round table | $\text{Ways} = (n - 1)!$ | 1 fixed anchor breaks rotational symmetry. |
| **Necklace / Garland** | Reversible circular loop | $\text{Ways} = \frac{(n - 1)!}{2}$ | Clockwise and counterclockwise are identical. |
| **Handshakes** | $n$ people shake hands once | $\text{Total} = {}^n C_2 = \frac{n(n - 1)}{2}$ | Each pair is counted once. |
| **Polygon Diagonals** | $n$-sided polygon | $\text{Diagonals} = {}^n C_2 - n = \frac{n(n - 3)}{2}$ | Subtract the $n$ perimeter edges from all lines. |
| **Two-Dice Sum** | Sum $S$ from rolling two 6-sided dice | For $S \le 7$: $S - 1$<br>For $S \ge 8$: $13 - S$ | Total sample space is strictly 36. |
| **"At Least One" Trap**| Probability of $\ge 1$ occurrence | $P(\ge 1) = 1 - P(\text{None})$ | Calculating directly requires summing many cases. |
| **Independent Events** | Events $A$ and $B$ are independent | $P(A \cap B) = P(A) \times P(B)$ | Only multiply if outcome of A does not alter B. |

---

## 🛠️ The 10 Core Model Archetypes & Worked Solutions

---

### Model 1: Digit Formation with Even/Odd & Repetition Constraints

> **Question:**  
> Using the digits $\{1, 3, 5, 6, 8, 9\}$, with repetition allowed, how many 4-digit even numbers can be formed?

#### 🧠 The Behavior & First Principles
1. A number is **even** if and only if its units (last) digit is divisible by 2.
2. From the pool $\{1, 3, 5, 6, 8, 9\}$, only **6 and 8** are even (2 choices for units place).
3. The problem explicitly states **repetition is allowed**.
4. The remaining positions (Thousands, Hundreds, Tens) can each take any of the 6 available digits.

#### ⚡ Solution & Shortcut Method
* **Thousands Place:** 6 choices
* **Hundreds Place:** 6 choices
* **Tens Place:** 6 choices
* **Units Place (Even):** 2 choices $\{6, 8\}$

$$\text{Total 4-Digit Even Numbers} = 6 \times 6 \times 6 \times 2 = 216 \times 2 = \mathbf{432}$$

---

### Model 2: Dictionary Rank of a Word with Repeating Letters

> **Question:**  
> If all the words that can be formed using the letters of the word **"MAHESH"** are arranged in alphabetical order (as in a dictionary), what is the rank of the word "MAHESH"?

#### 🧠 The Behavior & First Principles
1. Inventory and alphabetical sort: **A, E, H, H, M, S** (Total 6 letters; 'H' repeats 2 times).
2. Count all words that appear strictly before "MAHESH" alphabetically by fixing starting letters.

#### ⚡ Solution & Shortcut Method
* **Words starting with A:** Remaining letters $\{E, H, H, M, S\}$:
  $$\frac{5!}{2!} = \frac{120}{2} = 60$$
* **Words starting with E:** Remaining letters $\{A, H, H, M, S\}$:
  $$\frac{5!}{2!} = \frac{120}{2} = 60$$
* **Words starting with H:** Fix one 'H'. Remaining letters $\{A, E, H, M, S\}$ are all distinct:
  $$5! = 120$$
* **Words starting with M:**
  * Sub-branch **M-A-E...**: Remaining $\{H, H, S\}$:
    $$\frac{3!}{2!} = 3$$
  * Sub-branch **M-A-H...**:
    * Next alphabetical is **M-A-H-E-H-S**: $1 \text{ word}$ (Rank 244)
    * Next alphabetical is **M-A-H-E-S-H**: **The Target Word!** (Rank 245)

$$\text{Total Rank} = 60 + 60 + 120 + 3 + 1 + 1 = \mathbf{245}$$

---

### Model 3: Restricted Word Arrangements — "Always Together" (String Method)

> **Question:**  
> In how many ways can the letters of the word **"CORPORATION"** be arranged such that all the vowels always come together?

#### 🧠 The Behavior & First Principles
1. Letter breakdown:
   * Total = 11 letters.
   * Vowels: $\{O, O, A, I, O\} \implies 5$ vowels ('O' repeats 3 times).
   * Consonants: $\{C, R, P, R, T, N\} \implies 6$ consonants ('R' repeats 2 times).
2. **String Method:** Tie the 5 vowels into **1 single super-letter** `[O, O, A, I, O]`.

#### ⚡ Solution & Shortcut Method
1. **Outer units to arrange:** 6 consonants + 1 vowel bundle $= \mathbf{7 \text{ units}}$:
   $$\text{Outer Arrangements} = \frac{7!}{2!} = \frac{5040}{2} = 2520$$
2. **Inner bundle arrangements:** 5 vowels with 'O' repeating 3 times:
   $$\text{Inner Arrangements} = \frac{5!}{3!} = \frac{120}{6} = 20$$
3. **Total Valid Arrangements:**
   $$\text{Total} = 2520 \times 20 = \mathbf{50,400}$$

---

### Model 4: Restricted Word Arrangements — "Never Together" (Gap Method)

> **Question:**  
> In how many ways can the letters of the word **"EQUATION"** be arranged such that no two consonants are ever together?

#### 🧠 The Behavior & First Principles
1. Total = 8 letters (Vowels: E, U, A, I, O $= 5$; Consonants: Q, T, N $= 3$).
2. **The Gap Method Invariant:** When elements must **never** be adjacent, arrange the *unrestricted* elements first, then place the restricted elements into the empty gaps between and around them.

#### ⚡ Solution & Shortcut Method
1. Arrange the 5 vowels:
   $$\text{Ways to arrange vowels} = 5! = 120$$
2. Identify available gaps created by 5 vowels:
   $$\_ \text{ V } \_ \text{ V } \_ \text{ V } \_ \text{ V } \_ \text{ V } \_ \implies \mathbf{6 \text{ gaps}}$$
3. Choose 3 gaps out of 6 for the 3 distinct consonants and arrange them:
   $${}^6 P_3 = 6 \times 5 \times 4 = 120$$
4. **Total Valid Arrangements:**
   $$\text{Total} = 120 \times 120 = \mathbf{14,400}$$

---

### Model 5: Committee Selection with "At Least / At Most" Constraints

> **Question:**  
> A team of **5 members** is to be selected from **6 men** and **4 women**. In how many ways can the team be selected such that it contains **at least 2 women**?

#### 🧠 The Behavior & First Principles
"At least 2 women" means we must account for all disjoint cases:
* Case 1: 2 Women AND 3 Men
* Case 2: 3 Women AND 2 Men
* Case 3: 4 Women AND 1 Man

#### ⚡ Solution & Shortcut Method
* **Case 1 (2W, 3M):**
  $${}^4 C_2 \times {}^6 C_3 = \frac{4 \times 3}{2} \times \frac{6 \times 5 \times 4}{3 \times 2 \times 1} = 6 \times 20 = 120$$
* **Case 2 (3W, 2M):**
  $${}^4 C_3 \times {}^6 C_2 = 4 \times 15 = 60$$
* **Case 3 (4W, 1M):**
  $${}^4 C_4 \times {}^6 C_1 = 1 \times 6 = 6$$

$$\text{Total Ways} = 120 + 60 + 6 = \mathbf{186}$$

---

### Model 6: Geometric Combinations (Points, Lines, Triangles, Diagonals)

> **Question:**  
> (A) There are 12 points on the circumference of a circle. How many distinct triangles can be formed?  
> (B) How many diagonals does a regular decagon (10-sided polygon) have?

#### 🧠 The Behavior & First Principles
* **Triangles on a Circle:** Since all points lie on a circle, no three points can ever be collinear. Any selection of 3 points forms exactly 1 unique triangle $\implies {}^n C_3$.
* **Polygon Diagonals:** A polygon with $n$ vertices has ${}^n C_2$ total connecting line segments. Exactly $n$ of these lines are the outer edges/sides. The remaining lines are internal diagonals $\implies {}^n C_2 - n$.

#### ⚡ Solution & Shortcut Method
* **Part A (Triangles):**
  $${}^{12} C_3 = \frac{12 \times 11 \times 10}{3 \times 2 \times 1} = 2 \times 11 \times 10 = \mathbf{220}$$
* **Part B (Diagonals for $n = 10$):**
  $$\text{Diagonals} = \frac{n(n - 3)}{2} = \frac{10(10 - 3)}{2} = \frac{10 \times 7}{2} = \mathbf{35}$$

---

### Model 7: Urn & Ball Selection Without Replacement (Hypergeometric)

> **Question:**  
> A bag contains **6 red**, **5 blue**, and **4 green** balls. Three balls are drawn at random without replacement. What is the probability that **at least one ball of each color** is drawn?

#### 🧠 The Behavior & First Principles
1. Total balls $= 6 + 5 + 4 = 15$ balls.
2. Number of balls drawn $= 3$.
3. "At least one of each color" when drawing exactly 3 balls means we must draw **strictly 1 Red, 1 Blue, and 1 Green**.

#### ⚡ Solution & Shortcut Method
1. **Total Sample Space (${}^{15} C_3$):**
   $${}^{15} C_3 = \frac{15 \times 14 \times 13}{3 \times 2 \times 1} = 5 \times 7 \times 13 = 455$$
2. **Favorable Outcomes (1 Red, 1 Blue, 1 Green):**
   $$\text{Favorable} = {}^6 C_1 \times {}^5 C_1 \times {}^4 C_1 = 6 \times 5 \times 4 = 120$$
3. **Probability:**
   $$P = \frac{\text{Favorable}}{\text{Total}} = \frac{120}{455} = \frac{120 \div 5}{455 \div 5} = \mathbf{\frac{24}{91}}$$

---

### Model 8: Position-Constrained Word Probability

> **Question:**  
> All letters of the word **"PENCIL"** are written on individual cards. If a 5-letter arrangement is formed by randomly selecting 5 cards without repetition, what is the probability that the arrangement begins with a consonant and ends with a vowel?

#### 🧠 The Behavior & First Principles
* Letters in "PENCIL": 6 distinct letters.
  * Consonants: $\{P, N, C, L\} \implies 4$ consonants.
  * Vowels: $\{E, I\} \implies 2$ vowels.
* Arrangement structure: `[Consonant] _ _ _ [Vowel]`.

#### ⚡ Solution & Shortcut Method
* **First card must be a consonant:**  
  $$P(\text{Position 1 is Consonant}) = \frac{4}{6} = \frac{2}{3}$$
* **Last card must be a vowel (5 cards remain, 2 are vowels):**  
  $$P(\text{Position 5 is Vowel} \mid \text{Pos 1 is Consonant}) = \frac{2}{5}$$
* **Net Joint Probability:**  
  $$P = \frac{2}{3} \times \frac{2}{5} = \mathbf{\frac{4}{15}}$$

*(Verification via Combinatorics: $\frac{{}^4 P_1 \times {}^2 P_1 \times {}^4 P_3}{{}^6 P_5} = \frac{4 \times 2 \times 24}{720} = \frac{192}{720} = \frac{4}{15}$.)*

---

### Model 9: Two-Dice Sums (The Pyramid Invariant)

> **Question:**  
> Two fair 6-sided dice are rolled simultaneously. What is the probability that the sum of the numbers appearing on top is **greater than 8**?

#### 🧠 The Behavior & First Principles
* Total outcomes for two dice $= 6 \times 6 = 36$.
* "Sum greater than 8" means sum is **9, 10, 11, or 12**.
* **Pyramid Rule for Sum $S \ge 8$:** Number of ways $= 13 - S$.

#### ⚡ Solution & Shortcut Method
* Sum = 9: $13 - 9 = 4$ ways $\{(3,6), (4,5), (5,4), (6,3)\}$
* Sum = 10: $13 - 10 = 3$ ways $\{(4,6), (5,5), (6,4)\}$
* Sum = 11: $13 - 11 = 2$ ways $\{(5,6), (6,5)\}$
* Sum = 12: $13 - 12 = 1$ way $\{(6,6)\}$

$$\text{Total Favorable Ways} = 4 + 3 + 2 + 1 = 10$$
$$P(\text{Sum} > 8) = \frac{10}{36} = \mathbf{\frac{5}{18}}$$

---

### Model 10: The "At Least One" Independent Event Complement Rule

> **Question:**  
> Three marksmen A, B, and C fire at a target simultaneously. Their probabilities of hitting the target are $\frac{1}{2}$, $\frac{2}{3}$, and $\frac{3}{4}$ respectively. What is the probability that the target is hit?

#### 🧠 The Behavior & First Principles
1. "The target is hit" means **at least one** marksman hits the target.
2. The only scenario where the target is NOT hit is when **all three marksmen miss**.
3. Since their shots are independent, multiply their individual failure probabilities.

#### ⚡ Solution & Shortcut Method
1. **Individual Failure Probabilities:**
   * $P(\bar{A}) = 1 - \frac{1}{2} = \frac{1}{2}$
   * $P(\bar{B}) = 1 - \frac{2}{3} = \frac{1}{3}$
   * $P(\bar{C}) = 1 - \frac{3}{4} = \frac{1}{4}$
2. **Probability that all three miss:**
   $$P(\text{All Miss}) = P(\bar{A}) \times P(\bar{B}) \times P(\bar{C}) = \frac{1}{2} \times \frac{1}{3} \times \frac{1}{4} = \frac{1}{24}$$
3. **Probability that target is hit:**
   $$P(\text{Target Hit}) = 1 - P(\text{All Miss}) = 1 - \frac{1}{24} = \mathbf{\frac{23}{24}}$$
