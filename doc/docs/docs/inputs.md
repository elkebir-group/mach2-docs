<!-- markdownlint-disable MD036 -->

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

*(McPherson 2016, Ovarian Cancer)*

## Labeling File

MACH2 also requires a file that labels extant nodes (otherwise known as the leaves) of the phylogenetic tree. This is a two column dataset where elements in the same row are separated by spaces (similar to a tsv). Column 1 is the node id in the phylogeny and Column 2 is the anatomical labeling. See below for an example:

```text
A1 Om
A2 SBwl
A3 LFTB
A4 LOv
A5 ApC
A6 RFTA
B1 Om
B2 SBwl
B3 LFTB
B4 LOv
B5 ApC
C1 SBwl
D1 LOv
E1 ROv
F1 ROv
G1 ROv
H1 ROv
H2 LOv
I1 ROv
```

## (Optional) Coloring File

When running MACH2 from the command line, a coloring file may be used for integer assignments (colors) for anatomical locations. The file looks like the one below. Note how Column 1 contains values from Column 2 of the labelling file.

```text
LOv 1
Adnx 2
ROv 3
ApC 7
Bm 8
Brn 2
Bwl 7
CDSB 5
ClnE 9
LFT 7
LFTC 7
LFTB 9
LPv 7
Om 8
RFTA 4
RPv 4
RUt 5
SBwl 5
```
