10-8 Quant Gen
========================================================

 * Genetic basis of resemblance between relatives
 
 ------------------
 
 
 Fisher- causal components of variance  
$V_A,V_D, V_{Eg}, V_{Ec} \ldots$

causal componets are in contrast to observational compoentens of variance - a different way of partitioning the phenotypic variance   
How do we relate the observational to the causal?

A lot of this relies on the covariance, the measure of the quantitative resemblence of relatives of a certain kind. The measure ofthe linear association of two varianble -- trait values for a pair of individuals in our case. 

Now, we focus onthe genetic basis of resemblance - simply, the sharing of gene between relatives. The closer the relationship the more genes are shared. 

The coefficients of coacestries - the quantitative methods of measuring the sharing of genes between relatives. 

Talking bout expression 9.2  
Regression coefficient  -- $b_{OP} = 1/2 \frac{V_A}{V_P}$
A regression coefficient - Thinking about Galton's Peas, Y vs. X is trait in offspring vs trait in parent. Parents with higher values tended to have offspring with higher values. The slope of this line is b, the regression coefficient. 
slope = b = Cov(Offspring, Parent) / Var(Parental)

Cov(O,P) = 1/2 $V_A$

Going deeper $\ldots$
In thinking aovut the covariance of offsping and parent, Cov(O,P) = Exp[O*P] - Exp[O]Exp[P]; the covariance is equal to the expectation of the product of O and P, minus the expectation of O and expectation of P multiplied together. 


... did a lot of talk of covariance and stuff .. didn't pay attention


Within generation pairs of individuals 

full siblings
 * both alleles shared: $1/2 \times 1/2 = 1/4$
 * single allele shared: $1/2$
 * no alleles shared: $1/2 \times 1/2 = 1/4$
On average, full sibs share a single allele at a locus. 

Cov(Monozygotic Twins) = Var(G) = $V_A + V_D$
Cov(Dizygotic twins) = just like full sibs


General

Cov(any pair of individuals) = $Cov(Z_X,Z_Y)$, Z= trait, individuals X and Y
$$
Cov(Z_X,Z_Y) = rV_A + uV_D
$$

$$
r = 2 f_{X,Y} //
u = Prob(\verb!both alleles are IDB!)
$$

Looking for a general expression for u, how could X and Y share a single allele at a locus?

A X B -> X ; C X D -> Y

$$
u = f_{A,C}f_{B,D} + f_{A,D}f_{B,C}
$$

for epistatsis
$$ 
Cov(Z_X,Z_Y) = r^2 V_{A*A} + ru V_{A*D} + u^2 V_{D*D} + r^3 V_{A*A*A} + r^2u V_{A*A*D} \ldots u^3V_{D*D*D}
$$

