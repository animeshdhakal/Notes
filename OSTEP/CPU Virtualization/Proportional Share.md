Proportional Share Scheduling Algorithm instead of minimizing turnaround time and response time tries to provide each job fair share/percentage of the CPU.

## Lottery Scheduling
In lottery scheduling, each job is provided with specific number of tickets. At each time slice, the scheduler hosts a lottery picking a random number from 0 to total number of tickets. The process holding that number will be ran. This approach is **probabilistic** which is its greatest strength. It doesn't guarantee exact proportions over short periods but will converge to the correct proportions over the long run.

## Stride Scheduling
Each process has a stride which is inversely proportional to its number of tickets. 
$$Stride = \frac{Large Number}{Number of Tickets}$$
Each process has **pass value** which is a counter. Lets say A, B, C are jobs with 100, 200, 40 stride values. During the first arrival, any of the job is ran. Lets say A in this case. The **pass value** will be incremented by the **stride value**. And at next time slice, the process with a lower **pass value** will be ran. This approach is **deterministic**

## Completely Fair Scheduler (CFS)

### Virtual Runtime (vruntime)
Each process has a **vruntime**. **vruntime** is a measure of the total execution time of a process. The process with the least **vruntime** will be ran first.

### Balancing Fairness
The major advantage of CFS is its ability to use custom time slice for each process. 
$$Time Slice = \frac{sched_latency}{no of processes}$$
 The minimum value of time slice is set through the **min_granularity**.

### Weighting
Each process has a **nice** value which ranges from -20 to +19 which is mapped to a weight. A process with lower nice value(higer weight) gets a larger share of the cpu. Its **vruntime** accumulates more slowly, causing the scheduler to pick it more often.

### Efficient Implementation
Instead of a simple list (which is slow to search), CFS stores runnable processes in a **red-black tree**, ordered by **vruntime**. This allows the scheduler to find the next process to run very quickly (in O(log n) time), which is critical for systems with thousands of processes.

### Dealing with Sleeping Processes
A process that sleeps for a long time will have a very low **vruntime** when it wakes up, potentially allowing it to monopolize the CPU. To solve this, When a process wakes up, CFS sets its **vruntime** to the minimum **vruntime** currently in the red-black tree. This prevents starvation of other jobs but means I/O-heavy jobs might not get their full share of the CPU.