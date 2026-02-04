# Round Robin Tournament Scheduler in C

## 📌 Project Overview
This project implements a **Round Robin Tournament Scheduling System** in **C**, designed to automatically generate a complete match schedule for multiple teams and venues under real-world constraints.

The program ensures:
- Every team plays every other team exactly once
- No team plays on consecutive days
- No repeated matches
- Fair distribution of matches
- Automatic venue assignment
- Sequential date progression

The scheduling logic is built using **matrix-based modeling**, **combinatorial mathematics**, and **constraint-aware random selection**.

---

## ⚙️ Core Concepts Used
- Dynamic Memory Allocation (`calloc`)
- 2D Matrix Modeling
- Graph-like traversal of remaining matches
- Constraint-based random selection
- Combinatorics (nC2 for match count)
- Date arithmetic
- Modular program design in C

---

## 🧠 How the Algorithm Works

### 1. Match Matrix Initialization
- Each team is assigned a row
- First column stores number of matches left
- Remaining columns store opponent teams yet to be played

### 2. Team Selection Logic
- **Team A selection** avoids:
  - Teams from the previous day
  - Teams with no valid future opponents
- **Team B selection** ensures:
  - Not played before
  - Not from previous day
  - Still has matches remaining

### 3. Matrix Editing After Each Match
- Played teams are removed from each other’s match lists
- Remaining match count is updated
- Teams with zero matches are shifted out

### 4. Edge Case Handling
- When normal selection fails near tournament end:
  - Remaining matches are extracted
  - Reinserted safely into the match history without conflict

### 5. Schedule Printing
- User inputs start date
- Matches are assigned one per day
- Venues are randomly selected
- Output includes:
  - Match number
  - Teams
  - Date
  - Time
  - Venue

---

## 📂 File Structure
