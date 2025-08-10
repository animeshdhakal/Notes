The Multi Level Feedback Queue tries to minimize **turnaround time** for CPU intensive jobs and **response time** for interactive jobs. It tries to incorporate the behavior of the job over time. This is where the feedback part comes. MLFQ contains different priority queues. On the basis of the behavior of the job, scheduler puts the job to a certain queue based on the observation.

## Rules for MLFQ
1. Rule 1: If Priority(A) > Priority(B) then, A runs.
2. Rule 2: If Priority(A) = Priority(B) then, A and B are run in Round Robin.
3. Rule 3: When a job enters the system, it is placed at the highest priority.
4. Rule 4: Once a job uses all of its **allotment**, it is reduced to lower priority.
5. Rule 5: After a certain period, all of the jobs are reset to the top priority.

If there was no **priority boost**, then the jobs with lower priority would not be able to use the CPU at all because the CPU will be used by shortest job at the highest priority.  This is called as **Starvation**.

A program could trick the scheduler by issuing a trivial I/O request just before its time slice ends to retain its high priority. So to avoid this, we have to see the overall CPU usage.

**Time Allotment** is the CPU time given to each job. If a job uses all of its allotment, then it is reduce to a lower priority.