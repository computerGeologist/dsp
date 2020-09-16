[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d

def ComputeDifferencesInWeights(live, firsts, others):
    """Computes and displays statistics related to weight and pregnancy length between first and later babies.
    
    live:Dataframe
    firsts:Dataframe
    others:Dataframe
    
    """
    
    print('Mean weight(lbs)')
    print('Live: ' + live.totalwgt_lb.mean())
    print('Firsts: ' + others.totalwgt_lb.mean())
    print('Others: ' + firsts.totalwgt_lb.mean())
    
    print('Mean pregnancy length (weeks)')
    print('Live: ' + live.prglngth.mean())
    print('Firsts: ' + firsts.prglngth.mean())
    print('Others: ' + others.prglngth.mean())
    
    print('Cohen\'s effect size for weight: ' + CohenEffectSize(firsts, others).totalwgy_lb.mean())
    print('Cohen\'s effect size for pregnancy length: '  + CohenEffectSize(firsts, others).prglngth.mean())
    
    
#While first babies tend to have slightly (0.03 std deviations) longer pregnancies, they also tend to be slightly (0.09 standard deviations) lighter.
#This is unexpected, given that shorter pregnancies would normally indicate lighter babies. 
