# 05 — Time, Speed & Distance (TSD), Trains & Races

> **Track:** Quantitative Reasoning Level 1  
> **Syllabus Module:** 05 — Time, Speed & Distance  
> **Format:** Formula Cheatsheet + Core Behavioral Mechanics + 6 Fully Solved Model Archetypes  
> **Target Velocity:** 90 Seconds per MCQ

---

## 🧭 The Core Mental Model: The Ratio & Freeze-Frame Method

Most people fail TSD questions in aptitude tests because they set up heavy algebraic equations with $x$ and $y$. In a 90-second exam, **algebra is your enemy; ratios and relative reference frames are your weapon.**

```
                       Distance = Speed × Time
                                  │
         ┌────────────────────────┴────────────────────────┐
         ▼                                                 ▼
Distance is Constant (D₁ = D₂)                   Time is Constant (T₁ = T₂)
Speed & Time are INVERSELY proportional:         Distance & Speed are DIRECTLY proportional:
        S₁ / S₂ = T₂ / T₁                                D₁ / D₂ = S₁ / S₂
(Go 2x faster ⟹ take half the time)             (Go 2x faster ⟹ cover 2x the distance)
```

### 1. The Metric Unit Invariant
Never mix hours with meters or seconds with kilometers:
$$\text{Speed in } \text{m/s} = \text{Speed in } \text{km/h} \times \frac{5}{18}$$
$$\text{Speed in } \text{km/h} = \text{Speed in } \text{m/s} \times \frac{18}{5}$$

> **First-Principles Proof:**  
> $1 \text{ km} = 1000 \text{ m}$ and $1 \text{ hour} = 3600 \text{ seconds}$.  
> $\frac{1000 \text{ m}}{3600 \text{ s}} = \frac{10}{36} = \frac{5}{18} \text{ m/s}$.  
> **Memory Trick:** Small unit ($\text{m/s}$) needs small number on top ($\frac{5}{18}$). Big unit ($\text{km/h}$) needs big number on top ($\frac{18}{5}$).

---

## ⚡ Master Formula & Speed Cheatsheet

| Scenario | Condition | Formula / Rapid Shortcut | High-Frequency Exam Trap |
| :--- | :--- | :--- | :--- |
| **Average Speed** | Equal Distances ($d_1 = d_2$) | $V_{\text{avg}} = \frac{2 v_1 v_2}{v_1 + v_2}$ | **Never** take arithmetic mean $\frac{v_1 + v_2}{2}$ unless *times* are equal. |
| **Average Speed** | Equal Times ($t_1 = t_2$) | $V_{\text{avg}} = \frac{v_1 + v_2}{2}$ | Only valid if spent equal duration at each speed. |
| **General Average Speed** | Varying $d$ and $t$ | $V_{\text{avg}} = \frac{\text{Total Distance}}{\text{Total Time}} = \frac{d_1 + d_2 + \dots}{t_1 + t_2 + \dots}$ | Always sum total distance and total time separately. |
| **Relative Speed** | Opposite Directions ($\to \leftarrow$) | $S_{\text{rel}} = S_1 + S_2$ | Speeds **add** (gap closes faster). |
| **Relative Speed** | Same Direction ($\to \to$) | $S_{\text{rel}} = |S_1 - S_2|$ | Speeds **subtract** (overtaking takes longer). |
| **Train vs. Point Object** | Pole, standing person, post | $D = L_{\text{train}}$ | Point object length is strictly **0**. |
| **Train vs. Extended Object**| Platform, bridge, tunnel, train | $D = L_{\text{train}} + L_{\text{object}}$ | Must clear the sum of *both* lengths. |
| **Late / Early Invariant** | Speed $S_1 \to$ late by $t_1$, $S_2 \to$ early by $t_2$ | $D = \frac{S_1 \cdot S_2}{|S_1 - S_2|} \times \Delta T_{\text{total}}$ | $\Delta T_{\text{total}} = \text{Late} + \text{Early}$. Convert minutes to hours! |
| **Races: Beat by Distance & Time**| $A$ beats $B$ by $x$ meters or $t$ seconds | $\text{Speed of } B = \frac{x}{t}$ | $B$ would take $t$ seconds to run the missing $x$ meters. |
| **Boats & Streams** | Downstream ($D$) / Upstream ($U$) | $S_{\text{boat}} = \frac{D + U}{2}, \quad S_{\text{stream}} = \frac{D - U}{2}$ | $D = B + S$, $U = B - S$. Boat must be $>0$. |

---

## 🛠️ The 6 Core Model Archetypes & Worked Solutions

---

