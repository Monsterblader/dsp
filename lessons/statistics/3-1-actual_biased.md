[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```{python}
resp = nsfg.ReadFemResp()
nmkid = thinkstats2.Pmf(resp.numkdhh, label='Number of kids')
thinkplot.PrePlot(2)
thinkplot.SubPlot(2)
thinkplot.Pmfs([nmkid])
nmkid.Mean()

1.024205155043831

def biased(pmf, lab):
    new_nmk = pmf.Copy(label=lab)

    for x, p in pmf.Items():
        new_nmk.Mult(x, x)

    new_nmk.Normalize()

    return new_nmk

biased_nmk = biased(nmkid, 'Biased kid count')
thinkplot.PrePlot(2)
thinkplot.SubPlot(2)
thinkplot.Pmfs([biased_nmk])

biased_nmk.Mean()

2.403679100664282
```