# SIMULATED ANNEALING ALGORITHM
## Contributors:
<p>1. Brianna Vudembeke - </p>
<p>1. Nyaga Muthomi Nathaniel V - </p>

## Introduction
Simulated annealing is a proposed alternative to generic greedy search,hill climbing algorithms. A hill climbing algorithm is really good at finding local optimal solutions but doesn't perform well with global solution.
Inspiration simulated Annealing is inspired by the process of annealing in metallurgy. In this natural process a material is heated and slowly cooled under controlled conditions to increase the size of the crystals in the material and reduce their defects. This has the effect of improving the strength and durability of the material.

## Simulated Annealing Algorithm
Simulated annealing is a probabilistic to finding a global maximum.
The main difference in strategy between greedy search and simulated annealing is that greedy search will always choose the best proposal, where the simulated annealing has a probability(using a Boltzman distribution) of choosing a worst proposal than strictly only accepting improvements.
This helps the algorithm find a global optimum by jumping out of local optimum.
The simulated annealing algorithm goes as follows for a function h(.) that we're trying to maximize:
    1. Generate an initial candidate solution x
    2. Get an initial Temperature $ T > 0$
    3. for i in 1:N(N = number of iterations)
        a. Sample $ \zeta ~ g(\zeta)$ where g is a symmetrical distribution.
        b. The new candidate solution is $x' = x ± \zeta$
        c. Calculate probability $p=exp(\Delta h/T_{i})$
        d. Accept the candidate solution with probability $p; u U(0, 1)$, accept $x = x'$ if $u \leq p.$
        e. Update the temperature (cooling), e.g. $T = aT where 0 < a < 1$

## Notes on Parameters
The greater the value of T (temperature), the greater likelihood of moving around the search space. As T get closer to zero, the algorithm will function like greedy hill climbing
Good starting values for T will vary problem by problem. I usually start with 1, 10, 100 and adjust after a few experiments. For a, I normally choose 0.95. However, you can change T by any amount, Robert and Casella suggest a temperature decrease in $1/log(1+i)$ for i in 1:N

## References:
Introduction to Monte Carlo Methods with R by Robert and Casella
Optimization by Simuland Annealing: An Experimental Evaluation; Part I, Graph Partitioning
