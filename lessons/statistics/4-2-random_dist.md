[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```
numbers = np.random.random(1000)
numbers_pmf = thinkstats2.Pmf(numbers) 
#First, looking at the pmf of the samples. 
thinkplot.Pmf(numbers_pmf)
#Problem: It looks like a solid block of color, making it difficult to tell if there's any variation. 
numbers_cdf = thinkstats2.Cdf(numbers)
thinkplot.Cdf(numbers_cdf)
#The cdf looks close to a straight line, indicating that it's probably a uniform distribution. 
```
