# CW2011-ReplicationCodes

[![License](https://img.shields.io/badge/license-BSD%203--clause-green.svg)](https://github.com/vcurdia/CW2011-ReplicationCodes/blob/master/LICENSE)

These codes reproduce the results in:

**Cúrdia, V., and M. Woodford (2011)**  
[The Central-Bank Balance Sheet as an Instrument of Monetary Policy](http://www.sciencedirect.com/science/article/pii/S0304393210001224)  
*Journal of Monetary Economics*, 58(1), pp. 54-79.

[Technical Appendix](https://github.com/vcurdia/CW2011-ReplicationCodes/blob/master/CW2011_Appendix.pdf)

These replication codes are available online at:  
https://github.com/vcurdia/CW2011-ReplicationCodes

# Requirements

## Matlab (R)
The codes were tested using Matlab (R) R2016b with the following toolboxes
- Symbolic Toolbox
- Optimization Toolbox

## LaTeX
LaTeX is used by some tools to compile certain documents.

`epstopdf`, included in most LaTeX releases, is used by some tools.


## Additional codes

Codes by [Vasco Cúrdia](http://www.frbsf.org/economic-research/economists/vasco-curdia/):
- [ACR-LQ](https://github.com/vcurdia/ACR-LQ)
  joint with Filippo Altissimo and Diego Rodriguez Palenzuela, version 
  [v1.0.0](https://github.com/vcurdia/ACR-LQ/releases/tag/v1.0.0)

Codes by [Chris Sims](http://www.princeton.edu/~sims/):
- [gensys](http://sims.princeton.edu/yftp/gensys/)
- [optimize](http://dge.repec.org/codes/sims/optimize/)

All auxiliary codes included in this repository in subfolders.


# Description of Replication Codes

## CB incentive to engage in credit policy

These codes produce the figures comparing the response of the Central Bank's
incentive to engage in credit policy displayed in figures 4 and 5 of the
paper.

`Exercise2.m`  
Generates results under the assumption that interest rate is optimal.

`Exercise3.m`  
Generates results under the assumption that interest rate follows a simple
Taylor rule.

Both `Exercise2` and `Exercise3` can be set to ignore or not the zero lower
bound (ZLB); consider different sizes of the shock to the spread; and to
consider different persistency of shocks.

`IRFPlotCompareExercise2.m`  
Plots figure 4, based on results generated by `Exercise2`.

`IRFPlotCompareExercise3.m`  
Plots figure 5, based on results generated by `Exercise2` and `Exercise3`, with
and without ignoring the ZLB.


## Optimal credit policy, under optimal interest rate policy

`Exercise4.m`  
`Exercise4SearchSequence.m`  
Generate solution and IRF with and without credit policy, under optimal
interest rate policy. First need to run `Exercise4` to generate base results
under a given sequence of regimes (with and without credit policy and with and
without ZLB binding). Then use `Exercise4SearchSequence` to more quickly check
alternative sequences of regimes. The search is done by checking if the ZLB is
violated, if credit policy is negative, or if the lagrange multipliers for the
slack conditions are negative. Each time that the `SearchSequence` code is run
tables with checks and a plot with evolution of some of these are shown to
inform on how to change the candidate sequence of regimes.

`IRFPlotCompareExercise4.m`  
Plot the IRFs with and without credit policy. There are several options
available.


## Optimal credit policy, under interest rate Taylor rule

`Exercise5.m`  
`Exercise5SearchSequence.m`  
Generate solution and IRF with and without credit policy, when interest rate
follows a simple Taylor rule. First need to run `Exercise5` to generate base
results under a given sequence of regimes (with and without credit policy and
with and without ZLB binding). Then use `Exercise5SearchSequence` to more
quickly check alternative sequences of regimes. The search is done by checking
if the ZLB is violated, if credit policy is negative, or if the lagrange
multipliers for the slack conditions are negative. Each time that the
`SearchSequence` code is run tables with checks and a plot with evolution of
some of these are shown to inform on how to change the candidate sequence of
regimes.

`IRFPlotCompareExercise5.m`  
Finally, `IRFPlotCompareExercise5` is used to plot the IRFs with and without
credit policy.


## Credit policy rule

`Exercise6.m`  
`Exercise6SearchSequence.m`  
Generate solution and IRF under simple credit policy rule, when interest rate
follows a simple Taylor rule. First need to run `Exercise6` to generate base
results under a given sequence of regimes (with and without ZLB binding). Then
use `Exercise6SearchSequence` to more quickly check alternative sequences of
regimes. The search is done by checking if the ZLB is violated. Each time that
the `SearchSequence` code is run tables with checks and a plot with evolution
of some of these are shown to inform on how to change the candidate sequence of
regimes.

`IRFPlotCompareExercise6.m`  
Plot the IRFs under alternative credit policy rule coefficients. These figures
are not shown in the JME version of the paper but are shown in
the [NBER working paper](http://www.nber.org/papers/w16208) version.


## Options for the previous codes (common to all of them)

`BindBp` controls how much higher CB intervention cost is relative to
the steady state critical level for no credit policy lending in steady
state, measured in basis points, where a value of zero implies that it is at
the critical level and a value of 10 is 10bp higher, as shown in figure 8,
for example. 

`dSP` controls the size of the shock to the spread, with 4 representing 4% in
annualized terms.

`PersSP` controls the persistency of the shock, with 90 corresponding to an
AR(1) coefficient of 0.90.


## Scripts to generate individual figures

Because there are many options and switches available, we also include scripts
that generate the individual figures of the JME and NBER papers. Each of these
runs all necessary pre-requirements and tweaks needed for each figure.

`MakeFig4.m`  
`MakeFig5.m`  
`MakeFig6.m`  
`MakeFig7.m`  
`MakeFig8.m`  
`MakeFig9.m`  
`MakeFig10.m`  
`MakeFig11.m`  
`MakeFig12.m`  
`MakeFigNBER5.m`

