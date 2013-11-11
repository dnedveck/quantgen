10-17 Quant Gen
======================================================

to obtain the estimate of the additive variance, 
$$
\hat{V}_A = 4 * (MS_S - MS_D) / n * d  
$$

Just by sampling variation alone, if the variance is close to zero, then the sampling variation would cause the values to be negative some of the time. 

Or another cause for negative values is having the wrong model of variance (not accounting for a bias)

$$
\sigma^2_S = cov(between paternal halfsibs) = 1/4 V_A \\
\sigma^2_d = cov(between maternal halfsibs) = 1/4 V_A \\
\sigma^2_{S*d} = cov(full sibs) -\sigma^2_S - \sigma^2_d = 1/4 V_D \\
\sigma^2_w = within full sib families = 1/2 V_A + 3/4 V_D + V_{Eg}
$$
$\sigma^2_w$ is also known as the segregation variance. 


$$
\sigma^2_d - \sigma^2_S = V_{mat} \\
4* \sigma^2_{S*d} = V_D
$$




------------------------------------------------------

### Discussion of Mitchell and Shaw 1993











