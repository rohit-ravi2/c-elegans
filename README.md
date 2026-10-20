# c-elegans

The data foundation for my 2025 *C. elegans* connectome work. I gathered the published wiring diagrams
(White et al. 1986, Witvliet et al. 2021 datasets 1 to 8, Cook et al. 2019), the neuron lineage relatedness
tables and the OpenWorm NeuroML cell models into one layout, merged them, and checked every file move against
a manifest. The merged edge list has 27,727 edges (20,714 chemical, 7,013 electrical) from the eight Witvliet
animals and the Cook hermaphrodite edge list.
The analysis that grew out of it lives in
[c-elegans-multimodal](https://github.com/rohit-ravi2/c-elegans-multimodal).

## What is here

- `phase0.ipynb` scans the raw files, classifies them by content, builds `data/metadata/data_catalog.yml`,
  moves everything into the layout below, and verifies the move (3,226 files verified, 0 missing).
- `data/connectivity/processed/merged_edges.csv`: edges with source, target, type, synapse count and source
  file, and `merged_edges_with_relatedness.csv`, the same edges joined to lineage relatedness.
- `data/connectivity/processed/consensus_connectome_*.csv`: a consensus connectome with 3D soma positions,
  mean chemical and gap-junction weights and an uncertainty column, in full (90,000 neuron pairs) and trimmed
  versions, with and without a functional weight.
- `data/lineage/processed/merged_lineage_table.csv`: 38,781 pairwise lineage relatedness scores.
- `utils/`: the move manifests, inventories and validation reports written by the notebook.

## Layout

```
data/connectivity/raw/        published connectomes and their reader scripts (from OpenWorm c302)
data/connectivity/processed/  merged and consensus edge tables
data/lineage/                 neuron lineage tables (WormAtlas) and the merged relatedness table
data/neuroml/, data/nml/      OpenWorm NeuroML cell and network models
data/metadata/                data catalog and file index
utils/                        manifests and validation reports
```

## Sources

The raw files are published data, included here as I collected them. Please cite the originals:
White et al. 1986 (Phil Trans R Soc B 314:1), Witvliet et al. 2021 (Nature 596:257), Cook et al. 2019
(Nature 571:63), WormAtlas neuron lineage tables, and OpenWorm c302 (https://github.com/openworm/c302).
