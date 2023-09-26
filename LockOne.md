# LOCK ONE

## Implementação

```c
bool flags[2] = {false, false}

lock() {
    int myID = getID();
    flags[myID] = true;
    while(flags[1-myID]);
}

unlock() {
    int myID = getID();
    flags[myID] = false;
}
```
