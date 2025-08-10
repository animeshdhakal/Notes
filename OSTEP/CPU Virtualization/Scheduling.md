## Scheduling Metrics
Some metrics are needed to measure the performance of different policies.

- Turnaround Time = T Completion - T Arrival
- Response Time = T First Run - T Arrival

Trying to tweak one causes other to be worsen.

## First In First Out (FIFO)
This is a very basic scheduling algorithm. The jobs are run **non-preemptive** way. This scheduling algorithm has a major flow known as the **Convoy Effect**. When longer jobs arrives before the shorter job, the shorter job have to wait till the longer job has run completely. This algorithm is very bad for **turnaround time**.

## Shortest Job First (SJF)
For this algorithm to work we need to know about the job length which is a non-ideal approach. We don't know the length of the job arriving. This algorithm tries to run the shortest job first. This algorithm is very good for average **turnaround time**. But still suffers from the **Convoy Effect**.

## Shortest To Completion First (STCF)
This algorithm is a **preemptive approach**. If a longer job is currently running on the CPU, but if a new short job arrives. The algorithm switches to the shorter job and runs it completely. This algorithm is also very good for average **turnaround time**. 

## Round Robin (RR)
A preemptive algorithm that runs each job for a fixed **time slice** (or quantum) and then switches to the next job in the ready queue. This is very good for average **response time** but very bad for average **turnaround time**. This also has a cost of **context switching**.
