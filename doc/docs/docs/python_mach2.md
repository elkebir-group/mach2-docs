# MACH2 Python Usage

[(back)](../tutorial.md)

Along with running via command line, you can compute migration histories using the Python API. Suppose you have a clone tree file `patient.tree` and an anatomical labeling of the leaves/extant nodes of the tree `patient.labeling`. For more information on the input files required for MACH2, see [here](inputs.md).

## 1. Load the Data

Data can be loaded through the following Python code:

``` py
import mach2

tree = mach2.Phylogeny.from_file('patient.tree', 'patient.labeling') #(1)
```

1. This line creates a `Phylogeny` object storing the leaf-labeled tree. In the next section we will solve this tree by labeling the internal nodes.

## 2. Compute the Solution

This is simply done with the following code:

``` py
solver = mach2.MACH(tree, primary_site=None)  #(1)
solutions = solver.solve('gurobi', 30, n_threads=30) #(2)
```

1. Optionally, you can specify a primary tumor location in the form of a string. If the primary location is `None`, then all solutions across multiple possible primary tumor locations will be returned.
2. This creates a `SolutionSet` object that contains all possible labeled trees. An ILP solver like Gurobi is required to compute these solutions, so be sure to have that installed.

## 3. Exporting Solutions

Now that you have a Python object storing the solutions, you need to export it to a more readable format. This can be done in the following ways.

### Exporting to JSON

This is done with the following line of code. This will result in a JSON similar in format to [this example](https://github.com/elkebir-group/mach2-viz/blob/main/src/samples/A7/A7.json).

``` py
solutions.json('out.json') #(1)
```

1. Replace the filename with whatever you want.

### Static Visualization

If you are using a Jupyter Notebook, you can return static visualizations. You can index into one of the solutions and generate visualizations through the following code.

``` py
solutions[0].phylogeny #(1)
solutions[0].migration_graph
```

1. Change the index depending on the solution you would like to view. To get the number of solutions simply run `len(solutions)`

This method is shown in [this example](https://elkebir-group.github.io/mach2-docs/quickstart/#visualizing-solutions).

### Interactive Visualization (Recommended)

Interactive visualizations allow for filtration of solutions based on priors such as known migrations or absences of migrations. It also allows for examining polytomy resolution and visualilzation of the entire solution space. To open a visualization directly from Python, run the following snippet of code. You should see a window like [this](https://elkebir-group.github.io/mach2-viz/#/viz?labeling=T-0&labeling2=T-0) open up.

``` py
solutions.open_in_viz()
```

**Alternatively**, you can:

1. Export the solution to JSON file
2. Open the homepage of MACH2-Viz [(link)](elkebir-group.github.io/mach2-viz/)
3. Click the `+` icon at the bottom right and upload your file.

## Python API

These methods are a part of the Python API. Please see the following objects for more information on the API:

- [MACH](api/mach.md)
- [MigrationGraph](api/migrationgraph.md)
- [Phylogeny](api/phylogeny.md)
- [RefinedPhylogeny](api/refinedphylogeny.md)
- [SolutionSet](api/solutionset.md)
- [Solution](docs/api/solution.md)
