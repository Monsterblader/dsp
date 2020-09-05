[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```{python}
rand = np.random.random(1000)

pmf = thinkstats2.Pmf(rand)
thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='number', ylabel='count')

cdf = thinkstats2.Cdf(rand)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='number', ylabel='count')
```

The distribution seems pretty uniform to me.