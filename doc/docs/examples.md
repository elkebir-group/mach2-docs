# Example Usage

[(back)](tutorial.md)

## MACH2

### Python API

To see example usage for the Python API, please refer to the [Quick Start Guide](quickstart.md)

### Command Line Examples

See the example commands below:

```bash
mach2 
    data/mcpherson_2016/patient1.tree 
    data/mcpherson_2016/patient1.labeling 
    -c data/mcpherson_2016/coloring.txt
```

To constrain the solution space to `LOv` (left ovary):

```bash
mach2 
    data/mcpherson_2016/patient1.tree 
    data/mcpherson_2016/patient1.labeling 
    -c data/mcpherson_2016/coloring.txt
    -t 30
    -p LOV
```

## MACH2-Viz

To see examples for MACH2-Viz, visit the [homepage](https://elkebir-group.github.io/mach2-viz/#/) and click entries in the table.
