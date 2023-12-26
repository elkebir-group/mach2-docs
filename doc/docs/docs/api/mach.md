<!-- markdownlint-disable MD007 -->
<!-- markdownlint-disable MD024 -->
<!-- markdownlint-disable MD036 -->

# `mach2.MACH`

[(back)](../../tutorial.md)

Solver object for MACH2

## Class Constructor

```py
mach2.MACH(
    phylogeny,
    primary_site=None,
    suboptimal_mode=False,
    seeding_site=False,
    specify_migration_comigration=None,
    possible_migration_list=None,
    clones_observed=None)
```

### Parameters

- `phylogeny (Phylogeny)`: The tree with unlabeled internal nodes

#### Optional

- `primary_site (str)`: The anatomical location of the primary site.
- `suboptimal_mode (bool)`: Return suboptimal solutions as well.
- `seeding_site (bool)`: **TODO**
- `specify_migration_comigration (TODO)`: **TODO**
- `possible_migration_list (list)`: Array of length-2 arrays containing strings representing anatomical locations. Constrains possible migrations in solution space.
- `clones_observed (TODO)`: **TODO**

## Methods

### `add_polytomy_resolution_compatibility_constraints()`

Updates the constraints for polytomy resolution.

### `add_constraints_for_z()`

**TODO**

### `add_constraints_for_z_b_R_suboptimal()`

**TODO**

### `add_constraints_for_q()`

**TODO**

### `add_constraints_for_q_suboptimal()`

**TODO**

### `add_constraints_binary()`

**TODO**

### `add_primary_site_constraints(primary_site)`

Dynamically the constraint on primary tumor location.

#### Parameters

- `primary_site (str)`: Location of the primary tumor

### `add_contraints_specifying_mig_comig()`

**TODO**

### `solve(solver, nSolutions, logfile='', n_threads=0, raw=False)`

Solves the Parsimonious Migration History problem with Tree Resolution (PMH-TR) given the conditions specified in the class parameters.

#### Parameters

- `solver (str)`: ILP solver to use. *We currently only support Gurobi (`"gurobi"`), and hope to add support for more ILP solvers in the future.*
- `nSolutions (int)`: The number of solutions returned by MACH2
- `n_threads (int)`: Number of threads to run in parallel.
- `raw (bool/object)`: Raw data describing the solution set. If the user just needs to cast the solution data, then raw data can be passed in without necessarily running MACH2
