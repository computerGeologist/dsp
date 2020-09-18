[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> REPLACE THIS TEXT WITH YOUR RESPONSE

import scipy.stats

#First, calculate the normal distribution for adult men's heights. 
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

#Then, what is 5'10" and 6'1" in cm?
low = 2.54 * (5*12+10)
high = 2.54 * (6*12+1)
#Then, using that, subtract "everyone below 5'10" from "everyone below 6'1"
dist.cdf(high)-dist.cdf(low)
