# From Gene Mutation to Disease: BRCA1 and Hereditary Breast/Ovarian Cancer

## Project Information

| Item | Details |
|---|---|
| Name | Ferrer, Mary Rose V. |
| Subject | BIO 300 – Cell and Molecular Biology |
| Section | B |
| Instructor | Sir Abner A. Bucol |
| Disease | Hereditary Breast and Ovarian Cancer (HBOC) |
| Gene | BRCA1 (chromosome 17q21) |
| Reference transcript / CDS | NM_007294.4 (CDS, 5,592 nt) |
| Reference protein | NP_009225.1 (1,863 aa) |
| Documented variant | NM_007294.4(BRCA1):c.68_69delAG (p.Glu23ValfsTer17), frameshift |
| ClinVar accession | Variation ID 17662 |
| Galaxy history | Ferrer_HBOC_BRCA1_Mutation_Lab |
| Date of analysis | September 18, 2026 |

## Summary

The wild-type (WT) BRCA1 CDS was translated in Galaxy to give a predicted protein sequence identical to NP_009225.1. Two edited copies of the CDS were then translated and aligned to the WT with EMBOSS needle (gap open 10.0, gap extend 0.5):

| Sequence | CDS length | Predicted protein length | Mutation type | Frame changed | Premature stop | needle identity |
|---|---|---|---|---|---|---|
| WT | 5,592 nt | 1,863 aa | n/a | n/a | n/a | n/a |
| c.68_69delAG (documented) | 5,590 nt | 38 aa | Frameshift | Yes | Yes (position 39) | 22/1,863 (identical region only; full-length identity not meaningful post-truncation) |
| Artificial 1-nt deletion (position 500, codon ~167) | 5,591 nt | 232 aa | Frameshift | Yes | Yes (position 233) | 166/1,863 (identical region only; full-length identity not meaningful post-truncation) |

The documented mutation removes 2 nucleotides near the start of the coding sequence, shifting the reading frame almost immediately and truncating the predicted protein to 38 amino acids. The artificial deletion shifts the frame further downstream, truncating the predicted protein to 232 amino acids instead. Both are frameshift deletions with no clean in-frame indel. All protein sequences here are predicted from translation; expression and function were not tested.

## Workflow

1. Retrieved the WT BRCA1 CDS (NM_007294.4) from NCBI RefSeq using the "Send to → Coding Sequences" option.
2. Uploaded it to a new Galaxy history and translated it with EMBOSS transeq; checked the result against NP_009225.1.
3. Copied the WT CDS and manually deleted nucleotides 68–69 (AG) to reproduce the documented c.68_69delAG mutation, then translated it.
4. Copied the WT CDS again and deleted one nucleotide at position 500 as the artificial mutation, then translated it.
5. Because transeq continues translating past the first stop codon, each mutant translation was manually trimmed to its first stop codon before alignment, reflecting the true biological protein length.
6. Aligned each trimmed mutant predicted protein sequence to the WT with EMBOSS needle.
7. Wrote the interpretation and final report.

The original WT files were never modified; every edit was made on a copy.

## References

- NCBI RefSeq: NM_007294.4, NP_009225.1
- ClinVar Variation ID 17662: NM_007294.4(BRCA1):c.68_69delAG (p.Glu23ValfsTer17)
- Struewing JP, Abeliovich D, Peretz T, et al. The carrier frequency of the BRCA1 185delAG mutation is approximately 1 percent in Ashkenazi Jewish individuals. *Nat Genet*. 1995;11(2):198–200.
- Wu J, Lu W, Liu X, et al. BRCA1 and Breast Cancer: Molecular Mechanisms and Therapeutic Strategies. *Front Cell Dev Biol*. 2022;10:813457.
