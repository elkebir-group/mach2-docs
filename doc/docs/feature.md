# Features

## MACH2 Features

MACH2 infers migration histories of metastatic cancers given the clonal phylogeny and the location of extant clones.

MACH2 takes as **input** the following:

1. **Input tree file** : Tree file describing the input clone tree.
2. **Leaf labeling file** : Labeling file describing the leaf labeling of input clone tree.

And returns **output** in one of the following formats:

1. **Refined tree file** : Tree file describing the output refined tree.
2. **Vertex labeling file** : Labeling file describing the vertex labeling of the refined tree. Labels designate the anatomical location of each node.
3. **Refined tree DOT** : Refined tree with vertex labeling in [DOT](https://en.wikipedia.org/wiki/DOT_(graph_description_language)#:~:text=DOT%20is%20a%20graph%20description,dot%20filename%20extension%20—%20.) format.
4. **Migration graph file** : Multi-graph file describing the migration graph.
5. **Migration graph DOT** : Migration graph in DOT format.

## MACH2-Viz Features

MACH2-Viz is an interactive visualizer that allows the user to explore migration patters inferred by MACH2. It has the following features.

- **Highlight corresponding nodes**: The user can highlight nodes in the clonal tree or migration graph, and nodes in the corresponding structure will highlight as well.
- **Compare solutions**: Users can open solutions side by side and compare them.
- **Require or omit migrations**: A summary panel can be opened and migration edges can be required or omitted from the list of solutions displayed.
- **Examine polytomy refinement**: The input clonal phylogeny can be compared against the refined phylogeny and corresponding nodes can be panned to and comapred.
- **Extensibility**: Users can upload their own solutions or make contributions to the home page table of example solutions.
- **Backwards compatibility**: Solutions from [MACHINA (2018)](https://github.com/raphael-group/machina) can also be loaded into the visualizer.
