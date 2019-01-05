# Statistics

# Table of Contents

[1. Introduction](#section-a)  
[2. Why We Are Using Think Stats](#section-b)  
[3. Instructions for Cloning the Repo](#section-c)  
[4. Required Exercises](#section-d)  
[5. Optional Exercises](#section-e)  
[6. Recommended Reading](#section-f)  
[7. Resources](#section-g)

## <a name="section-a"></a>1.  Introduction

[<img src="img/think_stats.jpg" title="Think Stats"/>](http://greenteapress.com/thinkstats2/)

Use Allen Downey's [Think Stats (second edition)](http://greenteapress.com/thinkstats2/) book for getting up to speed with core ideas in statistics and how to approach them programmatically. This book is available online, or you can buy a paper copy if you would like.

Use this book as a reference when answering the 6 required statistics questions below.  The Think Stats book is approximately 200 pages in length.  **It is recommended that you read the entire book, particularly if you are less familiar with introductory statistical concepts.**

Complete the following exercises along with the questions in this file. Some can be solved using code provided with the book. The preface of Think Stats [explains](http://greenteapress.com/thinkstats2/html/thinkstats2001.html#toc2) how to use the code.  

Communicate the problem, how you solved it, and the solution, within each of the following [markdown](https://guides.github.com/features/mastering-markdown/) files. (You can include code blocks and images within markdown.)

## <a name="section-b"></a>2.  Why We Are Using Think Stats 

The stats exercises have been chosen to introduce/solidify some relevant statistical concepts related to data science.  The solutions for these exercises are available in the [ThinkStats repository on GitHub](https://github.com/AllenDowney/ThinkStats2).  You should focus on understanding the statistical concepts, python programming and interpreting the results.  If you are stuck, review the solutions and recode the python in a way that is more understandable to you. 

For example, in the first exercise, the author has already written a function to compute Cohen's D.  **You could import it, or you could write your own code to practice python and develop a deeper understanding of the concept.** 

Think Stats uses a higher degree of python complexity from the python tutorials and introductions to python concepts, and that is intentional to prepare you for the bootcamp.  

**One of the skills to learn here is to understand other people’s code.  And this author is quite experienced, so it’s good to learn how functions and imports work.**

---

## <a name="section-c"></a>3.  Instructions for Cloning the Repo 
Using the [code referenced in the book](https://github.com/AllenDowney/ThinkStats2), follow the step-by-step instructions below.  

**Step 1. Create a directory on your computer where you will do the prework.  Below is an example:**

```
(Mac):      /Users/yourname/ds/metis/metisgh/prework  
(Windows):  C:/ds/metis/metisgh/prework
```

**Step 2. cd into the prework directory.  Use GitHub to pull this repo to your computer.**

```
$ git clone https://github.com/AllenDowney/ThinkStats2.git
```

**Step 3.  Put your ipython notebook or python code files in this directory (that way, it can pull the needed dependencies):**

```
(Mac):     /Users/yourname/ds/metis/metisgh/prework/ThinkStats2/code  
(Windows):  C:/ds/metis/metisgh/prework/ThinkStats2/code
```

---


## <a name="section-d"></a>4.  Required Exercises

*Include your Python code, results and explanation (where applicable).*

### Q1. [Think Stats Chapter 2 Exercise 4](statistics/2-4-cohens_d.md) (effect size of Cohen's d)  
Cohen's D is an example of effect size.  Other examples of effect size are:  correlation between two variables, mean difference, regression coefficients and standardized test statistics such as: t, Z, F, etc. In this example, you will compute Cohen's D to quantify (or measure) the difference between two groups of data.   

You will see effect size again and again in results of algorithms that are run in data science.  For instance, in the bootcamp, when you run a regression analysis, you will recognize the t-statistic as an example of effect size.

### Q2. [Think Stats Chapter 3 Exercise 1](statistics/3-1-actual_biased.md) (actual vs. biased)
This problem presents a robust example of actual vs biased data.  As a data scientist, it will be important to examine not only the data that is available, but also the data that may be missing but highly relevant.  You will see how the absence of this relevant data will bias a dataset, its distribution, and ultimately, its statistical interpretation.

### Q3. [Think Stats Chapter 4 Exercise 2](statistics/4-2-random_dist.md) (random distribution)  
This questions asks you to examine the function that produces random numbers.  Is it really random?  A good way to test that is to examine the pmf and cdf of the list of random numbers and visualize the distribution.  If you're not sure what pmf is, read more about it in Chapter 3.  


**ANSWER TO QUESTION 3**

Here is the code I used to solve the problem:

Part 1:  Code to model the actual distribtion of the data set .  
 
# Calculate Actual Distribution    
actual_dist = thinkstats2.Hist(resp['numkdhh'], label='frequency') .  .  
thinkplot.Hist(actual_dist)   .  
thinkplot.Config(xlabel='Number of Children per Family', ylabel='Count') .  .  
   
actual_n = actual_dist.Total() .  .  
actual_dict = {}    .
for x in resp['numkdhh']:      
    actual_dict[x] = actual_dict.get(x, 0) + 1    .  
     
actual_mean = 0    . 
for key in actual_dict:  
    quick_calc = actual_dict[key] * key /actual_n   . 
    actual_mean += quick_calc   
       
  
# Calculate Biased Distribution

biased_dist = thinkstats2.Hist(resp['numkdhh'], label='Frequency') .  /n  
biased_dist[0] = 0   ./n  
thinkplot.Hist(biased_dist)   .  /n
thinkplot.Config(xlabel='Number of Children per Family (Biased Sample)', ylabel='Count')   . /n
  
biased_n = biased_dist.Total()  . /n 

biased_dict = {}    /n  
for x in resp['numkdhh']:    /n
    biased_dict[x] = biased_dict.get(x, 0) + 1   ./n 
biased_dict[0] = 0 .  /n

      
biased_mean = 0   /n  
for key in biased_dict:    /n
    quick_calc = biased_dict[key] * key / biased_n    . /n
    biased_mean += quick_calc   . /n
     
   
Part 2:  Output from code (NOTE: Unable to copy graphs from Jupyter Notebook to this page.  Will try again)
     

   
   
   
   


### Q4. [Think Stats Chapter 5 Exercise 1](statistics/5-1-blue_men.md) (normal distribution of blue men)
This is a classic example of hypothesis testing using the normal distribution.  The effect size used here is the Z-statistic. 



### Q5. Bayesian (Elvis Presley twin) 

Bayes' Theorem is an important tool in understanding what we really know, given evidence of other information we have, in a quantitative way.  It helps incorporate conditional probabilities into our conclusions.

Elvis Presley had a twin brother who died at birth.  What is the probability that Elvis was an identical twin? Assume we observe the following probabilities in the population: fraternal twin is 1/125 and identical twin is 1/300.  

>> **ANSWER TO QUESTION 5**

This is an example of conditional probability.  To answer the question, you need to focus on the relative probability of being part of a set of male identical twins to the probability of being **either** part of a set of male fraternal twins **or** part of a set of male identical twins. 

Let's start with the probability of being an identical twin (1/300).  This is not the probability we need, because a set of identical twins will be composed of **either** two boys **or** two girls.  We are only interested in the probability of two boys, which can be expressed as (1/300) * 0.50 or **(1/600)**.  This probability will be the numerator of the fraction we will solve.

The denominator will be the probability of being part of a set of identical **male** twins **plus** the probability of being a part of a set of **male** fraternal twins.  We have already calculated the first probability, so let's move on to finding the probability of being part of a set of male fraternal twins.

We know the probability of being part of a set of fraternal twins is (1/125).  There are four possible ways that fraternal twins can be ordered:  two boys (25%), two girls (25%), 1st twin boy / 2nd twin girl (25%) and 1st twin girl / 2nd twin boy (25%).  So the probability of having a set of fraternal boy twins is (1/125) * 0.25 or **(1/500)**.

Putting it all together, the numerator is the probability of two identical male twins (1/600) divided by the probability of two identical male twins (1/600) **PLUS** the probability of two male fraternal twins (1/500).

This expression is equal to:  **(1/600) / ( (1/600) + (1/500) )**.  We need to convert the denominator of all the fractions to the least common denominator, which is 3000.  That will enable us to complete the calculation.

Once we restate all the fractions in terms of their least common denominator, the expression looks like this:   
      **(5/3000) / ( 5/3000 + 6/3000 )**

The fraction reduces to ( 5/3000 / 11/3000), or **5/11**.  The probability that Elvis was an identical twin **GIVEN** that he had a twin brother is 5/11, or **45.4545%**.





---

### Q6. Bayesian &amp; Frequentist Comparison  
How do frequentist and Bayesian statistics compare?

>> **ANSWER TO QUESTION 6**

NOTE:  The response to this question is based in large part from material in "A Comparison Of Bayesian And Frequentist Statisticas As Applied In A Simple Repeated Measures Example" (Jan Perkins & Daniel Wang), as well as various articles in Wikipedia.


Bayesian methods model uncertainty by a prior probability distribution over the research hypothesis. This probability is termed the posterior distribution and is used to reach conclusions about the research question.  The prior probability distribution may be based on a variety of external evidence and expert opinions.  With continued data collection, it is possible to revise the analysis and determine a new (and hopefully more precise) posterior distribution that can be used to analyze the research hypothesis and the data set.  This updating of the prior distribution occurs as understanding of the problem of interest changes in light of the evidence gathered. 

Essentially, this process can be summarized as assigning an initial prior probability distribution, revising that prior probability distribution by integrating new information from different sources as evidence is collected, and then revising conclusions in light of new information.

Classical (or frequentist) statistics is what most people study in a high school or college statistics class.  Data is interpreted based using statistical models based on frequencies.  Probabilities of an event are a function of the number of times the event occurs in the set of available data.  No prior probability distributions are assumed -- in fact, this is actively discouraged because it is thought to introduce unnwanted subjectivity into the analysis.  

In frequentist statistics, researchers form a hypothesis based on the analysis of a sample data set from a larger population. This hypothesis is compared to an alternative, or null, hypothesis.  Hypothesis tests are used to determine what outcomes of a study would lead to the rejection of the null hypothesis based on a pre-specified level of significance, which is expressed by p-values and confidence intervals.         




---

## <a name="section-e"></a>5.  Optional Exercises

The following exercises are optional, but we highly encourage you to complete them if you have the time.

### Q7. [Think Stats Chapter 7 Exercise 1](statistics/7-1-weight_vs_age.md) (correlation of weight vs. age)
In this exercise, you will compute the effect size of correlation.  Correlation measures the relationship of two variables, and data science is about exploring relationships in data.    

### Q8. [Think Stats Chapter 8 Exercise 2](statistics/8-2-sampling_dist.md) (sampling distribution)
In the theoretical world, all data related to an experiment or a scientific problem would be available.  In the real world, some subset of that data is available.  This exercise asks you to take samples from an exponential distribution and examine how the standard error and confidence intervals vary with the sample size.

### Q9. [Think Stats Chapter 6 Exercise 1](statistics/6-1-household_income.md) (skewness of household income)
### Q10. [Think Stats Chapter 8 Exercise 3](statistics/8-3-scoring.md) (scoring)
### Q11. [Think Stats Chapter 9 Exercise 2](statistics/9-2-resampling.md) (resampling)

---

## <a name="section-f"></a>6.  Recommended Reading

Read Allen Downey's [Think Bayes](http://greenteapress.com/thinkbayes/) book.  It is available online for free, or you can buy a paper copy if you would like.

[<img src="img/think_bayes.png" title="Think Bayes"/>](http://greenteapress.com/thinkbayes/) 

---

## <a name="section-g"></a>7.  More Resources

Some people enjoy video content such as Khan Academy's [Probability and Statistics](https://www.khanacademy.org/math/probability) or the much longer and more in-depth Harvard [Statistics 110](https://www.youtube.com/playlist?list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo). You might also be interested in the book [Statistics Done Wrong](http://www.statisticsdonewrong.com/) or a very short [overview](http://schoolofdata.org/handbook/courses/the-math-you-need-to-start/) from School of Data.
