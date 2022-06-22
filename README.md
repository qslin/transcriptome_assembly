<summary>Assemble transcriptome</summary>

Since I need to predict sRNA target sites that might be located on UTRs of genes, transcriptome was re-assembled even though CDS sequences were known.

> sbatch [scripts/transcriptome_assembly/trinity.sh](https://github.com/qslin/flayed_RNA_analysis/blob/master/scripts/transcriptome_assembly/trinity.sh)

> sbatch [scripts/transcriptome_assembly/refine.sh](https://github.com/qslin/flayed_RNA_analysis/blob/master/scripts/transcriptome_assembly/refine.sh)

At this point, a rough CDS file was generated. However, I need transcripts instead of CDS. So another vsearch was done for all transcripts regardless of protein-coding ability.

> sbatch [scripts/transcriptome_assembly/cluster.sh](https://github.com/qslin/flayed_RNA_analysis/blob/master/scripts/transcriptome_assembly/cluster.sh)

Evaluate the transcriptome quality.

> sbatch [scripts/transcriptome_assembly/evaluate.sh](https://github.com/qslin/flayed_RNA_analysis/blob/master/scripts/transcriptome_assembly/evaluate.sh)

Map transcripts to annotated genes.

> sbatch [scripts/transcriptome_assembly/minimap2.sh](https://github.com/qslin/flayed_RNA_analysis/blob/master/scripts/transcriptome_assembly/minimap2.sh)


