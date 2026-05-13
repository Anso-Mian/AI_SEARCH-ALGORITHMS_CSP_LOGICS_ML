# 🎓 AL2002 - Artificial Intelligence Lab: Student Performance Prediction

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.8+-blue)
![Dataset](https://img.shields.io/badge/Dataset-UCI-orange)

---

## 📋 Project Overview

This project implements comprehensive AI techniques to analyze and predict student academic performance. Using the UCI Student Performance dataset, we develop intelligent agents, search algorithms, and data analysis pipelines to understand patterns in student behavior and outcomes.

**Course:** AL2002 - Artificial Intelligence Lab  
**Track:** Track C  
**Institution:** FAST University  
**Members:** Ans Rizwan (24F-0779), Khalil (24F-0525), Shaheer (24F-0785)
**Academic Year:** 2024-2025

---

## 👥 Team Members

| ID | Name |
|---|---|
| 24F-0779 | Muhammad Ans Rizwan |
| 24F-0525 | Khalil |
| 24F-0785 | Shaheer Hayat |

---

## 📊 Dataset Information

**Dataset Name:** Student Performance Prediction (UCI)  
**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/student+performance)  
**Main File:** `student-mat.csv` (Mathematics)

### Dataset Features
- **Size:** 395 students × 33 attributes
- **Target Variable:** `G3` (Final grade)
- **Key Features:**
  - Demographics: age, gender, address type
  - Academic: previous grades (G1, G2), study time, failures
  - Social: absences, health, Dalc (workday alcohol), Walc (weekend alcohol)
  - Family: parental education, job, cohabitation status

---

## 🏗️ Project Structure

```
AI_PROJECT_TRACK_C/
├── AI_PROJECT_TRACK_C.ipynb          # Main notebook (all phases)
├── student-mat.csv                   # Dataset
├── README.md                         # This file
├── AL2002_Lab_Manual.pdf            # Lab guidelines & requirements
└── outputs/                         # Generated visualizations & results
```

---

## 📑 Project Phases

### **Phase 1: Python & Data Foundation** 🐍

#### Objectives
- Load and explore the student performance dataset
- Implement Python fundamentals with real data
- Build graph representations from tabular data

#### Key Tasks
1. **Data Loading & Inspection**
   - Load CSV with proper parsing (`;` delimiter)
   - Analyze shape, data types, and missing values
   - Display first 10 rows

2. **Data Exploration**
   - Create grade categories: A, B, C, F
   - Count class distribution
   - Generate dataset statistics

3. **Object-Oriented Programming**
   - Define `DataRecord` class with features and labels
   - Create instances from dataset rows
   - Display record details

4. **Graph Construction**
   - **Nodes:** Study time levels (1-4), grade categories (A-F)
   - **Edges:** Co-occurrence relationships in student records
   - Build adjacency dictionary representation
   - Calculate graph metrics (nodes, edges)

#### Technologies
- pandas, numpy
- Python dictionaries & lists
- OOP principles

---

### **Phase 2: Intelligent Agent & Search Algorithms** 🤖

#### Objectives
- Implement intelligent agents using the student data graph
- Develop uninformed & informed search algorithms
- Evaluate algorithmic performance

#### Key Components

**1. Agent Design**
```python
class AIAgent:
    - perceive(state): Get possible next states
    - act(action): Move to new state
    - goal_test(state): Check if goal reached
    - get_cost(state1, state2): Calculate transition cost
```

**2. Search Algorithms Implemented**
- **Breadth-First Search (BFS)**
  - Explores all neighbors at current depth
  - Optimal for unweighted graphs
  
- **Depth-First Search (DFS)**
  - Explores deeply before backtracking
  - Memory efficient
  
- **Uniform Cost Search (UCS)**
  - Finds lowest-cost path
  - Uses priority queue
  
- **Greedy Best-First Search**
  - Heuristic-guided exploration
  - Fast but not always optimal
  
- **A* Search**
  - Combines cost & heuristic
  - Optimal and complete

**3. Search Parameters**
- **Initial State:** `study_2` (2-5 hours of study)
- **Goal State:** `grade_A` (Highest grade category)
- **Cost Function:** Uniform (1 per edge)
- **Graph:** Multi-feature connections (study time → failures → grades)

#### Performance Metrics
- Nodes explored
- Path length
- Search efficiency
- Cost comparison

#### Technologies
- Graph algorithms
- Queue & Stack (collections.deque, heapq)
- Heuristic functions
- Complexity analysis

