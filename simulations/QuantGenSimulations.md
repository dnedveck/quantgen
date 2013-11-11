Quant Gen simulations  
========================================================


Breeding value, ch 9 stuff
---------------------------------------

First let's create some data. For this I'm going to have one male crossed with one female, which then produce multiple offspring. For my case, it's going to be plant height, and the multiple offspring will be multiple seeds from the maternal plant.


```r
set.seed(666)
# 3 families, with 9 individuals each

exdf1 <- data.frame(family = c(rep("a", 9), rep("b", 9), rep("c", 9)), offspring = c(1:9, 
    1:9, 1:9))
# generating the trait values, with an SD of 0.5 units
trait_a <- rnorm(n = 9, mean = 4, sd = 0.5)
trait_b <- rnorm(n = 9, mean = 6, sd = 0.5)
trait_c <- rnorm(n = 9, mean = 8, sd = 0.5)

# appending trait values onto the data frame
exdf1$trait <- c(trait_a, trait_b, trait_c)
```


So I generated some data with random error, and the SD was 0.5. Let's see what the groups look like:


```r
plot(trait ~ family, data = exdf1)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 


It looks like the families are pretty well defined as having different mean trait values. Now lets calculate some stuff.

Let's find the within group variance, or $\sigma^2_W$ as we refer to it in Quant Gen:


```r
sigma_w_a <- var(exdf1$trait[which(exdf1$family == "a")])
sigma_w_a
```

```
## [1] 0.6195
```

```r
sigma_w_b <- var(exdf1$trait[which(exdf1$family == "b")])
sigma_w_b
```

```
## [1] 0.3838
```

```r
sigma_w_c <- var(exdf1$trait[which(exdf1$family == "c")])
sigma_w_c
```

```
## [1] 0.2127
```


And the between group variance, $\sigma_B^2$:

```r
sigma_B <- var(exdf1$trait)
sigma_B
```

```
## [1] 2.97
```


From this information we can calculate $t$, the intraclass coeffficient. Not sure what it does, but I can do it:
$$
t = \frac{\sigma^2_B}{\sigma^2_B + \sigma^2_W}
$$


```r
t_a <- sigma_B/(sigma_B + sigma_w_a)
t_a
```

```
## [1] 0.8274
```

```r
t_b <- sigma_B/(sigma_B + sigma_w_b)
t_b
```

```
## [1] 0.8855
```

```r
t_c <- sigma_B/(sigma_B + sigma_w_c)
t_c
```

```
## [1] 0.9332
```


--------------------------------------------------------

Well, to do some of the other fun stuff it looks like I'm going to have to simulate some data that's a bit more complex.

What kind of data do I need? Well, I can start off with giving both parents trait values, and then deciding what kind of trait mean the offspring should have. Since I eventually want to do some regression analysis, I'll need more than just three families (crosses)
, so... I'll use 30 crosses. Working with plant height, I'll choose to have a mean of 30, with a variance of 10 for each trait. Later I'll actually put a genetic component to determining trait value, but now I'll just stick with using `rnorm()`. 



```r
# going to make a vector of the parent traits for each one
pat <- rnorm(30, 30, 10)
mat <- rnorm(30, 30, 10)
```


I'll be crossing `pat_trait[1]` with `mat_trait[1]`, so I can just go ahead and calculate the midparent values:


```r
midparent <- (pat + mat)/2
```


How do I want the trait to be inherited? I'll pick the midparent value, and then add some environmental noise, with a SD of 3. Since these are plants, I'll have 10 offspring per mating pair


```r
famframe <- as.data.frame(matrix(nrow = 10, ncol = 30))
for (i in 1:length(midparent)) {
    famframe[, i] <- midparent[i] + rnorm(10, 0, 3)
}
```

Now `famframe` is a dataframe with each family corresponding to a column, and offspring as a row in each column. 


Let's get the variance of each family:

```r
famvar <- sapply(famframe, var)
```


What does the family data look like?

```r
boxplot(as.list(famframe))
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10.png) 


Looks cool, I guess. 

Now I want to calculate the covariance, and then do some plotting, so for that it seems I need a new dataframe structure :(

dataframe is going to have five columns: mat, pat, mid, family, offspring; corresponding to maternal trait, paternal trait, midparent trait, family number, and then offspring trait.


```r
# fuck it , I'll use a for loop
mat_hold <- NULL
for (i in 1:30) {
    temp <- rep(mat[i], 10)
    mat_hold <- c(mat_hold, temp)
}
pat_hold <- NULL
for (i in 1:30) {
    temp <- rep(pat[i], 10)
    pat_hold <- c(pat_hold, temp)
}
mid_hold <- NULL
for (i in 1:30) {
    temp <- rep(midparent[i], 10)
    mid_hold <- c(mid_hold, temp)
}
fam_hold <- NULL
for (i in 1:30) {
    temp <- rep(i, 10)
    fam_hold <- c(fam_hold, temp)
}

off_hold <- NULL
for (i in 1:30) {
    temp <- famframe[, i]
    off_hold <- c(off_hold, temp)
}

pframe <- data.frame(mat = mat_hold, pat = pat_hold, mid = mid_hold, family = fam_hold, 
    offspring = off_hold)
```



Now that tha's over, I can plot what I want:

```r
plot(offspring ~ mid, data = pframe)
```

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-12.png) 


Ok, so now I can find the covariance of one parent, with the offspring:

```r
covM <- cov(pframe$mat, pframe$offspring)
covP <- cov(pframe$pat, pframe$offspring)
```









--------------------------------------------


```r
phenotype.means <- c(5, 15, 20)  # phenotype means for genotypes 0, 1, and 2
phenotype.sd <- 5
X <- rbinom(1000, 2, 0.4)
Y <- rnorm(1000, phenotype.means[X], phenotype.sd)
```

rbinom syntax, first is the number of samples to do, the second number is the number of trails to run per sample, and the third ( the probability), is the probability of sucess.







