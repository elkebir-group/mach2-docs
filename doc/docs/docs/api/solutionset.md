<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD024 -->
<!-- markdownlint-disable MD036 -->

# `mach2.SolutionSet`

[(back)](../../tutorial.md)

Object containg a set of solutions (a refined phylogeny and a migration graph). This is returned by [`mach2.MACH.solve`](https://elkebir-group.github.io/mach2-docs/docs/api/mach/#solvesolver-nsolutions-logfile-n_threads0-rawfalse).

## Constructor

``` py
mach2.SolutionSet(sol_list)
```

### Parameters

- `sol_list (list[tuple[mach2.RefinedPhylogeny, mach2.MigrationGraph]])`: The list of solutions to PMH-TR.

## Methods

### `__len__()`

In order to get the number of solutions, use `len(solutions)`

### `__getitem__(key)`

To index into a solution, use `solutions[key]`

### `co_occurence_table()` *(pandas.DataFrame)*

Returns a heatmap of the frequency of migrations that were in co-migrations together.

### `compute_summary(primary=None)` *(collections.defaultdict)*

Returns a summary migration graph, unioning edges across the solutions.

#### Parameters

- `primary (str)`: Specify a primary argument if you would like to constrain solutions from a single primary tumor location.

### `summary(self, primary=None, colormap=None, colormap_file=None, consider_multi_edges=False, dot=True)` *(graphviz.DiGraph | collections.defaultdict)*

A packaged method that either returns a DOT visualization of the summary graph, or the dictionary representing a summary graph.

#### Parameters

- `primary (str)`: Specify a primary argument if you would like to constrain solutions from a single primary tumor location.
- `colormap (dict[str, int])`: A mapping between anatomic label to color index
- `colormap_file (str)`: The coloring file, if a file is being passed instead of colormap data
- `consider_multi_edges (bool)`: Also union parallel edges that distinguish migration events at different times, but from the same locations
- `dot (bool)`: Return a dot visualization, and not a dictionary. If `False`, a `collections.defaultdict` will be returned.

### `summary_dot(filename, primary=None, colormap=None, colormap_file=None, consider_multi_edges=False)`

Returns a DOT visualization of the summary graph

#### Parameters

- `filename (str)`: The name of the file being written to
- `primary (str)`: Specify a primary argument if you would like to constrain solutions from a single primary tumor location.
- `colormap (dict[str, int])`: A mapping between anatomic label to color index
- `colormap_file (str)`: The coloring file, if a file is being passed instead of colormap data
- `consider_multi_edges (bool)`: Also union parallel edges that distinguish migration events at different times, but from the same locations

### `json(name='')` *(dict)*

Returns a json object representing the solutions returned.

#### Parameters

- `name (str)`: Name of the solution set returned. Ex. `patient1`

### `write_json(name='', filename=None)`

Write json object representing the solutions returned to file

#### Parameters

- `name (str)`: Name of the solution set returned. Ex. `patient1`
- `filename (str)`: The name of the file being written to

### `open_in_viz()`

Open the solution space in MACH2-Viz
