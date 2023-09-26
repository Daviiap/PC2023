# LOCK TWO

## Implementação

```c
int victim;

lock() {
    int myID = getID();
    
    victim = myID;

    while(victim == myID);
}

unlock() {}
```
