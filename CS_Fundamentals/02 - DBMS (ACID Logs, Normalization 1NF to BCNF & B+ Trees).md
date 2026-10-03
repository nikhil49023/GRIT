# 02 — DBMS: ACID Logs, Normalization (1NF to BCNF) & B+ Trees

> **Track:** CS Fundamentals Level 1  
> **Module:** 02 — Database Management Systems (DBMS)  
> **Format:** Real-Life Systems Mental Models + Formal SQL Invariants + High-Frequency MCQ Traps  
> **Target Velocity:** 60 Seconds per MCQ

---

## 🏛️ Module Overview: The 3 Core DBMS Pillars

```
┌────────────────────────────────────────────────────────────────────────┐
│                        CORE DBMS ARCHITECTURES                         │
├──────────────────────────┬─────────────────────────────┬───────────────┤
│ 1. Transaction Theory    │ 2. Schema Normalization     │ 3. B+ Trees   │
│    ACID Log Mechanics    │    Functional Dependencies  │    Leaf Layer │
│    Undo vs. Redo (WAL)   │    1NF ➔ 2NF ➔ 3NF ➔ BCNF   │    Doubly-Link│
└──────────────────────────┴─────────────────────────────┴───────────────┘
```

---

## 💾 1. Transaction Management & Physical ACID Implementation

### 🏦 Real-Life Analogy: The Bank Ledger & The Safety Pencil

A transaction is a single logical unit of work (e.g., Transferring $₹1,000$ from Account A to Account B: Debit A, Credit B).

| ACID Property   | Formal Technical Definition                                                                                                  | Real-Life Parallel                                                                               | Underlying Physical Engine Implementation                                                                                                                           |
| :-------------- | :--------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Atomicity**   | **All-or-Nothing:** Either every single SQL statement executes, or the entire transaction is rolled back with zero trace.    | If the power cuts after debiting A but before crediting B, the bank doesn't steal your money.    | **Undo Log:** Records "before-images". On crash or `ROLLBACK`, the engine reads backwards and undoes uncommitted changes.                                           |
| **Consistency** | Database moves from one valid state to another, preserving all explicit schema constraints, foreign keys, and domain checks. | Account balance cannot drop below $0$ if a `CHECK (balance >= 0)` constraint exists.             | Enforced by the query compiler and constraint checkers before commit.                                                                                               |
| **Isolation**   | Concurrent transactions execute without interfering with one another; intermediate uncommitted states are invisible.         | Two people buying concert tickets at the exact same millisecond don't corrupt each other's cart. | **Concurrency Control:** Two-Phase Locking (2PL) or Multi-Version Concurrency Control (**MVCC** snapshot isolation).                                                |
| **Durability**  | Once a transaction commits, its updates are **permanent and survive any power failure or OS crash**.                         | Once the ATM prints your receipt, a blackout 1 second later cannot wipe out your deposit.        | **Redo Log / Write-Ahead Logging (WAL):** Log records are flushed to disk **BEFORE** dirty data pages hit disk. On reboot, the engine replays the redo log forward. |

---

### 🔥 The 3 ANSI SQL Concurrency Phenomena (Must-Know for MCQs)

```
1. Dirty Read:
   Transaction 1 modifies a row (uncommitted).
   Transaction 2 READS that uncommitted value.
   Transaction 1 crashes and ROLLBACK occurs!
   👉 T2 just made business decisions based on "dirty garbage" that never officially existed!
   (Prevented in: Read Committed, Repeatable Read, Serializable).

2. Non-Repeatable Read:
   Transaction 1 reads row: balance = 500.
   Transaction 2 updates balance = 800 and COMMITS.
   Transaction 1 rereads the exact same row: balance = 800!
   👉 The same query inside the same transaction yielded different data!
   (Prevented in: Repeatable Read, Serializable).

3. Phantom Read:
   Transaction 1 queries: SELECT * WHERE age > 25 (returns 5 rows).
   Transaction 2 INSERTS a new person with age = 30 and COMMITS.
   Transaction 1 reruns: SELECT * WHERE age > 25 (returns 6 rows!).
   👉 A brand new "phantom" row appeared out of thin air!
   (Prevented strictly in: Serializable).
```

---

## 📐 2. Relational Schema Normalization (1NF through BCNF)

Normalization eliminates **data redundancy**, **insertion anomalies**, **deletion anomalies**, and **update anomalies**.

### 🔑 The 3 Key Definitions
1. **Superkey:** Any column (or set of columns) that uniquely identifies a row ($K \to R$).
2. **Candidate Key:** A **minimal** superkey (no redundant columns).
3. **Prime Attribute:** Any column that belongs to **at least ONE candidate key**.  
   *(Non-Prime Attribute = A column that belongs to NO candidate key).*

---

### 🪜 The 4 Normal Forms & Their Violation Rules

```
                      1NF: Atomic values only (no lists)
                       ▲
                       │
                      2NF: 1NF + NO Partial Dependencies
                           (Candidate Key Subset ➔ Non-Prime is FORBIDDEN)
                       ▲
                       │
                      3NF: 2NF + NO Transitive Dependencies
                           (Non-Prime ➔ Non-Prime is FORBIDDEN)
                       ▲
                       │
                     BCNF: For every non-trivial X ➔ Y,
                           X MUST be a Superkey!
```

