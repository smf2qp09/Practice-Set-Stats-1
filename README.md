# Practice-Set-Stats-1
#Felton Practice Set #2 Sampling Statistics and The Central Limit Theorem
#Due Feb. 18, 2021
#This was my general code - I edited x, N, and l to answer questions 1 and 2

import numpy as np
from numpy.random import seed
from numpy.random import randint
from numpy import mean
from numpy import std
import scipy.stats as stats
from scipy.stats import norm
import matplotlib.pyplot as plt

#Part 1 - Poisson Distribution

#seed the random number generator so experiment is replicable
#generate random samples
#sample data from a different distribution
#p for poisson distribution
#running poisson distribution with lamba = 'x' and size = 'y' which is number of samples 
#find the distrubition of means
seed(N)
x=20 #number of samples pulled in each trial
N=100 #number of times sampling is repeated (trials essentially)
l=10 #lambda

#how many times samples are repeated to create distribution 
p_means = [mean(np.random.poisson(lam=l, size=x)) for _i in range(N)]

#Part 2 - take z-score of distribution of means
y = stats.zscore(p_means)
plt.hist(y, alpha=0.5)

#Part 3 - KS-test to check normality
stats.kstest(y, 'norm')
