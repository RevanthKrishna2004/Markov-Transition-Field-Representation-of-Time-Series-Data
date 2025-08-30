# Markov Transition Field (MTF) Representation of Time Series Data

This project demonstrates how to transform a univariate time series into a **Markov Transition Field (MTF)**.  
The MTF is a 2D representation of time series dynamics that captures transition probabilities between discretized states and makes them suitable for visualization and image-based machine learning.

---

## Objectives

- Convert continuous time series data into discrete states using binning.  
- Construct transition matrices to model state changes over time.  
- Encode these transitions into a **Markov Transition Field (MTF)**.  
- Visualize the MTF as a heatmap and explore downsampling methods.  
- Analyze self-transition probabilities to better understand temporal patterns.  

---

## Steps

### 1. Load and Visualize the Data
- The dataset used is the **ETTh1 electricity dataset** from the ETT benchmark.  
- The time series column `HUFL` (High Use Frequency Load) was selected.  
- The first **1000 points** were taken for analysis.  
- A line plot was used to visualize the raw time series.  

---

### 2. Discretize the Time Series
To apply a Markov model, the continuous values of the time series were **discretized into bins**:
- **Quantile binning** was chosen to ensure equal distribution of samples across bins.  
- Each data point was assigned a discrete label (e.g., 0–9 for 10 bins).  

This step converts continuous dynamics into symbolic sequences suitable for transition analysis.  

---

### 3. Construct the Transition Matrices
- An **adjacency matrix** was created to count transitions between discretized states.  
- The adjacency matrix was normalized to form a **Markov Transition Matrix (MTM)**, representing probabilities of moving from one state to another.  

This captures the short-term dynamics of the time series.  

---

### 4. Build the Markov Transition Field (MTF)
The MTF encodes transition probabilities into a **2D matrix** aligned with the time dimension:
- Each entry *(i, j)* in the MTF represents the probability of transitioning between the states at time *i* and time *j*.  
- The result is a structured image-like representation of temporal dependencies.  

---

### 5. Visualize the MTF
- The MTF was visualized as a heatmap.  
- High-intensity regions indicate strong transition probabilities between states.  
- A **downsampled version** was also generated using block averaging, reducing resolution for easier interpretation and computational efficiency.  

---

### 6. Analyze Self-Transitions
- The diagonal of the reduced MTF contains **self-transition probabilities**.  
- These were plotted back onto the discretized time series, with color mapping indicating the likelihood of remaining in the same state over time.  

---

## Results
- The MTF provides a **2D image representation** of the original time series.  
- Downsampling creates a compact representation that still preserves temporal structure.  
- Self-transition analysis highlights which parts of the time series exhibit **stability versus variability**.  

---
