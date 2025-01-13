# pagerank-on-massive-graphs
 Ranking nodes in massive graph networks with pagerank algorithm by making use of sparse matrix operations.


$M = \beta P^{T} + (1 - \beta)\[1/N\]_{N x N}$ <br>

$\text{Here  } \beta \text{  is the damping factor and P is the transition matrix. And M is the final markov matrix.}$ <br>

$R_{t+1} = M R_{t}$ <br>

Re-arranging the equation to reduce the computations <br>

$R_{t+1} = \[\beta P^{T} + (1 - \beta) \[1/N\]_{N \times N}\] R_t$ <br>


$R_{t+1} = \beta P^{T} R_t + (1 - \beta) \[1/N\]_{N \times 1}$ <br>

$\text{since  } \sum^{N}_{i=1} r_i = 1$ <br>

$\text{We still have 'dead-end' nodes in   } P^{T} \text{   , i.e those nodes with no outlinks.}$ <br>

$\text{The sum of column values for these nodes is 0. But we need to enrich it such that sum of col = 1}$ <br>

$R_{t+1} = \beta P^{T} R_t + R_t\[\{dead-end nodes\}\]\times\beta\[1/N\]  + (1 - \beta) \[1/N\]_{N \times 1}$ <br>

$R_{t+1} = \beta P^{T} R_t + \(r_{t}^{d1} \times\beta\[1/N\] + r_{t}^{d2} \times\beta\[1/N\]\ .... + r_{t}^{dk} \times\beta\[1/N\]\)+ (1 - \beta) \[1/N\]_{N \times 1}$ <br>

