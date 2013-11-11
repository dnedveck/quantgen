10-15 Quant Gen
=======================================

Tying up some lose ends...

regression coefficient $b$= slope.
$$
b = \frac{Cov(X,Y)}{Var(X)}
$$
That's one way of standardizing the covariance

another way is
$$
r = \frac{cov(X,Y)}{\sqrt{Var(X)Var(Y)}}
$$
where $r$ is the correlation

Var(X) = parents, Var(Y) = offspring, and these relate to two estimates of the phenotypic variance, $V_P$

In general, the correlation is used more within generations

-------------------------------

We want to understand the genetic basis of differences in traits, this is the heritability. 

---------------


### Sib Analysis 

Set of random sires, mated to a number of dams, selected at random. From these matings we get $n$ offspring from each dam mated to a sire.

$S$ sires, $S_1$ up to $S_s$, where $s$ is the total number of sires. $d$ is the number of dams, and $n$ is the number of offspring from each dam

Now we go to ANOVA. Trait that we're interested in is $Z$

$$
Z_{ijk} = \mu + S_i + d_{ij} + w_{ikj}
$$
Where $S_i$ is the contribution of the sire, $d_{ij}$ is the dams contribution, and the difference of the individuals trait value with that of it's family, $w_{ijk}$

Each effect has their own distribution, assumed to be normal. The variance of the distribution, respresents the variance of the *blank* effects in the population, e.g. variance of the sire distribution is the variance of the sire effects in the population. Falconer refers to this as the observational or design components of variance (design because they are inherent in the design of how the data is collected - *I guess*). 

$$
V_P = V_A + V_D + V_{Eg}
$$
$$
V_P = \sigma^2_S + \sigma^2_d + \sigma^2_w
$$

ANOVA - This is a random effects model

Source | Degrees of Freedom | sums of Squares | Mean Squares
----------|----------|-----------|-----------
Sires | $S-1$ | $\sum_{i} (Z_{i}-\bar{Z})^2$ | $\frac{SS_s}{df_s}$
Dams | $S(d-1)$ | $\sum_{i}\sum_{j} (Z_{ij}-\bar{Z}_{i})^2$ | $\frac{SS_d}{df_d}$
Within | $Sd(n-1)$ | $\sum_{i}\sum_{j}\sum_{k} (Z_{ijk}-\bar{Z}_{ij})^2$ | $\frac{SS_w}{df_w}$

  
There's also the concept of the expected mean squares:

Source | Expected Mean Squares
---------|-------------
Sires | $\sigma_w^2 + n\sigma_d^2 + nd\sigma_S^2$
Dams | $\sigma_w^2 + n\sigma_d^2$
Within | $\sigma_w^2$


Mean squares of ANOVA is the observed variance, where the expected mean squares contain the true variances that contribute to the offspring.



$$
\sigma^2_S = \frac{MS_S - MS_d}{nd}
$$

$$
\sigma^2_d = \frac{MS_d - MS_w}{n}
$$

we're going to use the definition that the covariance within groups is equal to the variance among groups. 

$$
\sigma^2_S = cov(PatHS) = 1/4 V_A
$$
$$
4\hat{\sigma}^2_S = \hat{V}_A
$$
PatHS = Paternal half-sibs

variance of dams
$$
\sigma^2_d = cov(FullSibs) - \sigma_S^2 = 1/2 V_A + 1/4 V_D - 1/4 V_A \\
= 1/4V_A + 1/4 V_D
$$
$$
4(\sigma_d^2 - \sigma^2_s) = V_D
$$
$$
\sigma^2_w = V_P - \sigma_S^2 - \sigma_d^2 \\
= 1/2 V_A + 3/4 V_D + V_{Eg}
$$




