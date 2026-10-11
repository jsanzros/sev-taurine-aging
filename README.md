# Taurine transport contributes to the rescue of brain function by extracellular vesicles in aging

Bulk RNA-seq analysis code for the paper. Each notebook is a self-contained tool that runs in Google Colab
or any Jupyter environment on any dataset of the same kind: set the inputs in its settings cell and run it
top to bottom. Analysis parameters (filters, thresholds, gene sets, permutations) default to the values
used in the paper; the experimental design (samples, conditions, covariates and contrasts) is set in the
settings cell. In the paper, differential expression used `~ condition`; the aging signature was the aged
versus young contrast, and the youthful score of each treated group was computed against the aged
group. Each notebook installs what it needs and prints the library versions it ran with. For a local
environment with the tested versions: `pip install -r requirements.txt`.

## Notebooks

| Notebook | What it does | Input |
|---|---|---|
| `salmon_quantification.ipynb` | Salmon index of the Ensembl mouse transcriptome, per-sample quantification, gene-level count matrix | Trimmed FASTQ files |
| `bulk_rnaseq_analysis.ipynb` | DESeq2, preranked GSEA of GO Biological Process 2023, fold change against gene length, youthful score of a treatment against an aging signature with an exact permutation null | Gene count matrix and sample sheet |
| `cell_type_deconvolution.ipynb` | Deconvolution against the Allen Brain Cell Atlas whole-mouse-brain taxonomy (NNLS, nu-SVR cross-check), cell-type fractions and group tests, OXPHOS content of each cell type | Gene count matrix and sample sheet |

## Figure panels

| Figure | Panels | Notebook |
|---|---|---|
| Fig. 6 | B (fold change by gene length) | `bulk_rnaseq_analysis` |
| Fig. 6 | C, D (youthful score and permutation null) | `bulk_rnaseq_analysis` |
| Fig. 6 | E (GSEA) | `bulk_rnaseq_analysis` |
| Fig. S4 | A-C (cell-type deconvolution) | `cell_type_deconvolution` |

## Data

`data/GSE338230.md` describes the gene-level count matrix deposited in GEO (GSE338230), the input of
`bulk_rnaseq_analysis`. The raw reads are in the same GEO series.
`data/allen_brain_cell_atlas.md` describes the Allen Brain Cell Atlas reference used by `cell_type_deconvolution`.

## License

MIT; see `LICENSE`.
