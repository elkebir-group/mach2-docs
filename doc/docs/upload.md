# Uploading Datasets

If you would like your own JSON output from MACH2 to be included in the homepage of MACH2-Viz, follow the steps below.

## I. Generate a JSON

First, to learn how to generate a JSON dataset to upload to MACH2-Viz, see the following [link](docs/data_preparation.md).

## II. Modify the MACH2-Viz Repository

1. If you haven't already, fork the repository by visiting the following [link](https://github.com/elkebir-group/mach2-viz/fork).
      1. If you have, `git pull` from the `main` branch of MACH2-Viz.
2. `git clone` the forked repository.
3. Navigate to `src/samples/`, create a folder for your dataset, and put your JSON in the folder.
4. In `src/samples/mapping.json`, add an entry for your new dataset:

```json
{
    "name": "name", // (1)
    "dataset": "dataset", // (2)
    "path": "/path/to/your/json" // (3)
}
```

1. You can change this to whatever name you would like.
2. Likewise, this can be renamed to the name of your study.
3. This path is relative to `src/samples/`

## III. Open MACH2-Viz Locally

From the root of MACH2-Viz, simply run the following command:

```bash
npm install && npm start
```

<!-- ## III. Make a Pull Request

Once you are done modifying the repository, submit a [pull request](https://github.com/elkebir-group/mach2-viz/pulls) -->
