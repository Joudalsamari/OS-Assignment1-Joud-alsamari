# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
While a thread is a lightweight execution unit that operates inside a process and shares the same memory environment, a process is a completely independent program execution unit with its own private memory space and system resources. Because threads have far less overhead than individual processes in terms of creation time and context-switching, we used them in this assignment. For a CPU scheduler simulation, using threads is far more appropriate since it enables several jobs to effectively share data while the primary scheduler controls their order of execution. This method accurately simulates how contemporary operating systems manage several processes running simultaneously within a single program.
[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
A process is an entirely independent program execution unit with its own private memory space and system resources, whereas a thread is a lightweight execution unit that works inside a process and shares the same memory environment. We utilized threads in this assignment because they have significantly lower overhead than individual processes in terms of creation time and context-switching. Using threads is much more suitable for a CPU scheduler simulation since it allows multiple jobs to efficiently communicate data while the primary scheduler manages their execution order. This technique faithfully mimics how modern operating systems handle several processes functioning concurrently within a single program.
[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```▶ P1 executing quantum [4000ms]
  ⏸ P1 completed quantum 4000ms │ Overall progress: [███████████████░░░] 87%
     Remaining time: 567ms
  ↻ P1 yields CPU for context switch
  ➕ P1 (Pri:3 ) added to ready queue │ Burst time: 4567ms
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]
In this specific snippet, P1 started with a burst time of 4567ms while the time quantum was set to 4000ms. After P1 executed for the full 4000ms, it still had 567ms of work remaining, so it yielded the CPU and triggered a context switch. The program then added P1 back to the end of the Ready Queue (as shown by the "added to ready queue" message) so it could finish the rest of its work in a future round.
---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**
[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?]
New: When the Process object is initially constructed and the Thread object is initialized using new Thread(process) but has not yet been started, P1 enters the New state.

2. **Runnable**: [When does P1 become Runnable?]
Runnable: P1 becomes Runnable as soon as it is added to the processQueue, where it remains prepared and waits to be pulled for execution by the scheduler's main loop.

3. **Running**: [When is P1 Running?]
Running: When the scheduler invokes currentThread.start(), the JVM starts carrying out the particular logic specified inside the run() method, and P1 enters the Running state.

4. **Waiting**: [When/why would P1 be Waiting?]
Waiting: When Thread starts the simulation, P1 goes into a Timed Waiting state.Sleep() either "waits" back in the queue following a context switch or is used to simulate processing time.

5. **Terminated**: [When is P1 Terminated?]
Terminated: When P1's remainingTime reaches zero and the run() method finishes running, it enters the Terminated state, which permits its permanent removal from the scheduling cycle.
---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]
Web servers with many users

**Description**: 
[Describe the real-world scenario or application]
A server that manages hundreds of incoming requests at once, such a university portal used for course registration.

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]
By guaranteeing that each user request receives a tiny portion of CPU time, it offers exceptional responsiveness. This keeps everyone connected to a fair and engaging experience by preventing a single big data request from blocking all other users.
### Example 2: [Name of application/scenario]
Background Tasks for Modern Operating Systems

**Description**: 
[Describe the real-world scenario or application]
Managing background services in Windows or macOS, like a music player that plays while the user works on a document or a cloud backup service.

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]
When the OS switches between these background threads so quickly that the user never detects a latency, it offers "interactive fairness." Without starving or interfering with the user's main foreground program, the algorithm makes sure that low-priority background processes continue to advance.
---

## Summary

**Key concepts I understood through these questions:**
1. The Fundamental Distinctions Between Threads and Processes: I now know how threads accomplish lightweight concurrency by sharing memory and resources within a single process.
2. Round-Robin Scheduling Logic: I discovered how the Ready Queue and the time quantum cooperate to guarantee CPU fairness and avoid process hunger.
3. The Thread Lifecycle and State Transitions: I can now follow a process from the New state to the Runnable and Running states, and then to the Terminated state.

**Concepts I need to study more:**
1. Thread Synchronization and Locks: I'd like to know how to stop data corruption when several threads attempt to change the same variable simultaneously.
2. Advanced Scheduling Algorithms: I'm interested in how "Shortest Job First" and "Multilevel Feedback Queues" stack up against the Round-Robin technique we used.
