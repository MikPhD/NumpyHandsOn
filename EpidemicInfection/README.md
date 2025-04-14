# 🧪 Epidemic Spread Simulation Using Pure NumPy

## Overview

This project simulates the spread of an infectious disease over a 2D grid, using **only NumPy** for the underlying logic and computation. The goal is to demonstrate numerical modeling techniques without relying on external libraries like Pandas or SciPy. 

The model is intentionally built from scratch to illustrate competences in computational mechanics and array manipulation.

---

## Problem Statement

Simulate how an infectious disease spreads in a fixed-size 2D population grid over discrete time steps. Each individual occupies a cell on the grid and can be in one of the following states:

- **S**: Susceptible (healthy, not yet infected)
- **I**: Infected (can spread the disease)
- **R**: Recovered/Removed (no longer contagious)

At each time step:

- Infected individuals may infect their **immediate neighbors** (N, S, E, W) with a certain **infection probability**.
- After a fixed number of steps (`infection_duration`), infected individuals transition to the **R** state.
- The simulation runs until there are no infected individuals left.

The simulation should visualize the grid over time and include analytical metrics such as infection curves.

---

## Objectives

- Build a discrete-time epidemic model with NumPy, operating fully on 2D arrays.
- Avoid Python `for` loops where possible. Use **broadcasting**, `np.where`, `np.roll`, and array slicing instead.
- Track the evolution of each state (S, I, R) over time.
- Provide performance comparison between loop-based and vectorized implementations.
- Visualize the epidemic with heatmaps and infection curves (matplotlib allowed).
- Optional: Create interactive controls (e.g., via sliders in Jupyter).

---

## Key Features to Implement

1. **Population Grid Initialization**
   - Set grid size (e.g., 100x100)
   - Randomly infect a small percentage of individuals (e.g., 1%)

2. **State Management**
   - Represent the grid with a NumPy array (`int8` or `uint8`), where:
     - 0 = Susceptible
     - 1 = Infected
     - 2 = Recovered

3. **Infection Logic**
   - Use `np.roll` to check neighbors efficiently
   - Apply probabilistic infection (using `np.random.rand()` and `np.where`)

4. **Recovery Logic**
   - Track time since infection with a second matrix (`infection_time`)
   - Transition to Recovered after `infection_duration` steps

5. **Data Collection**
   - Track total number of S, I, R individuals at each time step
   - Store history in NumPy arrays or Python lists

6. **Visualization**
   - Plot infection heatmap (`matplotlib.imshow`)
   - Line plot showing number of infected over time

7. **Optional Enhancements**
   - Add mobility (random walk of individuals)
   - Add death state (S, I, R, D)
   - Create variants (SIR, SEIR models)
   - Allow different infection durations per individual (distribution)

---

