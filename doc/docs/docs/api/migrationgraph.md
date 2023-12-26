<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD024 -->
<!-- markdownlint-disable MD036 -->

# `mach2.MigrationGraph`

[(back)](../../tutorial.md)

Data structure containing the migration graph.

## Constructor

``` py
mach2.MigrationGraph(raw)
```

### Parameters

- `raw`: Raw data describing the migration graph

## Methods

### `has_migration(a, b)` *(bool)*

Returns whether a migration exists in the graph

#### Parameters

- `a (str)`: Anatomical location where the migration is from
- `b (str)`: Anatomical location where the migration is to

### `n_migrations(a, b)` *(int)*

Returns the number of such migrations that exist

#### Parameters

- `a (str)`: Anatomical location where the migration is from
- `b (str)`: Anatomical location where the migration is to

### `migration_edges()` *(list)*

Returns the number of edges in the migration graph.

### `migration_pattern()` *(str)*

Returns the migration pattern shown in the graph as described by *El-Kebir et. al. (2018)* (`'m'`, `'p'`, `'S'`, `'M'`, `'R'`)

### `write_graph(filename)`

Writes the graph into an edgelist format where rows are separated by spaces.

#### Parameters

- `filename (str)`: File being written to

### `draw(colormap=None, colormap_file=None)` *(graphviz.DiGraph)*

Constructs a visualization object of the migration graph

#### Parameters

- `colormap (dict)`: Dictionary mapping node ids to colors
- `colormap_file (str)`: Filename of a color mapping

### `write_dot(colormap=None, colormap_file=None)`

Create a graph vizualization in DOT file format

#### Parameters

- `colormap (dict)`: Dictionary mapping node ids to colors
- `colormap_file (str)`: Filename of a color mapping
