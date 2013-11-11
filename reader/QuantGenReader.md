Quant Gen Reader
========================================================


Chapter 3 
----------------------------------------------------------

### Dispersive process
There are two ways of looking at the dispersive process, either look at it like a sampling process and consider it in terms of sampling variance, or think of it like an inbreeding process and describe it in terms of genotypic changes resultant from mating individuals.


The dispersive process can be broken down into four parts, Falconer mentions these as the four _consequences_. 

#### Random Drift
This is also known plainly as drift. This is the random changes in gene frequency in a population from generation to generation. 
 
 
#### Differentiation between sub-populations
Subpopulations differentiate from each other by the process of drift occuring independently in the subpops. Natural pops are broken up into subpops because no large pop is truly randomly mating within itself.

#### Uniformity within sub-populations
As generations occur, genetic variation in subpops becomes more and more reduced, as the individuals become more genetically similar. _I don't really understand how this is a consequence of the dispersive process, Falconer goes on to mention something about inbred lines being used in laboratory_


#### Increased Homozygosity
Homozygotes increase in frequency. Since most deleterious alleles are recessive, the accumulation of recessive homozygotes is the genetic basis of reduced vigor and fitness that comes with inbreeding.

### Sampling

#### Variance of Gene Frequency
$q_0$ is the gene frequency of one allele in the base population. Forming lines from te base population is like a sampling problem, with each individual of the base pop having N genes, and forming 2N gametes which are then sampled at random to produce the next generation. The gene frequencies will then be an average of the base populaiton, i.e. $q$ will be $q_0$.  The averages will be distributed about the base pop means with a variance of $p_0q_0/2N$, which is the variance of $q_1$, the gene frequency in different lines after one generation. 

Variance of gene frequency from going from base to 1st pop is:
$$ 
\sigma_{p_0}^2 = \frac{p_0q_0}{2N}
$$

This can then be generalized to the variance of gene frequency among the lines at any given generation $t$ is:
$$
\sigma_p^2 = p_0q_0 \left[1 - \left(1 - \frac{1}{2N}  \right)^2 \right]
$$

### Inbreeding

__IBD - Identity By Descent__ One of the effect of a common ancestor is that that indivudals could carry replicates of a gene from the common ancestor. When they mate, the offspring has the potential to acquire both replicates, becoming homozygous for this gene from the common ancestor. This type of homozygote is one of a "origin of replication", two genes arising from the replication of one ancestral gene. This is called _identical by descent_. 

__coefficient of inbreeding__ $F$, the probability that two genes at any locus in an individual are identical by descent. If parents are mating at random, then this becomes the probability that any two gametes taken at random from the parent generation carry identical alleles at any given locus.

The coefficient of inbreeding in successive generations can be calculated by:
$$
F_t = \frac{1}{2N} + \left( 1 - \frac{1}{2N}  \right)F_{t-1}
$$

The change in inbreeding from generation to generation is:
$$
\Delta F = \frac{1}{2N}
$$

It can also be expressed as:
$$
\Delta F = \frac{F_t - F_{t-1}}{1 - F_{t-1}}
$$

There is also the panmictic index, $P$, where $P = 1-F$. 

The inbreeding coefficient of any generation $t$, is given by 
$$
F_t = 1 - (1 - \Delta F)^t \\
F_t = 1 - (1- \frac{1}{2N})^t
$$

### Variance of gene frequency

Variance of gene frequency using the inbreeding coefficient:
$$
\sigma^2_q = p_0 q_0 F_t
$$



Chapter 5 - Pedigreed Population and Close Inbreeding
---------------------------------------------------------













Chapter 7 - Values and Means
-------------------------------------------------------

Initially, we need to think about the genotype value. If we take genotypes and put them on a scale, $A_1A_1$ will be at $+a$, $A_1A_2$ will be at $d$, and $A_2A_2$ will be $-a$. To find these values, $a = (A_1A_{1value} - A_2A_{2value})/2$, the midpoint is $A_1A_{1value} - a$ and $d = A_1A_{2value}-midpoint$

We can determine effects of dominance by looking at the value of $d$. If $d=0$, then there is no dominance. If $d>0$, then $A_1$ is dominant, if $d<0$, then $A_2$ is dominant. If $d=\pm a$, then there is complete dominance of either allele. Overdominance is when $d$ is greater than $\pm a$. Another way to look at dominance is $d/a$.

