# PETERSON

## Implementação

```c
bool flags[2] = {false, false};
int victim;

lock() {
    int myID = getID();
    flags[myID] = true;
    victim = myID;

    while(flags[1-myID] && victim == myID);
}

unlock() {
    int myID = getID();
    flags[myID] = false;
}
```
