<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD024 -->
<!-- markdownlint-disable MD036 -->

# `mach2.Phylogeny`

[(back)](../../tutorial.md)

Data structure containing the clone phylogeny with only leaf-labelings (i.e. the input tree).

## Constructor

``` py
mach2.Phylogeny(edges, labels, colormap = None)
```

### Parameters

- `edges (list[tuple[str, str]])`: The edgelist of the phylogeny
- `labels (dict[str, str])`: The labeling of the leaves

#### Optional

- `colormap (dict[str, int])`: Mapping of node ids to color indices

## Methods

### `from_file(phylogeny_filename, labeling_filename, colormap_file=None)`

Returns a phylogeny constructed from edgelist and labeling files. Files are described [here](../inputs.md).

#### Parameters

- `phylogeny_filename (str)`: The filename of the edgelist
- `labeling_filename (str)`: The labeling filename
- `colormap_file (str)`: The color map filename

### `from_pandas(phylogeny_df, labeling_df)`

Similarly, constructs a phylogeny from an edgelist and labeling Pandas 2-column dataframes.

#### Parameters

- `phylogeny_filename (str)`: The dataframe of the edgelist
- `labeling_filename (str)`: The labeling dataframe

### `get_label(node)` *(str)*

Returns the anatomical location of a node. Throws a `ValueError` if the node is unlabeled.

#### Parameters

- `node (str)`: The node id in the phylogeny

### `get_parent_arc(node)` *(tuple[str, str])*

Returns the parent edge leading to the node `(parent_id, node_id)`.

#### Parameters

- `node (str)`: The node id in the phylogeny

### `get_children_arcs(node)` *(list[tuple[str, str]])*

Get edges going to children nodes.

#### Parameters

- `node (str)`: The node id in the phylogeny

### `write_tree(filename)`

Write the tree to an edgelist file

#### Parameters

- `filename (str)` The name of the file being written to

### `write_labeling(filename)`

Write the node labeling to file (of nodes that have labelings)

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
