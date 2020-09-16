[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

resp = nsfg.ReadFemResp()
kids = resp.numkdhh

actual_distribution=thinkstats2.Pmf(kids, label = "Children in household")
thinkplot.Hist(actual_distribution)

print("Mean by household: ", actual_distribution.Mean())

biased_distribution = actual_distribution.Copy(label="Children in household")
for x, p in biased_distribution.Items():
    biased_distribution.Mult(x, x)
biased_distribution.Normalize()
thinkplot.Hist(biased_distribution)

print("Mean, according to children: ", biased_distribution.Mean())
