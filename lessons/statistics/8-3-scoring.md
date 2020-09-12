[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

```{python}
def SimulateGame(lam):
    """Simulates a game and returns the estimated goal-scoring rate.

    lam: actual goal scoring rate in goals per game
    """
    goals = 0
    t = 0
    while True:
        time_between_goals = random.expovariate(lam)
        t += time_between_goals
        if t > 1:
            break
        goals += 1

    # estimated goal-scoring rate is the actual number of goals scored
    L = goals
    return L
```

```{python}
def simulate_season(lam, n=100000):
    score = []

    for _ in range(n):
        score.append(SimulateGame(lam))

    errors = [estimate - lam for estimate in score]
    mean_error = np.mean(errors)

    e2 = [(estimate - lam) ** 2 for estimate in score]
    rmse = np.mean(e2) ** 0.5

    return [mean_error, rmse]]
```

```{python}
simulate_season(3)
```

[-0.00336, 1.7282708121124999]]

There seems to be a heavy sampling bias.

---