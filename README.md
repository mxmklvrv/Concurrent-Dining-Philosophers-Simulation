# Philosophers

A multithreading simulation of the classic Dining Philosophers problem written in C as part of the Hive Helsinki curriculum.

The goal of this project was to understand concurrent programming, thread synchronization, and the challenges of shared resource management in a low-level environment.

The simulation models philosophers sitting around a table who alternate between eating, sleeping, and thinking, while competing for shared forks.

---

## 📌 Project Goals

Through this project, I aimed to deepen my understanding of:

* Multithreading with `pthreads`
* Mutexes and synchronization mechanisms
* Race conditions and data consistency
* Deadlock prevention strategies
* Time management in concurrent systems
* Low-level C programming under strict constraints

---

## ⚙️ Features

* Simulation of multiple philosophers running concurrently
* Each philosopher is represented by an independent thread
* Forks implemented using mutexes to ensure safe access
* Configurable simulation parameters:

  * number of philosophers
  * time to die
  * time to eat
  * time to sleep
  * optional number of required meals
* Accurate timestamp-based logging system
* Death detection and simulation termination
* Optional completion condition when all philosophers have eaten enough

---

## 🛠 Technical Approach

The simulation is built around POSIX threads, where each philosopher runs in its own thread and competes for shared fork resources protected by mutexes.

To avoid race conditions, every fork is locked before use and unlocked immediately after eating. A global monitoring mechanism checks whether any philosopher has exceeded their time-to-die limit.

Deadlock prevention is handled through careful ordering and timing strategies, such as staggered starts and structured fork acquisition logic.

Time-sensitive actions like eating and sleeping are implemented using precise timing functions to ensure simulation accuracy.

The codebase is structured into logical components such as:

* thread management
* philosopher routines
* monitoring system
* utility/time functions

---

## 🚧 Challenges

Some of the most difficult parts of the project included:

* Preventing race conditions in a highly concurrent environment
* Avoiding deadlocks while maintaining performance
* Ensuring accurate timing for death detection
* Debugging inconsistent or rare concurrency bugs
* Designing a clean and maintainable thread lifecycle

This project required extensive testing and careful reasoning about thread interactions and shared resources.

---

## 📚 What I Learned

Through this project, I gained practical experience with:

* Multithreaded programming in C
* Mutex synchronization and thread safety
* Deadlock and starvation problems
* Timing-sensitive system design
* Debugging concurrency issues
* Structuring medium-scale C projects

It significantly improved my understanding of how operating systems manage concurrency and how subtle synchronization mistakes can lead to complex bugs.
