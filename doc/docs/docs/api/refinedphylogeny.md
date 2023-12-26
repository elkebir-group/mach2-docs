<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD024 -->
<!-- markdownlint-disable MD036 -->

# `mach2.RefinedPhylogeny`

[(back)](../../tutorial.md)

Data structure containing the clone phylogeny with a full labeling and polytomy resolution (i.e. the output tree).

**NOTE**: `RefinedPhylogeny` inherits the [`Phylogeny`](phylogeny.md) object, so public methods from `Phylogeny` are callable from `RefinedPhylogeny` as well.

## Constructor

``` py
mach2.RefinedPhylogeny(phylogeny, raw)
```

### Parameters

- `phylogeny (mach2.Phylogeny)`: Phylogeny before refinement
- `raw (dict)`: Raw solutions returned by `MACH.solve()`

## Methods

### `infer_timestamps()`

Infers temporal integer labelings for when the mutated clone arose. Each clone is labeled with a natural number where a higher number means that the clone arose later in time.

### `write_tree(filename)`

Write the tree to an edgelist file

#### Parameters

- `filename (str)` The name of the file being written to

### `write_labeling(filename)`

Write the node labeling to file

#### Parameters

- `filename (str)` The name of the file being written to

### `write_dot(filename, colormap=None, colormap_file=None)`

Write a DOT format visualization of the tree.

#### Parameters

- `filename (str)`: The name of the file being written to
- `colormap (dict[str, int])`: A mapping between anatomic label to color index
- `colormap_file (str)`: The coloring file, if a file is being passed instead of colormap data

### `draw(colormap, colormap_file)` *(graphviz.DiGraph)*

Returns a visualization object of the phylogeny

#### Parameters

- `colormap (dict[str, int])`: A mapping between anatomic label to color index
- `colormap_file (str)`: The coloring file, if a file is being passed instead of colormap data
