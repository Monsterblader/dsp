[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```{python}
diff = l14.parity.mean() - others.parity.mean()
var1 = l14.parity.var()
var2 = others.parity.var()
n1 = len(l14.parity)
n2 = len(others.parity)
diff / np.sqrt((n1 * var1 + n2 * var2) / (n1 + n2))

-1.5146909326015194
```