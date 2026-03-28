# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 -[March 27, 2026, 02:00 AM]
What I did was update my identity and set up the project environment.
Details
copied the OS-Assignment repository to Visual Studio Code after forking it.
I changed my name and Student ID to 445052056 in the SchedulerSimulation.java file.
To make sure it builds successfully, I ran the original code and checked the Java environment.

**Challenges**: At first, the javac command was not recognized by the terminal.

**Solution**:To make sure the JDK was linked, I changed the PATH variable and restarted Visual Studio Code.

**Time spent**: 1 hour.

---

### Entry 2 -[March 27, 2026, 3:00 AM]
**What I did**: 
Feature 1 (Process Priorities) is being implemented.
Details
The Process class now has a priority property.
changed the process creation loop so that random priority values ranging from 1 to 5 were assigned.
To show the priority in the Ready Queue output, the toString() and print functions were updated.

**Challenges**: 
aligning the terminal output's priority text without causing the progress bars to become distorted.
**Solution**: 
To provide a constant width for the priority display, formatted strings (String.format) were used.
**Time spent**: 1 hour.

---

### Entry 3 - [March 27, 2026, 4:00 AM]
**What I did**: 
Feature 2's implementation (Context Switch Counting).
Details:
added a contextSwitchCount variable to the Process class.
Every time a thread initiates a new quantum, logic was added to the main scheduler loop to increase this counter.
confirmed that the counter appropriately shows the number of times a process used the CPU.

**Challenges**: 
deciding if the initial execution qualifies as a "switch."
**Solution**: 
According to Round-Robin logic, a "switch" is defined as each time a process is removed from the queue.
**Time spent**: 1.5 hour.

---

### Entry 4 - [March 27, 2026, 5:30 PM]
**What I did**: 
Feature 3 (Waiting Time Tracking) is being implemented.
Details:
created a technique to update the overall waiting time for every process in the processQueue while another process is operating.
The end-of-simulation report now includes code that shows the final "Total Waiting Time" for every process.

**Challenges**: 
logic issue where waiting time was inadvertently assigned to the active process.
**Solution**: 
During the wait-time update loop, a condition to bypass the current thread was included.
**Time spent**: 30 minutes.

---

### Entry 5 -[March 28, 2026, 7:00 AM]
**What I did**: 
Refactoring code and customizing output.
Details:
To make the terminal output appear more professional, it was redesigned utilizing ANSI colors and improved spacing.
A issue that prevented the final statistics from printing when the simulation stopped suddenly has been fixed.
To make sure every feature functions flawlessly, several test runs were carried out.

**Challenges**: 
controlling thread synchronization to prevent overlapping or jumbled output.
**Solution**: 
To make sure the main thread waits for the process thread to complete its task before printing the subsequent update, use currentThread.join().
**Time spent**: 1 hour.

---

### Entry 6 - [March 28, 2026, 8:00 AM]
**What I did**: 
Final Record and Thoughts.
Details:
provided thorough explanations for every technical query in ANSWERS.md.
completed the REFLECTION.md file, making sure that every sentence count criteria was satisfied.
final examination of every project file before to submission.

**Challenges**: 
extending technical responses to satisfy the required minimum of five to seven sentences for reflections.
**Solution**: 
broader understanding of practical applications and particular debugging techniques applied in the lab.
**Time spent**: 1 hour

---

## Summary

**Total time spent on assignment**: [X hours]
6 hours.
**Most challenging part**: 
accurately determining the waiting time for every idle process in the queue at the same time without resulting in logic errors or performance lags.
**Most interesting learning**: 
Seeing how Thread and Thread.sleep() work.In a single-core setting, join() can be used to mimic a real-world CPU scheduler.
**What I would do differently next time**: 
To make data collection even more effective, I would begin by creating a better class structure for the "Stats Collector" earlier in the procedure.
