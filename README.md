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

The bar chart illustrates how often each infant behavior—SLEEPING, HAPPY, and CRYING—occurs in the dataset. Among the three states, SLEEPING is the most frequent, appearing approximately 37 times, followed by HAPPY with around 24 occurrences, and CRYING as the least frequent with about 9 instances.

---

### Transition Probability Heatmap

![image](https://github.com/user-attachments/assets/79258593-48a9-495d-bc70-77b58309837d)

The heatmap shows the transition probabilities between three states—sleeping, crying, and happy—based on observed behavior patterns. From the "sleeping" state, there’s a high likelihood of transitioning to either "crying" (0.67) or "happy" (0.71), suggesting sleep often ends in emotional responses. The "crying" state is relatively unstable, with low probabilities of remaining in or transitioning to "happy", and a higher chance (0.19) of shifting back to "sleeping". From the "happy" state, the most common next state is "sleeping" (0.43), followed by a moderate chance of staying happy (0.25). Overall, this suggests a cyclic pattern where sleep frequently leads to emotional states, and crying tends to resolve back into sleep.
  
---

### Transition Graph

![image](https://github.com/user-attachments/assets/a89e96a4-e783-4ac1-a4c2-c73488ef0304)

The Markov Chain Transition Graph visually represents the possible state transitions and their probabilities between "SLEEPING", "CRYING", and "HAPPY" using directed arrows. Each arrow points from a current state to a possible next state, with its thickness and label indicating the transition probability (e.g., 0.38 from HAPPY to SLEEPING). The color scheme—magenta nodes and red edges—helps highlight state transitions, and the arc-style arrows make directionality clearer. From the graph, we observe that transitions like SLEEPING to HAPPY or CRYING have relatively high probabilities, whereas transitions from CRYING to HAPPY are much less likely. This confirms that "CRYING" is a more transient state, while "SLEEPING" and "HAPPY" have stronger cyclical links.

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