### Population Mean
The mean value of the population is acquired by multiplying the value of each of the genotypes by their frequency, and summing over the three genotypes:
$$
M = a(p-q) + 2 dpq
$$


#### Average Effect
Average effects are the properties of genes and populations, the genes and the gene frequencies. The average effect of a particular gene/allele is the mean deviation from the population mean of individuals that recieved that gene from one parent, and the other gene coming from another parent at random from the population. Another way to think about this, is to take a number of gametes with $A_1$ pair with other gametes chosen at random from the population; then the mean of these genotypes differs from the population mean by an amount, $\alpha_1$, the average effect of allele $A_1$. 
 
Average effect of $A_1$ is called $\alpha_1$:
$$ \alpha_1 = q[a+d(q-p) ] $$

The average effect of $A_2$ is $\alpha_2$:
$$\alpha_2 = -p[a + d(q-p) ] $$ 

When we are only considering two alleles, we can then talk about the __average effect of substitution__, which is the difference between the average effects of the two alleles, this is written as $\alpha$.
$$
\alpha = a + d(q-p) = \alpha_1 - \alpha_2
$$




#### Breeding Value

Genotype | Breeding Value
--------|-----------
$A_1A_1$ | $2\alpha_1 = 2q\alpha$
$A_1A_2$ | $\alpha_1 + \alpha_2 = (q-p)\alpha$
$A_2A_2$ | $2 \alpha_2 = -2p\alpha$



Chapter 8 - Variance
----------------------------------------------------------------

$$ P = G + E$$ and therefore  $$V_P = V_G + V_E$$ where $V_P$ is the variance in the total phenotype, $V_G$ in the variance in the contribution of the genotype to the total phenotype, and $V_E$ is the variance of the environmental effects on the phenotype. 

#### Componenets of variance  

|Variance Componenent | Symbol | Value that's measured|  
|-------------|:----------------:|----------------|  
Phenotypic | $V_P$ | Phenotypic value  
Genotypic | $V_G$ | Genotypic Value  
Additive | $V_A$ | Breeding Value  
Dominance | $V_D$ | Dominance Deviation  
Interaction | $V_I$ | Interaction Deviation   
Environmental | $V_E$ | Environmental Deviation   


### Heritability
Heritability = the relative importance of heredity in determining phenotypic values  
The ratio of $V_G/V_P$ is the extent to which individuals phenotypes are determined by the genotypes. This is the variance in the genotypic value over the variance in the phenotypic value. Also known as _heritability in the broad sense_ or _the degree of genetic determination_

_Heritability in the narrow sense_ ($h^2$) is $V_A/V_P$, the variance in the additive effects (Breeding Value, $A$), over the variance in the total phenotype. This is also known simply as _heritability_. Heritability determines the amount of resemblance between relatives. 

### Genetic components of variance 

$$G = A + D + I $$
$$V_G = V_A + V_D + V_I$$
Where G is the genotypic, A is the additive, D is the dominance, and I is the interaction variance. The __additive variance__ is the variance between breeding values. 

Expressions for variance of breeding values and dominance deviations are given in ch 7 ... table 7.3

Additive variance is:
$$ V_A = 2 p q \alpha^2$$
$$ V_A = 2 p q [ a + d(q - p)]^2 $$

The variance of dominance deviations is:
$$V_D = (2pqd)^2 $$

If there is no dominance (d = 0), then:
$$V_A = 2pqa^2 $$

But if there is complete dominance (d=a), then:
$$V_A = 8pq^3a^2 $$ 

If the allele frequencies are the same (p=q=0.5), then:
$$ V_A = \frac{1}{2}a^2 $$
$$ V_D = \frac{1}{2}d^2$$


### Total Genetic Variance

$$V_G = V_A + V_D $$
$$ V_G = 2pq[a+d(q-p)]^2 + (2pqd)^2 $$

### Multiple measurements: repeatability

Variance that is within an individual and arises from temporary or localized circumstances is called _special environmental variance_, or $V_{Es}$. The environmental variance contributing to the between-individual component which is also permanent (not temporary), is the _general environmental variance_, $V_{Eg}$. One can also calculate the ratio of the between-individual component and the total phenotypic variance:
$$
r = \frac{V_G + V_{Eg}}{V_P}
$$

Chapter 9
-------------------------------------------------------

There's now a distinction between the causal components of variance, $V$, and the observation components of variance, $\sigma^2$. $V$ is the phenotypic variance due to different causes. $\sigma^2$ is produced by partitioning the phenotypic variance by families that individuals belong to. 

