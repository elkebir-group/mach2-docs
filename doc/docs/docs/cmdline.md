# MACH2 Command Line Usage

[(Back)](../tutorial.md)

Along with the Jupyter Notebook/Python API usage described in the quick start guide, MACH2 can be run in command line in all platforms with Python installed.

## Input

To run MACH2 in command line, you will need the following files:

- **Input tree file**: Tree file describing the input clone tree. This is an edgelist file that follows a tsv format. ([Example](https://github.com/elkebir-group/MACH2/blob/main/data/mcpherson_2016/patient1.tree))
- **Leaf labeling file**: Labeling file describing the leaf labeling of input clone tree. It is in the form of a two-column csv where the first column is a node id and the second column is an anatomic labeling. ([Example](https://github.com/elkebir-group/MACH2/blob/main/data/mcpherson_2016/patient1.labeling))
- *(Optional)* **Coloring file**: An integer mapping for anatomical locations. For visualization purposes. ([Example](https://github.com/elkebir-group/MACH2/blob/main/data/mcpherson_2016/coloring.txt))

## Usage

```text
    usage: mach2 [-h] [-p PRIMARY] [-c COLORMAP] [--log] [-o OUTPUT] [-N NSOLUTIONS] [-C] [-t THREADS] [-s] [-S] clone_tree leaf_labeling

    MACH2

    positional arguments:
    clone_tree            Input clone tree
    leaf_labeling         Input leaf labeling

    options:
    -h, --help            show this help message and exit
    -p PRIMARY, --primary PRIMARY
                            Primary anatomical site
    -c COLORMAP, --colormap COLORMAP
                            Color map file
    --log                 Outputs Gurobi logging
    -o OUTPUT, --output OUTPUT
                            Output folder
    -N NSOLUTIONS, --nsolutions NSOLUTIONS
                            Maximum number of solutions retained
    -C, --count_solutions
                            Only prints the number of solutions (default=False)
    -t THREADS, --threads THREADS
                            Number of threads
    -s, --suboptimal      Returns suboptimal solutions without duplicates, may be slow (default=False)
    -S, --seeding_sites   Minimizes the number of seeding sites too (default=False)
```

## Example

```bash
mach2 data/mcpherson_2016/patient1.tree data/mcpherson_2016/patient1.labeling -c data/mcpherson_2016/coloring.txt
```
