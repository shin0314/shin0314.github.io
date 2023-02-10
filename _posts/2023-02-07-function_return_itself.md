---
title: Function return itself
date: 2023-02-07 
categories: [cs61a]
tags: [cs61a]
---
可视化工具: <https://pythontutor.com/visualize.html#mode=display>

```python
def count(n):
    """
    >>> f0 = count(1)
    >>> f1 = f0(5, 0)
    >>> f2 = f1(5, 5)
    >>> f3 = f2(10, 5)
    """
    def say(s0, s1):
        print(n, s0)
        return count(n + 1)
    return say
```

```python
def announce_lead_changes(last_leader=None):
    """Return a commentary function that announces lead changes.

    >>> f0 = announce_lead_changes()
    >>> f1 = f0(5, 0)
    Player 0 takes the lead by 5
    >>> f2 = f1(5, 12)
    Player 1 takes the lead by 7
    >>> f3 = f2(8, 12)
    >>> f4 = f3(8, 13)
    >>> f5 = f4(15, 13)
    Player 0 takes the lead by 2
    """
    def say(score0, score1):
        if score0 > score1:
            leader = 0
        elif score1 > score0:
            leader = 1
        else:
            leader = None
        if leader != None and leader != last_leader:
            print('Player', leader, 'takes the lead by', abs(score0 - score1))
        return announce_lead_changes(leader)
    return say
```