Yi et al. (2005)
================
Frederick J. Boehm
12/10/2019

Last modified: 2020-02-11 10:27:50.

## Model

\[y = \mu + X\Gamma\beta + \epsilon\]

\(\Gamma\) contains only zeroes and ones, to indicate which genomic loci
affect the trait. The entire genome is partitioned into \(H\) loci, and
assume that the QTL can only occur at the \(H\) loci.

For example, we might use the marker positions (with or without
intermediate positions) as the loci.

Yi et al. (2005) focus on at most \(L\) loci, where \(L << H\).

### Choosing \(L\), upper bound on the number of QTL.

Assume that number of QTL, \(l\), is Poisson with mean \(l_0\), the
prior expected number of QTL.

Then, choose \(L\) such that \(P(l > L) < \epsilon\), ie, the
probability that \(l\) is greater than \(L\) is sufficiently small.

For example, one might use \(L = l_0 + 3 \sqrt{l_0}\).

### Prior on \(\gamma\)

\(\gamma\) is an indicator vector of length \(H\). The \(i^{th}\) entry
is 1 if the \(i^{th}\) locus is in the
model.

\[p(\gamma) = \prod_j \left(w_j^{\gamma_j}(1 - w_j)^{1-\gamma_j} \right)\]

where \(w_j = w_m\) or \(w_j = w_e\), depending on whether it’s a main
effect or an epistatic effect. \(w_m\) and \(w_e\) are fixed
hyperparameters. They say in the discussion section that one might put
priors on them, too.

## Questions

1.  If I’m having difficulty with mixing and convergence due the
    reversible jump step in JANNINK and WU (2003), might I use this
    approach instead?? What would that look like?

<div id="refs" class="references">

<div id="ref-jannink2003estimating">

JANNINK, JEAN-LUC, and XIAO-LIN WU. 2003. “Estimating Allelic Number and
Identity in State of Qtls in Interconnected Families.” *Genetics
Research* 81 (2). Cambridge University Press: 133–44.

</div>

<div id="ref-yi2005bayesian">

Yi, Nengjun, Brian S Yandell, Gary A Churchill, David B Allison, Eugene
J Eisen, and Daniel Pomp. 2005. “Bayesian Model Selection for
Genome-Wide Epistatic Quantitative Trait Loci Analysis.” *Genetics* 170
(3). Genetics Soc America: 1333–44.

</div>

</div>
