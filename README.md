# ⚡ CS Fundamentals Mastery

> **First-Principles, High-Yield Computer Science Notes.**  
> Designed for university exams, technical interviews, and systems mastery. Balancing real-world physical intuitions, rigorous mathematical and kernel specifications, and high-frequency exam traps.

---

## 🏛️ The Three-Pillar Pedagogical Architecture

Every concept in this vault is deconstructed using a 3-step cognitive arc:
1. **Physical Intuition (The "Aha!" Mental Model):** Real-world mechanical analogies that remove the abstraction.
2. **Formal Kernel / Systems Specification:** Exact mathematical invariants, system call flows, and hardware-level mechanics.
3. **High-Yield Traps & Socratic Drills:** The exact misconceptions and boundary conditions tested in rigorous technical evaluations.

---

## 🗺️ Master Curriculum Roadmap

### ⚙️ Module 1: Operating Systems (OS)
* [x] [01.1 - Deadlock & The 4 Coffman Invariants](01.1%20-%20Deadlock%20&%20The%204%20Coffman%20Invariants.md)  
  *Coffman Invariants, RAG Single vs. Multi-Instance Cycles, C POSIX Mutex Ordering, Universal Threshold Formula ($m \ge n(k - 1) + 1$).*
* [ ] **01.2 - Deadlock Handling:** Prevention vs. Avoidance vs. Detection & Dijkstra’s Banker’s Algorithm
* [ ] **01.3 - CPU Scheduling Fundamentals:** Turnaround, Wait Time, FCFS, SJF, SRTF & Starvation
* [ ] **01.4 - Round Robin (RR) & Quantum Boundary Collapse:** $q \to 0$ vs $q \to \infty$ Context-Switch Latency
* [ ] **01.5 - Virtual Memory & Paging:** Logical-to-Physical Translation, TLB Hits & EMAT Formula
* [ ] **01.6 - Page Faults & Thrashing:** The MMU Trap Sequence & Working Set Invariants
* [ ] **01.7 - Page Replacement Algorithms:** Belady’s Paradox (FIFO) & Mathematical Immunity of Stack Algorithms (LRU/OPT)

### 🗄️ Module 2: Database Management Systems (DBMS) *(Coming Soon)*
* **2.1 Transaction Management & ACID Mechanics:** Undo Log (Rollback) vs. Redo Log (WAL)
* **2.2 Relational Normalization:** 1NF $\to$ 2NF $\to$ 3NF $\to$ BCNF Functional Dependencies
* **2.3 B+ Tree Index Architecture:** Clustered vs. Secondary Indexing & Doubly-Linked Leaf Layer

### 🌐 Module 3: Computer Networks (CN) *(Coming Soon)*
* **3.1 The TCP 3-Way Handshake (RFC 9293):** ISN Synchronization & 2-Way Handshake Failure Proof
* **3.2 TCP vs. UDP Protocol Engineering:** Byte Stream vs. Datagrams, Sliding Window Flow & Congestion
* **3.3 HTTP Status Standards (RFC 9110):** The Critical 401 Unauthorized vs. 403 Forbidden Invariant

### 🧱 Module 4: Object-Oriented Systems & C++ Architecture *(Coming Soon)*
* **4.1 Dynamic Dispatch:** Compiler `vtable` and `vptr` Memory Layout
* **4.2 The Diamond Problem:** Multiple Inheritance Memory Duplication & Virtual Base Pointers (`vbptr`)

---

## 📖 How to Use with Obsidian

This repository is structured as a standalone [Obsidian](https://obsidian.md/) vault.
1. Clone the repository:
   ```bash
   git clone https://github.com/nikhil49023/cs-fundamentals-mastery.git
   ```
2. Open Obsidian $\to$ **Open folder as vault** $\to$ Select the cloned directory.
3. Enjoy full native Mermaid diagrams, LaTeX math rendering, and bi-directional wikilinks.

---

## 🤝 Contribution & License
Maintained by [Nikhil](https://github.com/nikhil49023). MIT Licensed — feel free to star, fork, and share with your peers!
