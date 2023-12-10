# Simulation_OS_Assignment03

### FIFO: (FIFO_Algorithm.c)
First-In, First-Out (FIFO) algorithm
A FIFO replacement algorithm keeps track of each page the time when that page was brought into memory. 
When a page must be replaced, the oldest page is chosen first.
We can create a FIFO queue to hold all pages in memory.

Program Explanation:
Here we keep a track of all the pages in the form of list
We use while loop to go to the end of the list and when we reach the end we replace it with the new page.

![Example Image](FIFO_Alg_output_screenshot.jpeg) <br>

### LRU: (LRU_Algorithm.c)
Least Recently used algorithm
When a page must be replaced, LRU chooses the page that has not been used for the longest
period of time
We can think of this strategy as the optimal page-replacement algorithm looking backward in
time
Program Explanation:
Here we keep a track of all the pages previously used
When there is a need for page replacement, the page that is least used in recent will get replaced
by the new page
In this program FITLRULONE tracks the recent use of that particular page.

![Example Image](LRU_Alg_output_screenshot.jpeg) <br>

### MFU: (MFU_Algorithm.c)
Most Frequently Used algorithm
When a page must be replaced, MFU chooses the page that has been used more in the past.
We do this by assuming that as it has already been accessed so many times, there will be less
necessity of it in the future.
Program Explanation:
Here FITMCNTER keeps a track of the number of times the page is used.
We use a while loop to get the maximum used page (frequently used).
And we replace that page with the new page that has arrived.

![Example Image](MFU_Alg_output_screenshot.jpeg) <br>

### LFU: (LFU_Algorithm.c)
Least Frequently Used algorithm
When a page must be replaced, LFU chooses the page that has been used least in the past.
We do this by assuming that as it has already been accessed so many times, actively used page
should have a large reference count.
Program Explanation:
Here FITLFUCNTER keeps a track of the number of times the page is used.
We use a while loop to get the minimum used page (less frequently used).
And we replace that page with the new page that has arrived.

![Example Image](LFU_Alg_output_screenshot.jpeg) <br>

### Random pick: (Random_Algorithm.c)
Random pick Algorithm
When a page must be replaced, Random pick chooses a random page and replaces it with the
new page.
Program Explanation:
Here we use rand( ), which generates random numbers to replace the pages.
Using rand( ) we generate random number and check if the generated number is within the range
and then replace the page.

![Example Image](Random_Alg_output_screenshot.jpeg) <br>

### PAGE.h:
Here we declare all the variables and functions that we will be using.

### PAGE.c:
Here we define the already declared functions of the page.

### Simulation.c:
This is the main program where we simulate/call all other functions that implement page
replacement algorithm. And find the hit and miss ratio of each simulation.
Use the info in the log files and screenshots of the averages in the console to make an
argument about which one of the page replacement algorithms worked the best and which
one worked the worst:
According to log files and the averages in the console, Random pick algorithm worked the best,
then comes LRU compared to others and Most Frequently Used (MFU) algorithm was the worst.
The "best" algorithm depends on the specific characteristics of the workload. LRU is often
considered a good general-purpose algorithm, but it may not always outperform others. Some
systems use a combination of algorithms or dynamically switch between them based on the
current system state.

  
## Execution:
$gcc SIMULATION.c PAGE.c FIFO.c LFU.c MFU.c LRU.c R.c -o SIMULATION <br>
$./SIMULATION [FCFS/LRU/Random/MFU/LFU]
