# Dining Philosopher Problem — Simulation in Python and C++

## Overview

This project provides a Python-based simulation of the Dining Philosopher Problem, one of the classic synchronization problems in Operating Systems.
It demonstrates how threads and synchronization mechanisms (locks/semaphores) can be used to prevent deadlocks and ensure proper resource sharing among concurrent processes.

The solution is implemented in a Jupyter Notebook (Dining Philosopher.ipynb) as well as in C++ and visualizes how philosophers alternate between thinking and eating without causing starvation.

This was part my course project of subject Operating System and Virtual Machines CSE5060.

## Problem Statement

The Dining Philosopher Problem was proposed by Edsger Dijkstra to illustrate synchronization issues in concurrent processes.

There are N philosophers sitting around a circular table.

Each philosopher alternates between thinking and eating.

A fork (chopstick) is placed between each pair of philosophers.

To eat, a philosopher must pick up both the left and right forks.

The challenge: avoid deadlocks and starvation while allowing every philosopher to eat eventually.

## Implementation Details

Language: Python

Concepts Used:

Threading (threading module)

Locks / Semaphores for synchronization

Random time delays to simulate thinking/eating behavior

Notebook: Dining Philosopher.ipynb

The solution ensures:

No deadlocks

No starvation

Fair scheduling between threads

## Algorithm

Initialize all forks as locked resources.

Create N philosopher threads.

Each philosopher:

Waits (thinks) for a random period.

Attempts to acquire both forks (in a specific order to avoid circular wait).

Eats for a random duration.

Releases both forks and returns to thinking.

Repeat the cycle multiple times.

## Synchronization Strategy

To prevent deadlock:

Each philosopher picks up the lower-numbered fork first, then the higher one.

Alternatively, one philosopher (e.g., the last one) picks up forks in reverse order — ensuring no circular wait.

This design avoids:

Mutual hold and wait

Circular dependency
