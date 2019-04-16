# Os-Simulation-Assignments
Os assignments based on Sheduling and Page Table

Question 2: Consider a scheduler which schedules the job by considering the arrival time of the processes where arrival time if given as 0 is discarded or displayed as error. The scheduler implements the shortest job first scheduling policy, but checks the queue of the processes after the every process terminates and time taken for checking and arranging the process according to the shortest job is 2 time unit. Compute the waiting time, turnaround time and average waiting time and turnaround time of the processes. Also compute the total time taken by the processor to compute all the jobs. 
The inputs for the number of requirements, arrival time and burst time should be provided by the user.
Develop a scheduler which submits the processes to the processor in the defined scenario, and compute the scheduler performance by providing the waiting time for process, turnaround time for process and average waiting time and turnaround time.
Code:



DESCRIPTION
Shortest Job First Sheduling

Shortest job first (SJF) or shortest job next, is a scheduling policy that selects the waiting process with the smallest execution time to execute next. SJN is a non-preemptive algorithm. Shortest Job first has the advantage of having minimum average waiting time among all scheduling algorithms.
•	Shortest Job first has the advantage of having minimum average waiting time among all scheduling algorithms.
•	It is a Greedy Algorithm.
•	It may cause starvation if shorter processes keep coming. This problem can be solved using the concept of aging.
•	It is practically infeasible as Operating System may not know burst time and therefore may not sort them. While it is not possible to predict execution time, several methods can be used to estimate the execution time for a job, such as a weighted average of previous execution times. SJF can be used in specialized environments where accurate estimates of running time are available.


Algorithm:
Shortest Job First Scheduling Algorithm(non- preemptive): SJF is based on prediction of burst time. SJF schedules a process with smallest burst time. In simple words, this algorithms executes process with their increasing order of CPU burst time. If all processes are having same CPU burst time then this works as FCFS algorithm. SJF minimizes average waiting time, however it’s hard to predict CPU burst time in advance.
Example: Consider the following table:
Process no.	Arrival Time	Burst Time
P1	0	6
P2	2	1
P3	4	4
P4	5	3
Find the average waiting time and average turn arround time using SJF(non-preemptive) algorithm?
Solution:  Using SJF(non-preemptive) algorithm, gantt chart is:
 
 
Therefore,
 
Waiting Time	Turn around Time	Completion Time	Process No.	Arrival Time	Burst Time
6 - 6 = 0	6 - 0 = 6	6	P1	0	6
5 - 1 = 4	7 - 2 = 5	7	P2	2	1
9 - 4 = 5	14 - 5 = 9	14	P3	5	4
4 - 3 = 1	10 - 6 = 4	10	P4	6	3
 
So,
Average Turn arround time  = (6 + 5 + 9 + 4) / (4) = 6
Average Waiting time = (0 + 4 + 5 + 1) / (4) = 2.5




Code Snippet:

1.First we declare all the necessary variables regarding the problems such as waiting time,turnaround time,completion time etc.

 

2.As Given in the problem if user give 0 as a arrival time of any process then it must show an error.So the code of this constraint is as follows:-


3. Now we have to sort the table according to arrival time.
 
4.Arranging the table according to Burst,Execution,and Arrival Time.

 

5. Now at last we have to make a table of Process,Arrival Time,Burst Time,Compeltion Time,TurnAroundTime and store the value in Table.

 
6.Now Enter the Burst and Arrival time of all Process and number of process.

  
7.At Last it will Calculate Everything what is ask in Problem.

 

Complexity: As we see in sorting according to arrival time I use Nested for loop so the complexity will be:
O(n^2)



QUESTION 29

Question 29: Write a C program to create a page table for a program of 5MB. Consider page size as 2KB.
Assign frame numbers randomly in page table. (for conceptual clarity refer the textbook).


DESCRIPTION
Page Table:

Page table has page table entries where each page table entry stores a frame number and optional status (like protection) bits. Many of status bits used in the virtual memory system. The most important thing in PTE is frame Number.
Page table entry has the following information –
 
1.Frame Number – It gives the frame number in which the current page you are looking for is present. The number of bits required depends on the number of frames.

1.	Number of bits for frame = Size of physical memory/frame size
2.Present/Absent bit – Present or absent bit says whether a particular page you are looking for is present or absent. In case if it is not present, that is called Page Fault. It is set to 0 if the corresponding page is not in memory. Used to control page fault by the operating system to support virtual memory. Sometimes this bit is also known as valid/invalid bits.

3.Protection bit – Protection bit says that what kind of protection you want on that page. So, these bit for the protection of the page frame (read, write etc).

4.Referenced bit – Referenced bit will say whether this page has been referred in the last clock cycle or not. It is set to 1 by hardware when the page is accessed.

5.Caching enabled/disabled – Some times we need the fresh data. Let us say the user is typing some information from the keyboard and your program should run according to the input given by the user. In that case, the information will come into the main memory. Therefore main memory contains the latest information which is typed by the user. Now if you try to put that page in the cache, that cache will show the old information. So whenever freshness is required, we don’t want to go for caching or many levels of the memory.The information present in the closest level to the CPU and the information present in the closest level to the user might be different. So we want the information has to be consistency, which means whatever information user has given, CPU should be able to see it as first as possible. That is the reason we want to disable caching. So, this bit enables or disable caching of the page.

6.Modified bit – Modified bit says whether the page has been modified or not. Modified means sometimes you might try to write something on to the page. If a page is modified, then whenever you should replace that page with some other page, then the modified information should be kept on the hard disk or it has to be written back or it has to be saved back. It is set to 1 by hardware on write-access to page which is used to avoid writing when swapped out. Sometimes this modified bit is also called as the Dirty bit.






Code Snippet:

1.First we declare all the necessary variables regarding the problems such as frame no.,page no, etc.
 
2.Calculate Page Fault.
 
3.Now give input to No of pages,Page no. and No. of Frames.
 
4.Now Program Calculate Page Fault.
 




Complexity: O(n)
