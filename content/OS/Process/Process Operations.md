---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OS
Creation Date: 2023-08-09T22:50:00
Last Date: 2023-12-27T15:49:57+08:00
References: 
---
## Abstract
---
- [[Operation]] is described in [[C/C]]



## Process Creation
---
- A 2 steps process - [[#fork()]], [[exec()]]
- The two-step process gives the child the flexibility to manipulate its file descriptors(STDIN in the above example) after the fork but before the _execve_ in order to accomplish *redirection* of *standard input, standard output, and standard error*
- The code below creates a child [[Process (进程)]], [[Pipe (管道)]] the input of the child process, load and execute child process
```c
int pid = fork();
if (pid == 0)
{
	dup2(pipe_fds[numProcesses - 2][READ_STREAM], STDIN_FILENO);
	closePipes(numProcesses, pipe_fds);
	execvp(sub_process[0], (char *const *)sub_process);
}
```


## Process Termination 
---
### 2 Voluntary Ways
1. [[Process (进程)]] ends its job
2. [[Process (进程)]] hits an error during execution and exits gracefully

### 2 Involuntary Ways
1. Fatal error - which couldn't be handled by the [[Process (进程)]] itself (eg. [[Memory Failure]])
2. Termination by other process (killem all!)


## POSIX 
---
### fork()
- Creates an exact duplicate of the original [[Process (进程)]]
- When return value is `0`: we are inside the duplicate process
- Duplicated process' s [[Process IDentifier (PID)]] in parent process