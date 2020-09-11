[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

```{python}
def L_distribution(lam):
    mu = 1 / lam
    L_array = []
    means = []
    medians = []

    for i in range(1000):
        sample = [np.random.exponential(1 / lam) for i in range(10)]
        L_array.append(1 / (statistics.mean(sample)))
        means.append(statistics.mean(sample))
        medians.append(statistics.median(sample))
    
    e2 = [(estimate - mu) ** 2 for estimate in means]
    std_err = statistics.mean(e2) ** 0.5

    e2_90 = sorted(means)[1:8]
    conf_int = statistics.mean(e2_90) ** 0.5

    return [L_array, std_err, conf_int]

def run_L_distribution(lam):
    results = L_distribution(lam)

    plot.plot(results[0])
    print(results[1])
    print(results[2]))
```

```{python}
run_L_distribution(2)
```

0.1572334703142834

0.4195282438087024

```{python}
run_L_distribution(20)
```

0.016117441420777475

0.13665327489625276

```{python}
run_L_distribution(200)
```

0.001647270338734515

0.04390796512563289
