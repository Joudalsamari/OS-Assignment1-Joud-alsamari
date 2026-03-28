# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**
This assignment taught me that multithreading is an essential idea for creating effective, high-performance software that can manage several activities at once. I gained a deep understanding of the thread lifecycle, including how a thread moves between states like New, Runnable, Running, and Terminated. Additionally, I discovered that because threads share memory inside a single program, they are far more resource-efficient than processes. I became aware of how context switching enables a single CPU to appear to be handling multiple tasks at once after seeing the simulation's visual progress bars. Most significantly, I now know how scheduling techniques such as Round-Robin guarantee an equitable distribution of CPU time across all active threads.
[Write your answer here. Discuss specific concepts like thread creation, thread states, how threads execute concurrently, what surprised you, etc.]

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**
Accurately integrating Feature 3: Waiting Time Tracking into the current scheduler logic was the biggest obstacle I had to overcome. Finding the precise location in the code to update the total waiting time for every process in the queue while another process was operating proved to be challenging. I had to make sure that, without double counting or omitting any processes, the time quantum spent by the "Running" process was added to each other thread in the Ready Queue. Managing the logic for the "last process" was also challenging because, if it is the last work left, there shouldn't be any more waiting time. I had to properly use the processQueue iterator and carefully examine the loop structure in order to do this.
[Describe the specific challenge. Was it understanding the code? Implementing a feature? Using Git? Explain what made it difficult and how it relates to the course concepts.]

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**
By using a highly methodical and modular debugging strategy, I was able to overcome these technological difficulties. In order to monitor the waitingTime variable's values during the scheduler's execution, I began by inserting temporary System.out.println commands. This made it possible for me to spot any logical mistakes in the computation and to observe precisely when the values were being changed. In order to better grasp how to synchronize the main thread with the execution of process threads, I also took the time to go over the Java documentation for the Thread class and the join() method. Additionally, before integrating the more complicated Feature 3, I was able to confirm that Features 1 and 2 were operating flawlessly by segmenting the code into smaller, testable sections.
[Describe your problem-solving approach. Did you read documentation? Ask for help? Debug systematically? What resources did you use? What strategies worked?]

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**
I can leverage these multithreading ideas to create cutting-edge applications that need a very responsive user experience. In a mobile application, for example, I can utilize background threads to retrieve data from an external API while the main UI thread keeps handling animations and user interactions without freezing. This information is also useful in backend development, where a server must effectively manage several concurrent connections. I can develop better code for real-time systems, such multiplayer games or video streaming services, where timing and concurrency are crucial, if I understand how threads are scheduled. All things considered, these ideas are essential to developing expert software that satisfies customer demands for dependability and quickness.
[Give specific examples from real applications you use (web browsers, games, mobile apps, etc.). Explain why threads are useful in those scenarios. Connect to what you learned in this assignment.]

---

## Additional Reflections (Optional)

### What would you like to learn more about?
In order to avoid data races when many threads access the same variable, I would like to learn more about thread safety and how to use locks or semaphores.
[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?
Although I still need more practice with complicated synchronization and memory management, I currently feel very at ease with thread lifecycles and basic scheduling.
[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment
Because it transformed abstract OS ideas into a useful coding project that was enjoyable to implement and debug, this assignment was really beneficial.
[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