### Archetype 1: Average Speed & The Equal-Distance Trap
> **Question:**  
> A commuter drives from Bangalore to Mysore at a speed of $60\text{ km/h}$ and immediately returns along the same route at $40\text{ km/h}$. What is the average speed for the entire round trip?

#### 🧠 The Behavior & First Principles
Average speed is **NOT** $\frac{60 + 40}{2} = 50\text{ km/h}$.  
Because the distance is identical both ways, the commuter drives slower on the return trip, which means they spend **more time** traveling at $40\text{ km/h}$ than at $60\text{ km/h}$. The true average must tilt towards the slower speed.

#### ⚡ Method 1: The LCM Smart-Distance Method (Zero Formula, Zero Algebra)
1. Pick a convenient distance: $\text{LCM}(60, 40) = 120\text{ km}$.
2. Let one-way distance $= 120\text{ km}$.
   - Time going $= \frac{120}{60} = 2\text{ hours}$.
   - Time returning $= \frac{120}{40} = 3\text{ hours}$.
3. $\text{Total Distance} = 120 + 120 = 240\text{ km}$.
4. $\text{Total Time} = 2 + 3 = 5\text{ hours}$.
$$\text{Average Speed} = \frac{\text{Total Distance}}{\text{Total Time}} = \frac{240\text{ km}}{5\text{ h}} = \mathbf{48\text{ km/h}}$$

#### ⚡ Method 2: The Direct Harmonic Formula
$$V_{\text{avg}} = \frac{2 \cdot v_1 \cdot v_2}{v_1 + v_2} = \frac{2 \cdot 60 \cdot 40}{60 + 40} = \frac{4800}{100} = \mathbf{48\text{ km/h}}$$

---

### Archetype 2: The Late vs. Early Scenario (Product-over-Difference Shortcut)
> **Question:**  
> If a student walks to college at $4\text{ km/h}$, they arrive $10\text{ minutes}$ late. If they walk at $5\text{ km/h}$, they arrive $5\text{ minutes}$ early. Find the distance between the student's home and college.

#### 🧠 The Behavior & First Principles
The distance $D$ is constant. Increasing speed from $4\text{ km/h}$ to $5\text{ km/h}$ saves a total time difference:
$$\Delta T = 10\text{ min late} - (-5\text{ min early}) = 15\text{ minutes} = \frac{15}{60}\text{ hours} = \frac{1}{4}\text{ hour}$$

#### ⚡ Solution by Ratio of Speeds
1. $\text{Speed Ratio } S_1 : S_2 = 4 : 5$.
2. Since distance is constant, $\text{Time Ratio } T_1 : T_2 = 5 : 4$.
3. Difference in time ratio units $= 5 - 4 = 1\text{ unit}$.
4. We know $1\text{ unit} = 15\text{ minutes} = \frac{1}{4}\text{ hour}$.
5. Therefore, actual time $T_1 = 5 \text{ units} \times \frac{1}{4} = \frac{5}{4}\text{ hours}$.
6. $\text{Distance} = S_1 \times T_1 = 4\text{ km/h} \times \frac{5}{4}\text{ h} = \mathbf{5\text{ km}}$.

#### 🚀 The 10-Second Master Shortcut Formula
$$D = \frac{S_1 \cdot S_2}{|S_1 - S_2|} \times \Delta T_{\text{hours}} = \frac{4 \times 5}{|4 - 5|} \times \frac{15}{60} = \frac{20}{1} \times \frac{1}{4} = \mathbf{5\text{ km}}$$

---

### Archetype 3: Train Crossing a Moving Person / Train (Relative Speed)
> **Question:**  
> A $180\text{ m}$ long train moving at $54\text{ km/h}$ overtakes a cyclist riding in the **same direction** at $18\text{ km/h}$. How many seconds does the train take to completely cross the cyclist?

#### 🧠 The Behavior & First Principles
1. **The Target:** The cyclist is a point object. Length $L_{\text{cyclist}} = 0$.
2. **Total Distance to clear:** Just the train's own length $= 180\text{ m}$.
3. **Relative Frame:** Both move in the **same direction**.  
   Relative Speed $= S_{\text{train}} - S_{\text{cyclist}} = 54 - 18 = 36\text{ km/h}$.
4. Convert to $\text{m/s}$:
   $$36\text{ km/h} = 36 \times \frac{5}{18} = 10\text{ m/s}$$
5. Time taken:
   $$\text{Time} = \frac{\text{Distance}}{\text{Relative Speed}} = \frac{180\text{ m}}{10\text{ m/s}} = \mathbf{18\text{ seconds}}$$

---

