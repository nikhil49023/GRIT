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
* **DBMS:** ACID mechanics, WAL logs, Normalization (1NF through BCNF), and B+ Tree indexing.
* **Computer Networks:** TCP 3-way handshake (RFC 9293), TCP vs UDP, RFC 9110 HTTP status invariants (401 vs 403).
* **Object-Oriented Systems & C++:** Dynamic dispatch (`vtable`/`vptr`) and Diamond inheritance resolution.

---

### 🧠 2. [Applied Gen AI](Applied_GenAI/)
Modern generative AI engineering, production pipelines, and evaluation standards:
* **Retrieval-Augmented Generation (RAG):** Hybrid search, semantic embeddings, rerankers, and vector DB optimization.
* **RAGAS Evaluation Framework:** Faithfulness, Answer Relevance, Context Precision, and Context Recall.
* **Agentic Systems:** ReAct patterns, Reflexion self-correction loops, and structured tool-calling contracts.

---

### ⏱️ 3. [Quantitative Reasoning](Quantitative_Reasoning/)
High-speed mental shortcuts, model questions, and zero-fraction methods:
* [x] [01 - Time & Work and Pipes & Cisterns](Quantitative_Reasoning/01%20-%20Time%20&%20Work%20and%20Pipes%20&%20Cisterns.md)  
  *The LCM / Chocolate Method, Worker Leaving Midway, Inverse Efficiency Ratios, Alternate Days, Leaks, and $M_1 D_1 H_1 / W_1$ formula.*
* [ ] **02 - Speed, Time & Distance:** Relative Speed, Average Speed, Trains, Boats & Streams
* [ ] **03 - Percentages, Profit & Loss:** Multipliers, Successive Discounts, Dishonest Dealer, SI & CI
* [ ] **04 - Ratios, Mixtures & Alligations:** Ratio Chaining, Cross Alligation, Repeated Dilution
* [ ] **05 - Numbers, Divisibility & HCF/LCM:** Unit Digit Cyclicity, Remainder Theorem, Trailing Zeroes
* [ ] **06 - Permutations, Combinations & Probability:** Slot Method, Together/Separate, Committee Selection

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
