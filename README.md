# pagerank-on-massive-graphs
 Ranking nodes in massive graph networks with pagerank algorithm by making use of sparse matrix operations.


$M = \beta P^{T} + (1 - \beta)\[1/N\]_{N x N}$ <br>

$\text{Here  } \beta \text{  is the damping factor and P is the transition matrix. And M is the final markov matrix.}$ <br>

$R_{t+1} = M R_{t}$ <br>

Re-arranging the equation to reduce the computations <br>

$R_{t+1} = \[\beta P^{T} + (1 - \beta) \[1/N\]_{N \times N}\] R_t$ <br>


$R_{t+1} = \beta P^{T} R_t + (1 - \beta) \[1/N\]_{N \times 1}\]$ <br>

$\text{since  } \sigma^{N}_{i=1} r_i = 1$ <br>
