# BAKERY

## Implementação

```c
bool escolhendo[n] = { ...false };
int tickets[n] = { ...0 };

lock() {
    int myID = getID();

    escolhendo[myID] = true;
    int max = 0;
    for(int i = 0; i < n; i++) {
        if(tickets[i] > max) {
            max = tickets[i];
        }
    }
    tickets[myID] = max + 1;
    escolhendo[myID] = false;

    for(int i = 0; i < n; i++) {
        while(escolhendo[i]);
        while(
            (tickets[i] != 0 && tickets[i] < tickets[myID]) || 
            (tickets[i] == tickets[myID] && i < myID)
        );
    }
}

unlock() {
    int myID = getID();
    tickets[myID] = 0;
}
```
