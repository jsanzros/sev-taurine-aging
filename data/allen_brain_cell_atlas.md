# Allen Brain Cell Atlas reference

Whole-mouse-brain taxonomy of the Allen Brain Cell Atlas (Yao et al., Nature 2023; PMID: 38092916), used by
`notebooks/cell_type_deconvolution.ipynb`. The notebook downloads the files below from the public bucket
`https://allen-brain-cell-atlas.s3.us-west-2.amazonaws.com` on first use.

| File | Size | Content |
|---|---|---|
| `mapmycells/WMB-10X/20240831/precomputed_stats_ABC_revision_230821.h5` | 1.38 GB | Mean log2(CPM + 1) of 32,285 genes in each of the 5,322 clusters (MapMyCells reference) |
| `metadata/WMB-taxonomy/20231215/cluster_to_cluster_annotation_membership.csv` | 2.2 MB | Cluster labels, aliases and cell numbers |
| `metadata/WMB-taxonomy/20231215/views/cluster_to_cluster_annotation_membership_pivoted.csv` | 0.5 MB | Class, subclass and supertype of each cluster |

Clusters are grouped into 22 compartments by class and subclass (function `compartment` in the notebook):
12 neuronal compartments by Allen class (with dentate gyrus and CA/subiculum subclasses kept apart), and
non-neuronal cell types. For Fig. S4 the compartments are summed into eight cell types (`CLASSES`).