---

### ⚡ The High-Speed Normalization Decision Table

| Normal Form | The Rule (What is Allowed?) | The Violation (What Breaks It?) | Fast 5-Second MCQ Trick |
| :--- | :--- | :--- | :--- |
| **1NF** | Every cell must contain a single **atomic** value. | A cell contains a list or repeating group: `Phones = [987..., 912...]`. | If table has no arrays or nested tables, it is in **1NF**. |
| **2NF** | In 1NF **AND** every non-prime attribute must depend on the **WHOLE** candidate key. | **Partial Dependency:** A non-prime column depends on only *part* of a composite candidate key. | **Golden Rule:** If the Candidate Key is a **single column**, the table is **AUTOMATICALLY in 2NF**! (Partial dependency is impossible). |
| **3NF** | In 2NF **AND** for every $X \to Y$:<br>1. $X$ is a Superkey, **OR**<br>2. $Y$ is a Prime Attribute. | **Transitive Dependency:** A non-prime column determines another non-prime column ($A \to B \to C$). | Check right-hand side $Y$: if $Y$ is prime, 3NF is **satisfied**! |
| **BCNF** | For every non-trivial $X \to Y$, **$X$ MUST be a Superkey**. | $X$ is not a superkey, even if $Y$ is a prime attribute! | BCNF is strictly stronger than 3NF. It eliminates the "or $Y$ is prime" exception. |

---

#### 🧪 Concrete Exam Example:
> Given Relation $R(A, B, C, D)$ with Primary Key $(A, B)$.  
> Dependencies: $(A, B) \to D$ and $A \to C$.  
> **What Normal Form is violated?**

- **Analysis:**
  - Primary Key is composite: $(A, B)$.
  - Candidate Key attributes: $A, B$ (Prime).
  - Non-prime attributes: $C, D$.
  - Look at $A \to C$: $A$ is a *proper subset* of candidate key $(A, B)$, and $C$ is non-prime.
  - This is a **Partial Dependency**!
  - **Verdict:** Violates **2NF**! (The table is only in 1NF).

---

## 🌲 3. B+ Tree Index Architecture (The Library Index)

Why do real databases (MySQL InnoDB, Postgres, SQLite) use **B+ Trees** for indexes instead of Binary Search Trees or standard B-Trees?

```
                                 [ 50 | 100 ]            <── Internal Node (Keys & Pointers ONLY)
                                ┌─────┼──────┐
                                ▼     ▼      ▼
                           [10|25] [60|75] [110|150]    <── Internal Node (No Data Records)
                            │   │   │   │   │    │
              ┌─────────────┘   └───┼───┼───┼────┘
              ▼                     ▼   ▼   ▼
       ┌─────────────┐       ┌─────────────┐       ┌─────────────┐
       │ 10 │ 25 │ 30├──────▶│ 50 │ 60 │ 75├──────▶│100 │110 │150│ <── Leaf Nodes
       │ Data Records│◀──────┤ Data Records│◀──────┤ Data Records│     (Doubly-Linked!)
       └─────────────┘       └─────────────┘       └─────────────┘
```

### ⚡ The 3 Architectural Invariants of B+ Trees

1. **Internal (Non-Leaf) Nodes Store ZERO Data Records:**
   - Internal nodes store **only search keys and child page pointers**.
   - **Why?** Maximizes the **fan-out**! In a 4KB/8KB disk block, you can pack hundreds of child pointers. A B+ Tree can index **millions of records with a depth of just 3 or 4 levels**. (Minimal disk I/O!).
2. **Leaf Nodes Store ALL Data Records / Row Pointers:**
   - Every single search key appears in the leaf level along with the actual row data (clustered) or tuple pointers (secondary).
3. **The Doubly-Linked Leaf Layer (Range Query Rocket):**
   - All leaf nodes are linked sequentially via a **doubly-linked list**.
   - **SQL Range Query:** `SELECT * FROM orders WHERE amount BETWEEN 50 AND 100`:
     - Traverse from root to the first leaf node ($50$) in $\mathcal{O}(\log_m N)$.
     - Then simply walk linearly along the doubly-linked list until $100$.
     - **Zero backtracking up the tree!** (Standard B-Trees require expensive in-order traversals back through parent nodes).

---

## ⚡ 60-Second MCQ Trap-Detector

```
                       Quick MCQ Elimination Checklist
 ┌───────────────────────────┬─────────────────────────────────────────────────────────┐
 │ Exam Question             │ The Instant Elimination Rule                            │
 ├───────────────────────────┼─────────────────────────────────────────────────────────┤
 │ Undo vs. Redo Log?        │ Undo = Atomicity (Rollback). Redo = Durability (WAL).   │
 │ Single-column candidate k?│ Automatically in 2NF! (Partial dependency impossible).  │
 │ BCNF vs. 3NF difference?  │ In 3NF, Y can be prime. In BCNF, X MUST be superkey!    │
 │ B+ Tree Leaf linkage?     │ Always linked as a DOUBLY-LINKED list for range scans.  │
 │ Where are rows in B+ Tree?│ Exclusively in LEAF nodes. Internal nodes hold keys only│
 └───────────────────────────┴─────────────────────────────────────────────────────────┘
```
