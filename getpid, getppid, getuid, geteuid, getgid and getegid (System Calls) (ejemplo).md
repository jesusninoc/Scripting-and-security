# getpid, getppid, getuid, geteuid, getgid and getegid (System Calls) (ejemplo)
## C, Operating Systems, Processes 
### URL: https://www.jesusninoc.com/2014/12/30/getpid-getppid-getuid-geteuid-getgid-and-getegid-system-calls-ejemplo/
```C
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
int main(void)
{
int pid, ppid, uid, gid, euid, egid;
pid=getpid();
ppid=getppid();
uid=getuid();
gid=getgid();
euid=geteuid();
egid=getegid();
printf(“Identificador real del proceso actual:%d\n”,pid);
printf(“Identificador del proceso padre:%d\n”, ppid);
printf(“Identificador del usuario:%d\n”, uid);
printf(“Identificador del grupo: %\n”, gid);
printf(“Identificador efectivo del proceso actual:%\n”, euid);
printf(“Identificador efectivo del grupo del proceso actual:%d\n”, egid);
}

```