Example of ANOVA to illustrate this. Groupings of individuals into families of full sibs. ANOVA can partition the total variance into two parts, variation within groups, and variation between (among) groups. Between group component is the variance of the true means of the groups about the population mean, the within-group component is the variance of the individuals about the true mean of the group.

Intraclass correlation coefficient:
$$
t = \frac{\sigma^2_B}{\sigma^2_B + \sigma^2_W}
$$
Where $\sigma^2_B$ is the between-group component and $\sigma^2_W$ is the within-group component of variance. 

The regression of offspring on parents (how predictive the parents values are for offspring values):
$$
b_{OP} = \frac{cov(O,P)}{\sigma^2_P}
$$

Also, in the book they derived the following equation:
$$
cov(O,P) = \frac{1}{2}V_A
$$
Which states that the genetic covariance of offspring and one parent is half the genetic variance of the parents.

The generalized covariance of any relationship is:
$$
cov = r V_A + u V_D
$$
where $r$ is the fraction of additive genetic variance, and $u$ is the the fraction of dominance variance.

$$
r = 2 f_PQ
$$
and
$$
u = f_{AC}f_{BD} + f_{AD}f_{BC}
$$

$r$ can sometimes be called the coefficient of relationship, or the theoretical correlation between relatives considered. 
Chapter 10 - Heritability
------------------------------------------

(Narrow sense) Heritability, $h^2$ is equal to:
$$
h^2 = V_A / V_P
$$

an equivalent statement is that heritability is equal to the regression of the breeding value, $A$, on the phenotypic value, $P$:
$$
h^2 = b_{AP}
$$

an individual's estimated breeding value is the product of its phenotypic value and the heritability:
$$
A_{expected} = h^2 P
$$

small populations maintained over a long number of generations have many alleles fixed, and therefore have lower $V_P$. Compared to a larger population, the smaller pop will have a lower heritability since a lot of the phenotypic variation is due environmental variance



Chapter 11 - Selection
------------------------------------

rate of response to selection, $R$, is given by:
$$
R = i h^2 \sigma_P
$$
Where $i$ is the selection intensity, $h^2$ is the narrow sense heritability ( $1/2h^2$ = regression of offspring on single parents), and $\sigma_P$ is the phentypic standard deviation.

Ways to improve the response:
- increase heritability - done by reducing environmental variation (controlling environment, multiple measurements, to a certain extent assortive matings)
- phenotypic standard deviation is just specifying units - can't change it
- increasing intensity of selection - limited by reproduction rates (can't select less for breeding than are needed to be selected for for population replacement)


Chapter 12 - Experimental results of selection 
---------------------------------------

### Asymmetry of response

#### Random Drift
Asymmetry can result from random drift, random sampling of a allele from generation to generation. If there is only one replicate per selection treatment, then one can't determine if drift is the cause for asymmetrical response to selection. Drift cannot be predicted. 


#### Selection Differential
The selection differential may be different depending on direction of selection  

1. Natural selection may aid / inhibit selection in one direction or the other.  
2. fertility may change so that the intensity of selection that can be applied changes.  
3. As the trait means change over generations, the variances associated with them might change as well, either increasing or decreasing.  


#### Inbreeding depression
If the populations used for selection experiments are small, then inbreeding becomes a problem. If trait selected is subject to inbreeding depression, then the mean will decrease as inbreeding occurs.

#### Maternal Effects
Maternal component affects measured traits. Weaning weights of rat pups, larger moms produce more milk and feed pups better, resulting in higher weight. 6 weeks post-wean growth is no dependent on maternal effects. Atributing traits to be maternally influeced changes the selection from one character, to one that the mother has. 

#### Genetic Asymmetry
Genetic Asymmetry deals with effects of additive effects from genes at certain frequencies, and how changing their frequencies changes the amount of heritability. 

#### Genes with large effects
Initial selection acts on genes of large effect, causing a rapid and large change in the trait of interest. But subsequent selection results in a very anemic, or no, response to selection. 


#### Scalar Asymmetry
This arises when the genetic and environmental variances are skewed. This occurs when there are GxE interactions, such that individuals in one environment show less variability than those in a different one (good environment produces low variability, poor environment produces high variability). 


#### Indirect Selection
The selective pressure imposed to select on one trait (e.g. body size), inadvertently selects on a different trait (e.g. activity level/speed of movement)


