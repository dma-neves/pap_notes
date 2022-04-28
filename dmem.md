# Distributed Memory

## Message Passing

$time = latency + message\_size / bandwidth$

$t = l + m/B$

**Fully connected network**

- Broadcast methods
    - One sends to all: $t = (n-1) * (l + m/B)$
    - Binomial tree: $t = log(n) * (l + m/B)$

    ![alt text](binomial.gif)

- All gather methods
    - recursive doubling: ... $t = ... log(n)$

## Unidirectional Ring

```python
def bcast_ring(m,k):
    my_id = my_num()
    n = num_procs()

    if my_id != k:
        recv(m, (my_id-1)%n)

    if my_id != (k-1)%n:
        send(m, (my_id+1)%n)
```

Can be improved with pipelining