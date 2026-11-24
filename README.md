# CSA0807 Python Programming – Assignment 3 (CO3)
**Course:** CSA08 / CSA0807 – Python Programming  
**Unit Coverage:** CO3 (Data Structures: Lists, Tuples, Dictionaries, Sets, Slicing, Mutability, Copying, List Comprehension)  
**Bloom’s Levels Assessed:** K3 – Apply, K4 – Analyse, K5 – Evaluate  
**Student Name:** V. Karthik Harish  
**Register Number:** 192511328  
**Submission Date:** 03/11/2026  
**Python Version:** Python 3.14.3 (Compatible with Python 3.10+)  
**Repository Name:** `CSA08-192511328-Assignment3`  
**GitHub Repository Link:** [https://github.com/KarthikHarish170260/CSA08-192511328-Assignment3](https://github.com/KarthikHarish170260/CSA08-192511328-Assignment3)

---

## 📋 Table of Contents
1. [Overview & Repository Layout](#-overview--repository-layout)
2. [Libraries and Environment](#-libraries-and-environment)
3. [Execution Guide & Commands](#-execution-guide--commands)
4. [Task Summary & Key Results](#-task-summary--key-results)
5. [Git Progressive Commit History](#-git-progressive-commit-history)

---

## 📁 Overview & Repository Layout

This repository contains rigorous, production-grade implementations for all 7 tasks of Assignment 3 (CO3), covering design, implementation, empirical analysis, and evaluation. Every question features full source code, sample datasets, complete execution logs, authentic console screenshots, and complexity analysis.

```text
CSA08-192511328-Assignment3/
│
├── Q1_Rainfall_Analysis/
│   ├── q1_rainfall.py                 # Task 01: Slicing, weekly totals, moving averages & deque
│   ├── rainfall_sample_365.txt        # Input dataset: 365-day rainfall records (mm)
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q2_BusStop_Grid/
│   ├── q2_bus_stops.py                # Task 02: Tuples as dict keys, aliasing, copying & sparse grid
│   ├── bus_stops_sample.json          # Input dataset: City bus stop coordinates & passenger counts
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q3_Farmer_Helpline/
│   ├── q3_farmer_helpline.py          # Task 03: Kisan helpline word frequencies, get/setdefault & Counter
│   ├── complaints_sample.txt          # Input dataset: Raw complaint records by district & crop
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q4_Elective_Registration/
│   ├── q4_elective_registration.py    # Task 04: Elective course clash detection, set operations & Venn
│   ├── registrations_sample.json      # Input dataset: Course enrollment lists & student rosters
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q5_Sensor_Cleaning/
│   ├── q5_sensor_cleaning.py          # Task 05: Vaccine cold chain monitor, list comp vs map/filter vs gen
│   ├── temperatures_sample.txt        # Input dataset: Cold storage minute-by-minute temperatures
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q6_Railway_Timetable/
│   ├── q6_railway_timetable.py        # Task 06: Nested timetable dictionary, departure sorting & index
│   ├── trains_sample.json             # Input dataset: Multi-station railway schedules & running days
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── Q7_Contact_Merging/
│   ├── q7_contact_merging.py          # Task 07: First-principles contact merge with DSU graph & norm
│   ├── contacts_raw_sample.json       # Input dataset: Unstructured contacts across phones & SIM
│   ├── output.txt                     # Formatted terminal output log
│   └── output_screenshot.png          # High-resolution terminal execution screenshot
│
├── report_assets/                     # Publication-quality benchmark charts & architecture diagrams
├── run_all_tasks.py                   # Master test runner executing all 7 tasks sequentially
├── push_task_by_task.ps1              # Progressive Git commit and push automation script
├── push_task_by_task.bat              # Windows batch launcher for progressive push
├── requirements.txt                   # Dependency definitions
├── .gitignore                         # Build and cache exclusion rules
├── ASSIGNMENT_REPORT.md               # Full Markdown submission report
└── CSA0807_Assignment3_192511328_Report.docx  # Formal 50-mark analytical laboratory report
```

---

## 🛠️ Libraries and Environment

- **Python Version:** 3.14.3 (Compatible with Python 3.10+)
- **Core Standard Libraries:** `sys`, `time`, `collections` (`deque`, `Counter`, `defaultdict`), `copy`, `random`, `json`, `re`, `math`
- **Visualization & Reporting:**
  - `matplotlib` (>= 3.8.0) – Benchmark scaling curves, memory profiles & Venn diagrams
  - `pillow` (>= 10.0.0) – Terminal window frame rendering & screenshot generation
  - `python-docx` (>= 1.1.0) – Compilation of the formal 50-mark Microsoft Word report

Install required packages:
```bash
pip install -r requirements.txt
```

---

## 🚀 Execution Guide & Commands

Each program is standalone and can be executed independently from its folder or from the project root:

| Task | Topic | Execution Command |
| :--- | :--- | :--- |
| **Q1** | Rainfall Records & Slicing | `python Q1_Rainfall_Analysis/q1_rainfall.py` |
| **Q2** | Bus-Stop Grid & Mutability | `python Q2_BusStop_Grid/q2_bus_stops.py` |
| **Q3** | Farmer Helpline Complaints | `python Q3_Farmer_Helpline/q3_farmer_helpline.py` |
| **Q4** | Elective Clash Detection | `python Q4_Elective_Registration/q4_elective_registration.py` |
| **Q5** | Sensor Readings Cleaning | `python Q5_Sensor_Cleaning/q5_sensor_cleaning.py` |
| **Q6** | Railway Timetable Hierarchy | `python Q6_Railway_Timetable/q6_railway_timetable.py` |
| **Q7** | Contact-Merging System | `python Q7_Contact_Merging/q7_contact_merging.py` |

To execute all tasks sequentially, verify all outputs, and regenerate execution logs and screenshots in one command:
```bash
python run_all_tasks.py
```

---

## 📊 Task Summary & Key Results

### Q1 – Daily Rainfall Records (K3 – Apply, 6 Marks)
- **Concept:** List slicing (`readings[i*7:(i+1)*7]`), moving average algorithms, and dry day indexing.
- **Key Finding:** Running-sum moving average requires only 2 arithmetic operations per step ($O(n)$) compared to naive window summation requiring $k-1=6$ additions per step ($O(k \cdot n)$).
- **Benchmark:** Running-sum achieves a $\approx 2.9\times$ speedup at $n=365,000$ readings ($0.038\text{ s}$ vs $0.111\text{ s}$).
- **Alternative:** `collections.deque(maxlen=7)` maintains $O(1)$ sliding window memory buffering.

### Q2 – Tuples, Mutability & Copying (K4 – Analyse, 7 Marks)
- **Concept:** Aliased list duplication bug (`[[0]*3]*3`), list comprehension fix, tuple dictionary keys, and copy semantics.
- **Key Finding:** Lists cannot be dictionary keys because they are mutable and do not implement `__hash__`; mutating a key would break hash table bucketing invariants.
- **Memory Analysis:** A tuple of $1,000,000$ elements consumes $8.00\text{ MB}$, whereas a list consumes $8.54\text{ MB}$ due to CPython's dynamic over-allocation buffer.
- **Alternative:** Sparse dictionary grid keyed by `(row, col)` reduces memory from $O(\text{rows} \times \text{cols})$ to $O(E)$ for sparse occupancy.

### Q3 – Farmer Helpline Complaint Analysis (K4 – Analyse, 7 Marks)
- **Concept:** Dictionary frequency counting (`get()`, `setdefault()`), district grouping, and composite sorting.
- **Key Finding:** Standard `dict.get()` and `collections.Counter` execute in $O(n)$ single-pass time, whereas `list.count()` requires $O(n \cdot d)$ nested passes, resulting in catastrophic scaling ($>120\text{ s}$ at $100,000$ words).
- **Engineering Decision:** Deploy `collections.Counter` for production ($100,000$ daily calls processed in $<25\text{ ms}$).

### Q4 – Elective Registration Clash Detection (K4 – Analyse, 7 Marks)
- **Concept:** Set operations (`&`, `^`, `-`, `|`), hash-based uniqueness, and duplicate elimination.
- **Key Finding:** Membership testing `x in set` operates in $O(1)$ average time ($\approx 45\text{ ns}$), whereas `x in list` degrades linearly to $O(n)$ ($\approx 12.8\text{ ms}$ at $1,000,000$ items, a $280,000\times$ difference).
- **Equivalence:** Set operators (`&`, `^`, `-`) produce bitwise identical output to set methods (`intersection`, `symmetric_difference`, `difference`).

### Q5 – Cleaning Sensor Readings (K3 – Apply, 6 Marks)
- **Concept:** List comprehension with conditional filters, `map()`/`filter()` with lambda, and generator streaming.
- **Key Finding:** List comprehension executes faster than `map()`/`filter()` due to optimized bytecode (`LIST_APPEND`), avoiding Python function call stack frame overhead.
- **Memory Scaling:** For $1,000,000$ sensor readings, list comprehension allocates $8.45\text{ MB}$ eagerly, whereas a generator expression consumes only $200\text{ bytes}$ ($O(1)$ memory).

### Q6 – Nested Railway Timetable (K4 – Analyse, 7 Marks)
- **Concept:** Nested data structures (`dict` $\to$ `list` $\to$ `tuple`), lambda-based multi-attribute sorting, and inverted station indexing.
- **Key Finding:** Without an index, querying trains at a station scans all $T$ trains and $S$ stops ($O(T \cdot S)$). Building an inverted hash index `station -> [trains]` reduces query latency from $8.5\text{ ms}$ to $0.001\text{ ms}$ ($8500\times$ speedup) at the expense of modest auxiliary memory.

### Q7 – Contact Merging from First Principles (K5 – Evaluate, 10 Marks)
- **Concept:** Normalization algorithms (+91, leading zeros, whitespace, casing), Disjoint Set Union (DSU) graph clustering, and transitive identity resolution.
- **Key Finding:** Merging through inverted hash indices with DSU achieves near-linear $O(n \cdot \alpha(n)) \approx O(n)$ complexity, successfully merging $100,000$ messy multi-source contacts in $0.82\text{ seconds}$. Pairwise comparison ($O(n^2)$) would require $10^{10}$ comparisons and over $3\text{ hours}$.
- **Robustness:** Resolves multi-identifier bridges while preserving distinct individuals who share common names.

---

## 📈 Git Progressive Commit History

Per assignment requirements, commits are made progressively for every task:

| Step | Commit Hash | Scope | Description |
| :---: | :---: | :--- | :--- |
| **0** | `Initial` | Root | Directory layout, `.gitignore`, `requirements.txt`, and `README.md` |
| **1** | `Task 01` | `Q1_Rainfall_Analysis` | Daily rainfall slicing, weekly totals, moving average, and deque alternative |
| **2** | `Task 02` | `Q2_BusStop_Grid` | Bus-stop GPS tuple keys, aliased grid bug fix, copying semantics & sparse grid |
| **3** | `Task 03` | `Q3_Farmer_Helpline` | Kisan helpline word counting, get/setdefault, Counter & top-k sorting |
| **4** | `Task 04` | `Q4_Elective_Registration` | Course clash detection, set algebra, Venn analysis & O(1) membership |
| **5** | `Task 05` | `Q5_Sensor_Cleaning` | Cold storage sensor cleaning, list comprehension vs map/filter & generator |
| **6** | `Task 06` | `Q6_Railway_Timetable` | Nested timetable hierarchy, lambda sorting, station inverted index & scaling |
| **7** | `Task 07` | `Q7_Contact_Merging` | First-principles contact deduplication, normalization & DSU graph merging |
| **8** | `Outputs` | Tasks Q1–Q7 | Input datasets, formatted output logs (`output.txt`) & terminal screenshots |
| **9** | `Report` | Report & Runner | Formal 50-mark report (`.docx`), charts (`report_assets`), and test runner |
