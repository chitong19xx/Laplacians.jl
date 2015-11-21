# graphAlgs
### components
Computes the connected components of a graph. Returns them as a vector of length equal to the number of vertices. The vector numbers the components from 1 through the maximum number. For example,

```julia
gr = ErdosRenyi(10,11)
c = components(gr)

10-element Array{Int64,1}:
 1
 1
 1
 1
 2
 1
 1
 1
 3
 2
```


```julia
components{Tv,Ti}(mat::SparseMatrixCSC{Tv,Ti})
```

graphAlgs.jl:65



### vecToComps
This turns a component vector, like that generated by components, into an array of arrays of indices of vertices in each component.  For example,

```julia
comps = vecToComps(c)

3-element Array{Array{Int64,1},1}:
 [1,2,3,4,6,7,8]
 [5,10]         
 [9]   
```


```julia
vecToComps{Ti}(compvec::Array{Ti,1})
```

graphAlgs.jl:123



### biggestComp
Return the biggest component in a graph, as a graph


```julia
biggestComp(mat::SparseMatrixCSC{Tv,Ti<:Integer})
```

graphAlgs.jl:146



### shortestPaths
Computes the lenghts of shortest paths from `start`. Returns both a vector of the lenghts, and the parent array in the shortest path tree. DOC BETTER


```julia
shortestPaths{Tv,Ti}(mat::SparseMatrixCSC{Tv,Ti}, start::Ti)
```

graphAlgs.jl:161



### kruskal
Uses Kruskal's algorithm to compute a minimum (or maximum) spanning tree. Set kind=:max if you want the max spanning tree. It returns it a a graph


```julia
kruskal{Tv,Ti}(mat::SparseMatrixCSC{Tv,Ti})
```

graphAlgs.jl:357


