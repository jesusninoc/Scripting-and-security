# Uso de las funciones ftok(), shmget(), shmat() y shmctl()
## C, Processes 
### URL: https://www.jesusninoc.com/2014/11/22/uso-de-las-funciones-ftok-shmget-shmat-y-shmctl/
```PowerShell
key_t ftok(const char *pathname, int proj_id)

```
```PowerShell
int shmget (key_t key, int size, int shmflg)

```
```PowerShell
void *shmat (int shmid, char * shmaddr, int shmflg)

```
```PowerShell
int shmctl (int shmid, int cmd, struct shmid_ds *buf)

```
```PowerShell
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/shm.h>

```
