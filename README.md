# Operating Systems - Project 3: Concurrency

## Basic Infomation:

### Members:
- Bilal Drndo
- Dželila Tinjak

### Files:
```
    .
    ├── pseudocode       
    ├── [OS][Memory Concurrency Project] 5.pdf
    └── README.md
```

### Outline:
In this project, we have created a pseudocode for the given synchronization problem task.


### Sources/Tutorials that we have used:
- Pseudocde syntax taken from -> https://cseweb.ucsd.edu/classes/sp17/cse120-a/applications/ln/lecture7.html
- https://redirect.cs.umbc.edu/~jtang/archives/cs421.f19/lectures/L09ThreadSynchronizations.pdf
- https://rcvaram.medium.com/semaphore-world-76a2fe9c77a6

---

## Answer to the Task:
The pseudocode can be found in the `pseudocode` file.

- We have used the condition synchronization primitive in this project. 
- In the beginning we initialize all of the required parameters that we need i.e `N` integer -> number od max requests, `numberOfRequests` integer -> current number of requests, `isBusy` boolean -> to check if the server is busy, `mx` lock -> so we can acquire or release the lock and `cv` -> condition variable.
- After that we acquire the lock and check if the system is full, if it is full, we release the lock and exit a failure.
- If the system is not full, we increase the number of requests and check if the server is busy. If it is busy, we put that request on hold by calling the wait() function.
- After that, we assign that the server is busy,release the lock, receive the service, again acquire the lock, decrease the number of requests and set that ther server is not busy anymore.
- If the number of requests is greater that 0, we signal the condition variable.
- After that we release the mutex lock and exit with a success.