---

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8+
pandas
numpy
matplotlib
jupyter
```

### Installation
```bash
# Clone/download the project
cd AI_PROJECT_TRACK_C

# Install dependencies
pip install pandas numpy matplotlib jupyter

# Launch notebook
jupyter notebook AI_PROJECT_TRACK_C.ipynb
```

### Running the Project

1. **Load Data**
   ```python
   import pandas as pd
   df = pd.read_csv('student-mat.csv', sep=';')
   ```

2. **Explore Dataset**
   - Run Phase 1 cells to load and analyze data
   - Review data shape, types, and distributions

3. **Execute Algorithms**
   - Run Phase 2 cells to initialize agent
   - Execute search algorithms in sequence
   - Compare results

4. **Visualize Results**
   - Plot grade distributions
   - Show search paths
   - Compare algorithm efficiency

---

## 📊 Key Findings & Analysis

### Data Insights
- **Class Distribution:** Varied across A, B, C, F grades
- **Key Predictor:** Previous grades (G1, G2) strongly correlate with final grade
- **Study Time:** Positive correlation with academic performance
- **Failures:** Strong negative indicator of final grade

### Algorithm Performance
| Algorithm | Nodes Explored | Path Length | Optimal |
|-----------|---|---|---|
| BFS | 🔵 Medium | ✓ | ✓ |
| DFS | 🔵 Medium | ❌ | ❌ |
| UCS | 🟢 Low | ✓ | ✓ |
| Greedy | 🟢 Very Low | ❌ | ❌ |
| A* | 🟢 Low | ✓ | ✓ |

---

## 📈 Visualizations Included

- **Grade Distribution Histograms**
- **Study Time vs. Final Grade Scatter Plots**
- **Failures vs. Performance Analysis**
- **Feature Correlation Heatmaps**
- **Search Algorithm Comparison Charts**
- **Graph Network Visualizations**

---

## 🔍 Code Examples

### Creating the Agent
```python
from collections import defaultdict

# Build search graph
graph = build_search_graph(df)
agent = AIAgent(graph, goal_state='grade_A')

# Perceive neighbors
neighbors = agent.perceive('study_2')

# Test goal
is_goal = agent.goal_test('grade_A')
```

### Running BFS Search
```python
path, nodes_explored = bfs(
    graph=search_graph,
    start='study_2',
    goal='grade_A'
)
print(f"Path: {' → '.join(path)}")
print(f"Nodes Explored: {nodes_explored}")
```

---

## 📚 References & Resources

- **Dataset:** [UCI ML Repository - Student Performance](https://archive.ics.uci.edu/ml/datasets/student+performance)
- **Lab Manual:** AL2002_Lab_Manual.pdf
- **Course Materials:** [Your Course Portal]

### Algorithms & Theory
- Russell & Norvig: "Artificial Intelligence: A Modern Approach"
- Search Algorithm Fundamentals
- Graph Theory & Data Structures

---

## ✅ Deliverables Checklist

- ✓ Phase 1: Data Foundation (Python fundamentals, OOP, graphs)
- ✓ Phase 2: Intelligent Agents & Search (BFS, DFS, UCS, Greedy, A*)
- ✓ Comprehensive Analysis & Comparisons
- ✓ Visualizations & Charts
- ✓ Code Documentation
- ✓ README & Project Structure

---

## 📝 Notes & Remarks

- All algorithms use **uniform cost (1 per edge)** for path traversal
- Heuristic functions calculated based on graph structure
- Dataset preprocessed to handle categorical variables
- Results saved in outputs folder for reference
- Code includes comments for clarity and reproducibility

---

## 🔧 Troubleshooting

### Issue: Dataset not found
**Solution:** Ensure `student-mat.csv` is in the project root directory

### Issue: Jupyter kernel not starting
**Solution:** Install jupyter: `pip install jupyter`

### Issue: Import errors
**Solution:** Install dependencies: `pip install pandas numpy matplotlib`

---

## 📞 Support & Questions

For questions or issues:
1. Review the AL2002 Lab Manual
2. Check code comments in the notebook
3. Consult team members
4. Reach out to course instructors

---

## 📜 License & Usage

This project is part of the AL2002 Artificial Intelligence Lab course. Use for educational purposes only.

**Created:** 2024-2025 Academic Year  
**Status:** ✅ Complete  

---

<div align="center">

**Made with ❤️ by Track C Team**

![AI](https://img.shields.io/badge/AI-🤖-blue)
![Data](https://img.shields.io/badge/Data-📊-green)
![Learning](https://img.shields.io/badge/Learning-🎓-orange)

</div>