### Archetype 4: Two Trains Crossing Each Other (Opposite Directions)
> **Question:**  
> Train A ($150\text{ m}$ long) travels at $72\text{ km/h}$, and Train B ($250\text{ m}$ long) travels at $108\text{ km/h}$ on parallel tracks towards each other (**opposite directions**). From the moment their front engines meet, how long does it take for them to completely clear each other?

#### 🧠 The Behavior & First Principles
1. **Total Distance:** The rear bumpers must completely pass each other.
   $$D_{\text{total}} = L_A + L_B = 150 + 250 = 400\text{ m}$$
2. **Relative Speed (Opposite Direction $\to \leftarrow$):**
   $$S_{\text{rel}} = S_A + S_B = 72 + 108 = 180\text{ km/h}$$
3. Convert to $\text{m/s}$:
   $$180 \times \frac{5}{18} = 10 \times 5 = 50\text{ m/s}$$
4. Time taken:
   $$\text{Time} = \frac{D_{\text{total}}}{S_{\text{rel}}} = \frac{400\text{ m}}{50\text{ m/s}} = \mathbf{8\text{ seconds}}$$

---

### Archetype 5: Linear Races & Head Starts (Distance vs. Time)
> **Question:**  
> In a $1000\text{ m}$ race, Runner A gives Runner B a head start of $100\text{ m}$ and still beats Runner B by $20\text{ seconds}$. If Runner A's speed is $5\text{ m/s}$, find the speed of Runner B.

#### 🧠 The Behavior & First Principles
- A runs the full course: $D_A = 1000\text{ m}$.
- B has a head start of $100\text{ m}$, so B only needs to run:
  $$D_B = 1000 - 100 = 900\text{ m}$$
- A takes time:
  $$T_A = \frac{D_A}{S_A} = \frac{1000\text{ m}}{5\text{ m/s}} = 200\text{ seconds}$$
- A beats B by $20\text{ seconds}$. That means B was still on the track for $20\text{ seconds}$ longer:
  $$T_B = T_A + 20 = 200 + 20 = 220\text{ seconds}$$
- Speed of Runner B:
  $$S_B = \frac{D_B}{T_B} = \frac{900\text{ m}}{220\text{ s}} = \frac{90}{22} = \frac{\mathbf{45}}{\mathbf{11}}\text{ m/s} \approx \mathbf{4.09\text{ m/s}}$$

> [!TIP]
> **The Golden Race Heuristic:**  
> If "A beats B by $x$ meters or $t$ seconds", it means:  
> **In that final gap, B takes $t$ seconds to cover $x$ meters.**  
> Therefore, $S_B = \frac{x}{t}$ instantly!

---

### Archetype 6: Boats & Streams / Escalators (Current Assist & Opposition)
> **Question:**  
> A motorboat travels $36\text{ km}$ downstream in $2\text{ hours}$ and returns the same distance upstream in $3\text{ hours}$. What is the speed of the motorboat in still water, and what is the speed of the river current?

#### 🧠 The Behavior & First Principles
Let $B = \text{Speed of boat in still water}$, $C = \text{Speed of river current}$.
- **Downstream Speed ($D = B + C$):** Current aids motion $\implies D = \frac{36\text{ km}}{2\text{ h}} = 18\text{ km/h}$.
- **Upstream Speed ($U = B - C$):** Current resists motion $\implies U = \frac{36\text{ km}}{3\text{ h}} = 12\text{ km/h}$.

#### ⚡ Rapid Solution (Sum and Difference of Speeds)
$$B = \frac{D + U}{2} = \frac{18 + 12}{2} = \frac{30}{2} = \mathbf{15\text{ km/h}}$$
$$C = \frac{D - U}{2} = \frac{18 - 12}{2} = \frac{6}{2} = \mathbf{3\text{ km/h}}$$

---

## 🎯 90-Second Exam Trap-Detector & Sanity Check

```
                       Quick MCQ Elimination Checklist
 ┌───────────────────────────┬─────────────────────────────────────────────────────────┐
 │ Exam Trap                 │ How to Spot and Evade in 5 Seconds                      │
 ├───────────────────────────┼─────────────────────────────────────────────────────────┤
 │ 1. Unit Mismatch          │ Speed in km/h, time in seconds? Multiply by 5/18 first! │
 │ 2. Arithmetic Mean Trap   │ If distances are equal, V_avg CANNOT be (v1+v2)/2.      │
 │                           │ It is always LESS than the arithmetic mean.             │
 │ 3. Train vs Platform      │ Did you forget to add the platform length to distance?  │
 │ 4. Opposite vs Same Dir   │ Opposite = (+), Same = (-). Watch overtaking wording.   │
 │ 5. Race Head Start        │ Head start of 50m in 1000m means B only runs 950m!      │
 └───────────────────────────┴─────────────────────────────────────────────────────────┘
```
