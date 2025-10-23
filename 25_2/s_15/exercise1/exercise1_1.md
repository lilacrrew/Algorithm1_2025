Exercise 1.1 — Divide & Conquer on a Vector Containing a Single `1`
Problem Description

We are given a vector of length `n` that contains **exactly one `1`**, while all other elements are equal to `0`, for example:
v = [0, 0, 0, 0, 1, 0, 0, 0]
The tasks are:
The goal is to implement three recursive functions:

| Function | Description |
|----------|------------|
| `divide2(v, L, R)` | Recursively divide into **2 equal parts** until size `1` |
| `divide3(v, L, R)` | Recursively divide into **3 equal parts** |
| `dividefind2(v, L, R)` | Divide into 2 parts and **return the index of the single `1`** |


