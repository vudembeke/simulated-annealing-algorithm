# SIMULATED ANNEALING ALGORITHM
## Contributors:
<p>1. Brianna Vudembeke - Algorithm research, README file </p>
<p>1. Nyaga Muthomi Nathaniel V - Algorithm research, Python code, Beamer </p>

## Introduction
<p> Simulated annealing is a proposed alternative to generic greedy search,hill climbing algorithms. A hill climbing algorithm is really good at finding local optimal solutions but doesn't perform well with global solution.</p>
<p> Inspiration simulated Annealing is inspired by the process of annealing in metallurgy. In this natural process a material is heated and slowly cooled under controlled conditions to increase the size of the crystals in the material and reduce their defects. This has the effect of improving the strength and durability of the material. </p>

## Simulated Annealing Algorithm
<p> Simulated annealing is a probabilistic to finding a global maximum. </p>
<p> The main difference in strategy between greedy search and simulated annealing is that greedy search will always choose the best proposal, where the simulated annealing has a probability(using a Boltzman distribution) of choosing a worst proposal than strictly only accepting improvements. </p>
<p> This helps the algorithm find a global optimum by jumping out of local optimum. </p>
<p> The simulated annealing algorithm goes as follows for a function h(.) that we're trying to maximize:  </p>
<ol>
    <li>Generate an initial candidate solution x</li>
    <li>Get an initial Temperature T > 0</li>
    <li>For i in 1:N(N = number of iterations):</li>
    <ul>
    <li>Sample ζ ~ g(ζ) where g is a symmetrical distribution.</li>
    <li>The new candidate solution is x' = x ± ζ </li>
    <li>Calculate probability p=exp(Δ h/T~i~)</li>
    <li>Accept the candidate solution with probability p; u U(0, 1), accept x = x' if u ≤ p.</li>
    <li>Update the temperature (cooling), e.g. T = aT where 0 < a < 1</li>
</ul>
</ol>
## Notes on Parameters
<p> The greater the value of T (temperature), the greater likelihood of moving around the search space. As T get closer to zero, the algorithm will function like greedy hill climbing </p>
<p> Good starting values for T will vary problem by problem. I usually start with 1, 10, 100 and adjust after a few experiments. For a, I normally choose 0.95. However, you can change T by any amount, Robert and Casella suggest a temperature decrease in 1/log(1+i) for i in 1:N

## References
<p> Introduction to Monte Carlo Methods with R by Robert and Casella  </p>
<p> Optimization by Simuland Annealing: An Experimental Evaluation; Part I, Graph Partitioning  </p>
