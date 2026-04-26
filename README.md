# Process Mining Project – Sepsis Event Log Analysis

## 1. Project Overview

This project applies Process Mining techniques using the PM4Py library to analyze a real-world healthcare event log (Sepsis Cases). The main objectives are:

- Perform process discovery using Heuristics Miner and Inductive Miner
- Analyze event log characteristics
- Evaluate discovered models using conformance checking techniques
- Compare performance of different mining algorithms

---

## 2. Dataset

The dataset used is the **Sepsis Cases Event Log**, which contains clinical events related to patient treatment in a hospital environment.

Key characteristics:
- 1050 cases
- 15,214 events
- Average trace length: ~14.49 events
- Highly variable process with multiple treatment paths

---

## 3. Project Workflow

### 3.1 Data Import and Exploration
- Import XES event log using PM4Py
- Extract event attributes, start/end activities, and organizational resources
- Perform statistical analysis:
  - Variant distribution
  - Activity frequency
  - Case-level variability
  - Entropy and time-based analysis

---

### 3.2 Data Preprocessing
- Remove incomplete or invalid traces
- Filter cases based on length constraints
- Convert dataframe into event log format
- Sort events by timestamp

---

### 3.3 Process Discovery

#### Heuristics Miner
- Applied with dependency threshold tuning
- Generates Heuristics Net
- Converted to Petri Net for analysis

#### Inductive Miner (IMf)
- Noise threshold = 0.2
- Produces structured process tree
- Converted into sound Petri Net

---

### 3.4 Conformance Checking

#### Token-Based Replay
- Evaluates token consumption/production
- Measures fitness of log vs model

Results:
- Heuristics Miner: ~0.9281
- Inductive Miner: ~0.9796

#### Alignment-Based Conformance
- Computes optimal alignment between log and model
- Considers costs of deviations

Results:
- Heuristics Miner: ~0.8642
- Inductive Miner: ~0.9339

---

## 4. Key Findings

- Inductive Miner produces more structured and sound models
- Heuristics Miner is more flexible but less precise
- Inductive Miner achieves higher conformance scores in both TBR and alignment
- Event log shows high variability and concurrency in clinical processes

---

## 5. Tools and Libraries

- Python 3.10+
- PM4Py
- Pandas, NumPy
- Graphviz
- Jupyter Notebook

---

## 6. How to Run

```bash
pip install pm4py pandas numpy graphviz
