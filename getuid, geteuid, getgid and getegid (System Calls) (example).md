# getuid, geteuid, getgid and getegid (System Calls) (example)
## C, Operating Systems, Processes 
### URL: https://www.jesusninoc.com/2014/12/27/getuid-geteuid-getgid-and-getegid-system-calls-example/
```C
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>
int main(void)
{
printf(“Get a real user ID:%\n”, getuid());
printf(“Get the effective user ID:%\n”, geteuid());
printf(“Get the real group ID:%\n”, getgid());
printf(“Get the effective group ID:%\n”, getegid());
}

```
