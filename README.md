# ⚡ GRIT: Deep-Tech & Systems Mastery

> **First-Principles, High-Yield Engineering Notes & Frameworks.**  
> Built for rigorous technical assessments, deep-tech interviews, and engineering mastery. Every concept balances real-world intuition, exact mathematical and system specifications, and high-frequency exam traps.

---

## 🏛️ Repository Organization

This repository is structured into distinct skill tracks, each maintained as a modular subject domain:

```
GRIT/
├── CS_Fundamentals/      # Operating Systems, DBMS, Computer Networks, OOP
│   └── 01.1 - Deadlock & The 4 Coffman Invariants.md
├── Applied_GenAI/        # RAG, RAGAS, Agentic Systems, Fine-Tuning
│   └── README.md
└── README.md
```

---

## 📚 Skill Tracks & Curricula

### ⚙️ 1. [CS Fundamentals](CS_Fundamentals/)
Core systems foundations across the classic software stack:
* **Operating Systems:**
  * [x] [01.1 - Deadlock & The 4 Coffman Invariants](CS_Fundamentals/01.1%20-%20Deadlock%20&%20The%204%20Coffman%20Invariants.md)  
    *Coffman Invariants, RAG Single vs. Multi-Instance Cycles, C POSIX Mutex Ordering, Universal Threshold Formula ($m \ge n(k - 1) + 1$).*
  * [x] [01.2 - Deadlock Handling: Prevention, Avoidance & Detection](CS_Fundamentals/01.2%20-%20Deadlock%20Handling%20%28Avoidance,%20Bankers%20Algorithm%20&%20Detection%29.md)  
    *Prevention vs. Avoidance vs. Detection, State Space Topography, Banker's Algorithm Simulation, WFG Cycles & Aging.*
  * [ ] **01.3 - CPU Scheduling Fundamentals:** Turnaround, Wait Time, FCFS, SJF, SRTF & Starvation
  * [ ] **01.4 - Round Robin (RR) & Quantum Boundary Collapse:** $q \to 0$ vs $q \to \infty$ Context-Switch Latency
  * [ ] **01.5 - Virtual Memory & Paging:** Logical-to-Physical Translation, TLB Hits & EMAT Formula
  * [ ] **01.6 - Page Faults & Thrashing:** The MMU Trap Sequence & Working Set Invariants
  * [ ] **01.7 - Page Replacement Algorithms:** Belady’s Paradox (FIFO) & Stack Algorithms (LRU/OPT)
* [x] [02 - DBMS](CS_Fundamentals/02%20-%20DBMS%20%28ACID%20Logs,%20Normalization%201NF%20to%20BCNF%20&%20B+%20Trees%29.md)  
  *Transaction Theory & ACID (Undo log for Atomicity, Redo/WAL for Durability), ANSI Isolation phenomena (Dirty, Non-repeatable, Phantom read), Normalization (1NF to BCNF), and B+ Tree Index Architecture (Fan-out, doubly-linked leaves).*
* [x] [03 - Computer Networks](CS_Fundamentals/03%20-%20Computer%20Networks%20%28TCP%203-Way%20Handshake,%20UDP%20&%20RFC%209110%20HTTP%29.md)  
  *TCP 3-Way Handshake & Walkie-Talkie model, Why 2-Way fails (half-open connections), TCP vs UDP (Registered Mail vs Megaphone, 20-60B vs 8B header), RFC 9110 HTTP codes (401 Auth vs 403 Forbidden, 502 vs 504).*
* [x] [04 - OOPs & C++ Architecture](CS_Fundamentals/04%20-%20OOPs%20&%20C++%20Architecture%20%28vtable,%20vptr%20&%20Diamond%20Problem%29.md)  
  *Dynamic Dispatch mechanics (static `vtable` in `.rodata`, hidden `vptr` at offset 0, 1 pointer indirection), The Diamond Problem & `virtual inheritance` (`vbptr`), virtual destructors & abstract class constraints.*

---

### 🧠 2. [Applied Gen AI](Applied_GenAI/)
Modern generative AI engineering, production pipelines, and evaluation standards:
* **Retrieval-Augmented Generation (RAG):** Hybrid search, semantic embeddings, rerankers, and vector DB optimization.
* **RAGAS Evaluation Framework:** Faithfulness, Answer Relevance, Context Precision, and Context Recall.
* **Agentic Systems:** ReAct patterns, Reflexion self-correction loops, and structured tool-calling contracts.

---

### ⏱️ 3. [Quantitative Reasoning](Quantitative_Reasoning/)
*Test Pattern: 20 Questions | 30 Minutes (90s / question) | Moderate Difficulty*

* [ ] **01 - Number Systems:** Classification & Divisibility, Power Cycles & Remainder Cycles, LCM/HCF & Factor Counting
* [ ] **02 - Percentages & Applications:** Fraction-Percent Equivalence, Successive Change, Profit & Loss, Discount, SI & CI
* [ ] **03 - Ratios, Proportions & Applications:** Direct/Inverse Variation, Mixtures & Alligations, Partnerships
* [ ] **04 - Ages and Averages:** Age Equations & Timeline Shifts, Weighted Averages, Combined Average Invariants
* [x] [05 - Time, Speed & Distance](Quantitative_Reasoning/05%20-%20Time,%20Speed%20&%20Distance.md)  
  *Unit Conversions ($5/18$), Average Speed (Harmonic Mean), Relative Speed, Train Clearance Invariants, Races & Head-Starts, Boats & Streams.*
* [x] [06 - Basic Time & Work](Quantitative_Reasoning/06%20-%20Basic%20Time%20&%20Work.md)  
  *Work Efficiency, Worker Leaving Midway, Alternate Days, Pipes & Cisterns (Leaks), Wage Distribution & MDH Man-Chain Rule.*
* [x] [07 - Permutations, Combinations & Probability](Quantitative_Reasoning/07%20-%20Permutations,%20Combinations%20&%20Probability.md)  
  *Arrangements vs Selections, Repeating Letters, String & Gap Methods, Dictionary Rank, Circular & Polygon Diagonals, Hypergeometric Urn Draws, Two-Dice Pyramid, At Least One Rule.*

---

## 📖 How to Use with Obsidian

This repository is ready to be opened directly as an [Obsidian](https://obsidian.md/) vault.
1. Clone the repository:
   ```bash
   git clone https://github.com/nikhil49023/GRIT.git
   ```
2. Open Obsidian $\to$ **Open folder as vault** $\to$ Select the `GRIT` folder.
3. Enjoy full native Mermaid diagrams, LaTeX math rendering, and bi-directional wikilinks.

---

## 🤝 Contribution & License
Maintained by [Nikhil](https://github.com/nikhil49023). MIT Licensed — feel free to star, fork, and share with your peers!
