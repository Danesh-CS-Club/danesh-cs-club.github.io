---
layout: post
title: Search Algorithms Explained – BFS, DFS & A* (Danesh CS Club Lecture)
date: 2026-02-19 18:00:00 +0330
categories: [lectures, algorithms, search, ai]
tags: [bfs, dfs, a-star, graph-search, artificial-intelligence]
author: Ryan Samaeian
toc: true
---

## Search Algorithms Explained – BFS, DFS & A*

Hey everyone, today we’re talking about search algorithms. We’re going to cover three of the most important ones that are used everywhere: **BFS**, **DFS**, and **A*** (A-Star).

These three algorithms basically run the world right now — from finding the shortest path in games, to web crawlers, to Google Maps, to solving Sudoku. They look simple, but almost everything in AI and computer science is built on top of them.

Before we jump into the algorithms, we need to understand a few basic concepts that everything is based on.

### Important Concepts

- **Node**: Any point or piece of data (A, B, C, D… or a city, a web page, a Sudoku cell, etc.)
- **Initial State**: Where we start (the starting node)
- **Goal State**: Where we want to reach (the target node)
- **Action**: The move we can make from one node to another (the arrows between nodes)
- **Frontier**: The list of nodes we still need to explore
- **Transform State**: When we actually move from one node to another using an action

We also need two very important data structures:

- **Queue (FIFO)** → First In, First Out (like a normal line of people)
- **Stack (LIFO)** → Last In, First Out (like a stack of plates — you take the last one you put)

---

### 1. BFS – Breadth-First Search (برجسته‌ترین جستجو)

BFS uses a **Queue**.

It explores level by level — first all the closest nodes, then the next level, and so on.

**How it works:**
1. Start at initial state
2. Put all its neighbors into the queue
3. Take the first one from the queue (FIFO)
4. Check if it’s the goal
5. If not, add its neighbors to the end of the queue
6. Repeat

**Good for:**
- Finding the shortest path (in terms of number of steps)
- Web crawlers
- Finding the closest solution

**Bad for:**
- Uses a lot of memory when the graph is very wide

---

### 2. DFS – Depth-First Search (جستجوی عمقی)

DFS uses a **Stack**.

It goes as deep as possible down one path before going back.

**How it works:**
1. Start at initial state
2. Pick one neighbor and go deep
3. When you can’t go deeper, go back (backtrack) and try the next path
4. Repeat until you find the goal or explore everything

**Good for:**
- Uses very little memory
- Solving Sudoku, maze problems, Git branch history
- When the solution is deep

**Bad for:**
- Can get stuck in very deep wrong paths
- Does not guarantee the shortest path

---

### 3. A* (A-Star) – The Smart One

A* is an **informed search** algorithm. It’s like BFS but smarter — it uses a **cost** (how expensive each move is) + **heuristic** (estimate of how far we are from the goal).

This is what Google Maps, game AI (finding path around obstacles), and many real-world pathfinding systems use.

**Why it’s powerful:**
- Usually finds the best path
- Much faster than plain BFS in big graphs
- Still guarantees the shortest path if the heuristic is good

---

### Comparison Table

| Algorithm | Uses      | Memory Usage | Finds Shortest Path? | Best For                     |
|-----------|-----------|--------------|----------------------|------------------------------|
| BFS       | Queue     | High         | Yes                  | Shortest path, web crawling  |
| DFS       | Stack     | Low          | No                   | Sudoku, deep solutions       |
| A*        | Cost + Heuristic | Medium   | Yes (if heuristic good) | Maps, games, robotics      |

---

### Watch the Lecture

{% include embed/youtube.html id='https://www.youtube.com/watch?v=SzeBgYFHznQ' %}

https://www.youtube.com/watch?v=SzeBgYFHznQ

---

### Final Words

These three algorithms are the foundation of almost all search problems in computer science. Once you understand nodes, frontier, queue vs stack, and how BFS/DFS work, A* becomes much easier to understand.

Practice them! Try implementing BFS and DFS on a simple graph or maze — you’ll see how they behave differently.

Next lecture we’ll go deeper into A* with real examples and code.

Questions? Drop them in the comments or Discord.

See you in the next one!  
— Ryan, Danesh Computer Science Club
