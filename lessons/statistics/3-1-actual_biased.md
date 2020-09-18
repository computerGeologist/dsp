[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)


```
resp = nsfg.ReadFemResp()
kids = resp.numkdhh

actual_distribution=thinkstats2.Pmf(kids, label = "Children in household")
thinkplot.Hist(actual_distribution) #Graph 1: For each household, chart the number of children inside it. 

print("Mean by household: ", actual_distribution.Mean())

#Then, bias the distribution. For each household, we would recieve a number of responses equal to the number of children there. Therefore, we want to square the probability of response for that household.
biased_distribution = actual_distribution.Copy(label="Children in household")
for x, p in biased_distribution.Items():
    biased_distribution.Mult(x, x)
biased_distribution.Normalize()
thinkplot.Hist(biased_distribution)

print("Mean, according to children: ", biased_distribution.Mean())
```
