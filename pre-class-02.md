# pre-class


Make sure you commit this often with meaningfull messages. 

### Background

The exponential distribution is defined by its cumulative distribution function
\(F(x) = 1-e^{-\lambda x}\)

The R function ***rexp()*** generates random variables with an exponential distribution. For example 
<center><strong>rexp(n=10, rate=5)</strong> </center>

results in 10 exponentially distributed numbers with a rate \(\lambda=5\). If you leave out the 5 and just have
<center><strong>rexp(n=10) </strong></center>
then this results in 10 exponentially distributed numbers with a rate \(\lambda=1\), this is also referred to as the "standard exponential distribution". 

### Part 1


1. Generate 200 random values from the standard exponential distribution and store them in a vector `exp.draws.1`.  Find the mean and standard deviation of `exp.draws.1`.

'exp.draws.1' <- (rexp(n=200))
mean(exp.draws.1)
sd(exp.draws.1)


2. Repeat, but change the rate to 0.2, 5, 7.3 and 10, storing the results in vectors called  `exp.draws.0.2`,  `exp.draws.5`,  `exp.draws.7.3` and  `exp.draws.10`. 
'exp.draws.0.2' <- rexp(n=200,rate=0.2)
'exp.draws.5' <- rexp(n=200, rate=5)
"exp.draws.7.3" <-rexp(n=200, rate=7.3)
'exp.draws10' <-rexp(n=200, rate=10)


3. The function `plot()` is the generic function in R for the visual display of data. `hist()` is a function that takes in and bins data as a side effect. To use this function, we must first specify what we'd like to plot.
    a. Use the `hist()` function to produce a histogram of your standard exponential distribution. hist(exp.draws.1)
    
    b. Use `plot()` with this vector to display the random values from your standard distribution in order.
plot(exp.draws.1)
    
    c. Now, use `plot()` with two arguments -- any two of your other stored random value vectors -- to create a scatterplot of the two vectors against each other.
    
plot(exp.draws.1,exp.draws.5)

4. We'd now like to compare the properties of each of our vectors. Begin by creating a vector of the means of each of our five distributions in the order we created them and saving this to a variable name of your choice. Using this and other similar vectors, create the following scatterplots and explain in words what is going on:
    a. The five means versus the five rates used to generate the distribution.
    
x <- c(mean(exp.draws.0.2),mean(exp.draws.1),mean(exp.draws.5), mean(exp.draws.7.3), mean(exp.draws10))
'rates'<- c(.2, 1, 5, 7.3, 10)
plot(x,rates)

#There is a neagative correlation beween the means and the rates of the exponential distributions. 

    b. The standard deviations versus the rates.
    
 "stands" <- c( sd(exp.draws.0.2), sd(exp.draws.1), sd(exp.draws.5), sd(exp.draws.7.3), sd(exp.draws10))
plot(stands,rates)

#There is a neagative correlation beween standard deviations and the rates of the exponential distributions. 

    c. The means versus the standard deviations.
plot(x, stands)

#There is a positive correlation beween the means and the standard deviations of the exponential distributions

For each plot, explain in words what's going on.

### Part II (PHP 2560 Only)


5. R's capacity for data and computation is large to what was available 10 years ago. 
    a. To show this, generate 1.1 million numbers from the standard exponential distribution and store them in a vector called `big.exp.draws.1`. Calculate the mean and standard deviation.
    b. Plot a histogram of `big.exp.draws.1`.  Does it match the function \(1-e^{-x}\)?  Should it? 
    c. Find the mean of all of the entries in `big.exp.draws.1` which are strictly greater than 1. You may need to first create a new vector to identify which elements satisfy this.
    d. Create a matrix, `big.exp.draws.1.mat`, containing the the values in 
`big.exp.draws.1`, with 1100 rows and 1000 columns. Use this matrix as the input to the `hist()` function and save the result to a variable of your choice. What happens to your data?
    e. Calculate the mean of the 371st column of `big.exp.draws.1.mat`.
    f. Now, find the means of all 1000 columns of `big.exp.draws.1.mat` simultaneously. Plot the histogram of column means.  Explain why its shape does not match the histogram in problem 5b).
   
