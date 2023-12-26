# `mach2.SolutionSet.Solution`

[(back)](../tutorial.md)

A single solution object contained within the [`mach2.SolutionSet`](solutionset.md) object. This contains a refined and labeled phylogeny, and a migration graph.

## Constructor

``` py
mach2.SolutionSet.Solution(tree, graph)
```

### Parameters

- `tree ([mach2.RefinedPhylogeny)`: The [refined phylogeny](refinedphylogeny.md) in the solution
- `graph (mach2.MigrationGraph)`: The computed [migration graph](migrationgraph.md)
