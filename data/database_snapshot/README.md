# Magnetic Ordering Database Snapshot

The canonical repository for Materials Project calculations is on the [Materials Project website](https://materialsproject.org) and is accessible via a REST API. The easiest way to use the REST API is via the `MPRester` in [`pymatgen`](https://pymatgen.org).

For convenience and for the historical record, a static data dump is also provided here. This data dump is generated from the magnetic orderings workflow in [`atomate`](https://atomate.org) and is a copy of the generated `magnetic_orderings` collection. The file provided here is a snapshot of the database at this point in time. As the database is being expanded, future results will be made available at the Materials Project. This snapshot will not be updated.

The file format is JSON with crystal structures encoded via `pymatgen`. The easiest way to load this data is using the following code snippet, though note this will load the whole dataset in memory:

```
from monty.serialization import loadfn
data = loadfn("magnetic-orderings-database-snapshot.part1.json.gz")  # and the same for part 2
```

This snapshot is split into parts simply due to git's large file limit. If loading the data with a different JSON parser, the `Structure` objects can be reconstructed in Python using pymatgen and `Structure.from_dict()`. Data analysis is usually easier if the snapshot is first loaded into a database that can handle JSON documents, like MongoDB.

If using any of this data please cite:

N. C. Frey, M. K. Horton, J. M. Munro, S. M. Griffin, K. A. Persson, and V. B. Shenoy, https://arxiv.org/abs/2006.01075 1 (2020).

Horton, M. K., Montoya, J. H., Liu, M., & Persson, K. A. (2019). High-throughput prediction of the ground-state collinear magnetic order of inorganic materials using density functional theory. npj Computational Materials, 5(1), 2.

and the [canonical Materials Project citations](https://www.materialsproject.org/citing).

If there are any questions about the data, please email either Nathan Frey or Matt Horton, thank you!
