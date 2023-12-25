# Input Files

[(Back)](../tutorial.md)

## Tree File

MACH2 requires a file describing the input clonal phylogeny. This is in the form of an edgelist describing a tree (this means that there must not be multiple components or cycles in the edgelist). This is in a tsv formatted file with two columns. Entries are separated by spaces. See the example below:

```text
A A1
A A2
A A3
A A4
A A5
A A6
B B1
B B2
B B3
B B4
B B5
D D1
F F1
H H1
H H2
A B
A D
B C1
D F
D E1
F H
F G1
H I1
```
*(McPherson 2016)*

## Labeling File

## Coloring File