10-10 Quant Gen
========================================================

Pick up where we let off - talking about epistasis

$$
cov(X,Y) = rV_A + uV_D + r^2V_{A\times A} + ruV_{A\times D} + u^2V_{D\times D}
$$
$$
V_A = 2pq\alpha^2
$$

Breeding value ($\alpha$) is function of the differences between homozyogtes but also the dominance.

looking at epstasis, making sure everyone knows what it is.

### Addititvity of gene loci example

```r
exdf1 <- data.frame(A2A2 = c(2, 1, 0), A1A2 = c(5, 4, 3), A1A1 = c(6, 5, 4), 
    row.names = c("B1B1", "B1B2", "B2B2"))
exdf1
```

```
##      A2A2 A1A2 A1A1
## B1B1    2    5    6
## B1B2    1    4    5
## B2B2    0    3    4
```


looking at the values in the matrix, we can see that values of B do not depend on values of A. Going along the columns does not affect the row effects. 

### Epistatsis

```r
exdf2 <- data.frame(A2A2 = c(2, 1, 0), A1A2 = c(5, 5, 3), A1A1 = c(5, 5, 4), 
    row.names = c("B1B1", "B1B2", "B2B2"))
exdf2
```

```
##      A2A2 A1A2 A1A1
## B1B1    2    5    5
## B1B2    1    5    5
## B2B2    0    3    4
```



... You can think of $V_{A \times A}$ as the interaction of breeding values at a single loci. 


Now, putting things into practice with data

Between generation comparisons
- use regression
- trait parent or whatever, response is trait in offspring
$$
b = \frac{1}{2} h^2 = \frac{\frac{1}{2} V_A}{V_P} = \frac{cov(O,P)}{var(Parental)}
$$

Common environment 
contributor of shared environment - maternal effects
Maternal effects
- gestation effect
- environementally induced 
- mitchondrial / chloroplast
- seed endosperm (3N), 2N comes from maternal 
- pathogen effect on maternal

one thing to thnk about with al this regression business, is that what we calculate from the data are estimates of the true values. Then there is also sampling variance that affects the estimates that we get. 

heritability on the order of .3, is pretty high. or some traits are like .6

__broad sense heritability__
$$
h^2_B = \frac{V_G}{V_P}
$$

$h^2$ specific to narrow sense heritability
- trait, precision of observation
- population $V_A = 2pq (a+d(q-p))$
- environment 
 - macro environment $G \times E$
 - microenvironment - how variable the environment is

Within comparisons
- sib analysis
- analysis of variance
 - analysis = breaking don ito bits and pieces, breaking down the variance into it's component parts


impose mating scheme
 - random colleciton of sires ($s$), each mated to a randomly assigned distinct group ($d$) of females
 - from each of the matings, $n$ offspring obtained


