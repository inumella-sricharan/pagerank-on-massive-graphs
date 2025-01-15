# pagerank-on-massive-graphs
 Ranking nodes in massive graph networks with pagerank algorithm by making use of sparse matrix operations.

## <ins>👉 Intro:</ins> <br>
This project is about applying pagerank algorithm on a massive graph/network (in this case its a segment the wikipedia graph) and <br>
optimize the memory and speed using sparse matrix multiplications.<br>

## <ins>🌐 PageRank Algorithm:</ins> <br>
If we pose the problem of calculating centrality / importance of a node as<br> 
$\lambda C_{i} = \sum_{j \epsilon neighbors of i} C_{j}$

$M = \beta P^{T} + (1 - \beta)\[1/N\]_{N x N}$ <br>

$\text{Here  } \beta \text{  is the damping factor and P is the transition matrix. And M is the final markov matrix.}$ <br>
$\text{And N is the total number of nodes in the graph}$ <br>

$R_{t+1} = M R_{t} \text{    ---> until convergence}$ <br>

## <ins>🌀 Re-arranging the equation to reduce the computations:</ins> <br>

$R_{t+1} = \[\beta P^{T} + (1 - \beta) \[1/N\]_{N \times N}\] R_t$ <br>


$R_{t+1} = \beta P^{T} R_t + (1 - \beta) \[1/N\]_{N \times 1}$ <br>

$\text{since  } \sum^{N}_{i=1} r_i = 1$ <br>

$\text{We still have 'dead-end' nodes in   } P^{T} \text{   , i.e those nodes with no outlinks.}$ <br>

$\text{The sum of column values for these nodes is 0. But we need to enrich it such that sum of col = 1}$ <br>

$R_{t+1} = \beta P^{T} R_t + R_t\[dead-end\]\times\beta\[1/N\]  + (1 - \beta) \[1/N\]_{N \times 1}$ <br>

$R_{t+1} = \beta P^{T} R_t + \(r_{t}^{d1} \times\beta\[1/N\] + r_{t}^{d2} \times\beta\[1/N\] .... + r_{t}^{dk} \times\beta\[1/N\]\)+ (1 - \beta) \[1/N\]_{N \times 1}$ <br>

$\text{ Where d1, d2, ... dk are dead-end nodes}$

