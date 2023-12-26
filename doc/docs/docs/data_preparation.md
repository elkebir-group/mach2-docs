<!-- markdownlint-disable MD029 -->

# Preparing Data for MACH2-Viz

[(Back)](../tutorial.md)

In this page, we describe how to generate inputs for MACH2-Viz, how to open inputs in the visualizer, and lastly, the description of the inputs.

## Creating Inputs for Viz

Inputs for MACH2-Viz can be created using the following methods. The method used is dependent on the needs of the user.

- Create a solution object in the MACH2 API as described in the [quick start guide](../quickstart.md), and then open a localhost visualizer for the data.
- Export MACH2 to JSON, either via commandline or via the API, then upload it to MACH2-Viz
- Run [MACHINA (2018)](https://github.com/raphael-group/machina), and use the [json compression application](https://github.com/vikramr2/json_compression) to convert it into an input that is compatible with MACH2-Viz

### Directly from MACH2 API

This method is used if you would rather run MACH2-Viz in localhost, and would not like to use MACH2 via command line to compute solutions. You can open MACH2-Viz directly from the API using the following steps:

1. Follow the instructions described in the [API tutorial](python_mach2.md)
2. Once you have a `SolutionSet` object, `solutions`, run `solutions.open_in_viz()`

### Generating a JSON

This method is better if you would rather run MACH2 in commandline, or you would like to refrain from running in localhost.

1. Follow the instructions for [running MACH2 in commandline](cmdline.md)
2. Once you have a JSON file generated, navigate to the [Viz homepage](https://elkebir-group.github.io/mach2-viz/#/)
3. Click the `+` on the bottom right, and upload your JSON, the visualizer window will open.

### From MACHINA

This method is preferred if you have solutions generated from MACHINA, and you do not have the JSON formatting that is automatically done with MACH2. To generate inputs for MACH2-Viz using MACHINA outputs, do the following:

1. Run MACHINA to generate outputs.
2. In a command line, navigate to a preferred directory and run the following commands. Replace `<MACHINA output directory>` with the folder name of the MACHINA output.

```bash
git clone https://github.com/vikramr2/json_compression.git
cd json_compression && ./install.sh
./run.sh <MACHINA output directory>
```

You should then have a JSON that is compatible with MACH2-Viz. Then, open the home page of MACH2-Viz and upload the file.

## General format

JSON uploaded to MACH2-Viz has the following general format:

```json
{
    "name": "example",
    "original": [
        {
            "name": "", // (1)
            "tree": [
                ["5", "8"],
                // (2)
            ],
            "labeling": [
                ["8", "breast"],
                // (3)
            ],
            "solution_names": [
                "soln_name1",
                // (4)
            ]
        }
    ],
    "solutions": [
        {
            "name": "soln_name1",
            "tree": [
                [
                    "u",
                    "v",
                    2 // (5)
                ],
                [
                    "v",
                    "w" // (6)
                ]
                // ...
            ],
            "labeling": [
                ["u", "u_label"],
                ["v", "v_label"],
                // ...
            ],
            "migration": [
                [
                    "u_label",
                    "v_label"
                    2 // (7)
                ],
            ]
        },
        // ...
    ],
    "summary": [
        [
            "u_label",
            "v_label",
            3 // (8)
        ]
    ]
}
```

1. Naming can be arbitrary. Just make sure it's relevant to the dataset (perhaps mentioning the type of cancer or the patient ID)
2. This is the edgelist of the input clone tree
3. This is a per-clone assignment of anatomical locations. The only requirement for input trees is that the leaves must be labeled.
4. The corresponding solution names to this input tree
5. Optionally, output trees can be temporally labeled with integer timestamps. See the following [API method](https://elkebir-group.github.io/mach2-docs/docs/api/refinedphylogeny/#infer_timestamps) for labeling timestamps in the solution.
6. Timestamps however aren't necessary to be loaded into MACH2-Viz. MACH2-Viz currently doesn't support visualizing temporality of metastasis, but we hope to add support for it soon.
7. Timestamps can optionally be specified for migration graphs.
8. This weight is marked by the number of occurences of this migration across the full solution space.

### Required Field Descriptions

MACH2-Viz has support for visualizing many different aspects of the input data, but many of the fields above are optional. The required fields are listed below.

- `"name" (string)`: The name of the patient
- `"solutions" (list)`: The list of solutions. Each solution is an object with the following fields:
  - `"name" (string)`: The name of the solution
  - `"tree" (list)`: The clonal tree topology. This is an edge-list where each node is a string id of a clone.
  - `"labeling" (list)`: This is an array where each element is a pair of two (a 2-array) with the format [node, label]. This is a mapping between the clone id and its anatomical location.
  - `"migration" (list)`: This is the edge-list of the migration graph. Each edge goes from an anatomical site to another anatomical site.
- `"summary" (list)`: This is a weighted edge list. Each edge goes from anatomical site to another anatomical site, and the weightage is the number of solutions this edge appears in.

These are the required parameters for which an input for the MACH2-Viz should have at the minimum. For more in depth visualizations, there are optional parameters that can be included in the dataset.
