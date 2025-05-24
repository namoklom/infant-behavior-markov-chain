# Modelling Infant Behavior Transition using Markov Chain Simulation

## 👤 Author

| Name            | Role              | LinkedIn                                      |
|-----------------|-------------------|-----------------------------------------------|
| Jason Emmanuel  | Data Scientist | [linkedin.com/in/jasoneml](https://www.linkedin.com/in/jasoneml/) |

This repository contains a Python-based exploratory data analysis (EDA) of baby behavior patterns. The dataset used is a synthetic sequence of behavior states such as `SLEEPING`, `CRYING`, and `HAPPY`. The purpose of this project is to examine the frequency and transitions of behaviors to understand how babies shift from one state to another over time.

By modeling the behavior transitions with a Markov Chain, we can estimate the likelihood of moving from one emotional state to another. This type of analysis can be useful in behavioral science, healthcare, and early childhood development research.

---

## 📘 Project Description

The notebook walks through the following main steps:

1. **Data Preparation**: We define an `original_sequence` list containing a time series of baby behaviors.
2. **Frequency Analysis**: Using pandas and seaborn, we count and visualize how often each behavior appears.
3. **Transition Modeling**: A transition matrix is calculated to represent the probabilities of moving from one state to another.
4. **Visualization**: Data is visualized through bar plots, heatmaps, and optional graph structures to interpret frequency and transition patterns more clearly.

---

## 🧰 Tools and Libraries Used

| Library        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `pandas`       | Used for data manipulation and creating transition matrices.                |
| `matplotlib`   | Used for basic plotting functionality.                                      |
| `seaborn`      | Used for statistical visualizations like bar plots and heatmaps.            |
| `networkx`     | Used to create and visualize the behavior transition graph (if included).   |
| `numpy`        | Used for numerical calculations, particularly when working with matrices.   |
| `random`       | Used to simulate or shuffle behavior sequences (if needed).                 |
| `collections`  | Utilized for efficient counting of behavior transitions.                    |

---

## 📊 Visualizations

### Frequency of Each Behavior

![image](https://github.com/user-attachments/assets/28f07ba4-06dc-4203-9570-310373703ece)

This bar plot provides a visual summary of how often each behavior appears in the sequence. It uses `seaborn.barplot` to create an aesthetically pleasing chart that highlights the dominance of certain states.

**Interpretation**:
- The behavior `SLEEPING` occurs most frequently, indicating a calm or resting state as the default.
- `HAPPY` is the second most frequent state, showing positive engagement.
- `CRYING` is less frequent, potentially indicating rare discomfort or needs.

---

### Transition Probability Heatmap

![image](https://github.com/user-attachments/assets/79258593-48a9-495d-bc70-77b58309837d)

A heatmap generated using `seaborn.heatmap` visualizes the transition probabilities between different behavior states. Each cell `[i, j]` represents the probability of transitioning from state `i` to state `j`.

**Interpretation**:
- Brighter shades represent higher probabilities.
- Diagonal cells often represent the likelihood of remaining in the same state.
- Patterns such as frequent transitions from `SLEEPING` to `HAPPY` might suggest environmental or developmental responses.
  
---

### Transition Graph

![image](https://github.com/user-attachments/assets/a89e96a4-e783-4ac1-a4c2-c73488ef0304)

A directed graph is built using `networkx` to visually depict behavior state transitions. Nodes represent the states, while edges represent the transition direction and are weighted by transition probability.

**Interpretation**:
- Arrows show possible movements between states.
- Edge thickness or labels indicate transition strength.

---

### Steady-State Distribution of Baby Behavior

![image](https://github.com/user-attachments/assets/2c3a9808-a081-44b4-9496-aa5cac750566)

This plot illustrates the **steady-state probabilities** derived from the Markov Chain model, which shows the long-run behavior distribution of the baby assuming an infinite number of transitions.

In this specific analysis, the steady-state probabilities are as follows:

| Behavior State | Probability |
|----------------|-------------|
| SLEEPING       | 0.333       |
| CRYING         | 0.333       |
| HAPPY          | 0.333       |

The steady-state distribution represents the probability that the baby will be in a certain behavior state **after a large number of transitions**, regardless of the initial state. This is useful for identifying the long-term tendencies of behavioral patterns.

**Interpretation**:
- The equal probabilities indicate that the Markov process is **ergodic and symmetric**.
- Over time, the baby is equally likely to be **sleeping**, **crying**, or **happy**.
- This kind of result might arise in simulated or simplified datasets where transition dynamics are balanced or intentionally uniform.

---
