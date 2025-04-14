# Wedding Seating Algorithm

## Overview
This project implements an optimized **wedding seating arrangement algorithm** using **Simulated Annealing**, ensuring that guests are seated in a way that minimizes conflicts and maximizes social compatibility. The algorithm evaluates relationships between guests and iteratively improves seating arrangements to achieve an optimal distribution across tables.

## Purpose
Seating arrangements at weddings can significantly impact guest experience. This algorithm aims to:
- Minimize conflicts by considering guests' relationships.
- Ensure guests who know each other or belong to the same party are strategically placed.
- Distribute guests efficiently across tables while adhering to size constraints.
- Use a probabilistic optimization approach (Simulated Annealing) to refine seating dynamically.

## Algorithm Summary
1. **Data Preparation:**
   - A list of guests is stored with attributes such as **party affiliation**, **relationship with the bride/groom**.
   - A **relationship matrix** is created, scoring how guests interact with each other.
   - This data can be gathered from wedding magnement platforms like "TheKnot".

2. **Graph Representation:**
   - The guest list is represented as a graph where nodes are guests and edges are relationships (weighted by a relationship score).
   - The graph is converted into an **adjacency matrix** for mathematical processing.

3. **Simulated Annealing Optimization:**
   - A random initial seating arrangement is generated.
   - Guests are moved between tables, and the **cost function** evaluates each move.
   - If a move reduces seating conflicts, it is accepted.
   - If a move increases conflicts, it may still be accepted with a probability influenced by a cooling temperature.
   - The algorithm gradually "cools" down, refining seating arrangements over iterations.

4. **Output & Visualization:**
   - The final optimized seating chart is displayed.
        Initial Seating Arrangement:
         Table 1: Jenny Adam, Alice Adam
         Table 2: Ava Zelda
         Table 3: Henry Zelda, Liam Prescott
         Table 4: Don Adam, Mason Zelda
         Table 5: Alex Adam, Amelia Harrington, Charlotte Winslow, William Kensington
         Initial Cost: -4.25
         Final Seating Arrangement:
         Table 1: 
         Table 2: Alex Adam, Jenny Adam, Don Adam, Alice Adam
         Table 3: Henry Zelda, Mason Zelda, Ava Zelda
         Table 4: 
         Table 5: Liam Prescott, Amelia Harrington, Charlotte Winslow, William Kensington
         Final Cost: -11.25
   - The algorithm tracks **cost changes**, **temperature decay**, and **acceptance probability** for analysis.
        ![image](https://github.com/user-attachments/assets/3da42ac3-4048-439a-a152-37d4ff88b4ad)
        ![image](https://github.com/user-attachments/assets/ead80b8f-7eca-4338-89cf-6ee72b6d0fd3)


## Constraints Considered
- **Each guest is assigned to exactly one table.**
- **Each table has a size limit.**
- **Relationship scores dictate seating preferences, reducing conflicts.**

## Technologies Used
- **Python** (NumPy, Pandas, NetworkX, Matplotlib)
- **Graph Theory** for relationship mapping.
- **Simulated Annealing** for optimization.

## How to Use
1. Prepare a guest list with attributes. This list can be extracted from "TheKnot", if you are using that application for redding planning. 
2. Run the algorithm to generate an initial random seating.
3. Observe the optimization process.
4. Retrieve and use the final seating arrangement.
