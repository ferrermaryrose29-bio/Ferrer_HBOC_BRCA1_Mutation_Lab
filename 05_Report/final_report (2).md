# From Gene Mutation to Disease — BRCA1 and Hereditary Breast/Ovarian Cancer

| | |
|---|---|
| **Name:** Mary Rose V. Ferrer | **Section:** B |
| **Date:** September 18, 2026 | **Activity:** Activity 4 — Gene Mutation to Disease |
| **Instructor:** Mr. Abner A. Bucol | **Subject:** Cell & Molecular Biology |

---

## 1. Disease Background

Hereditary breast and ovarian cancer (HBOC) syndrome is an inherited cancer predisposition condition caused by a pathogenic germline mutation in the BRCA1 (or BRCA2) gene. Carriers of a pathogenic BRCA1 variant have a substantially elevated lifetime risk of developing breast and ovarian cancer compared with the general population, with cumulative breast cancer risk estimated at roughly 80% by age 80, compared with approximately one in eight women in the general population.

BRCA1-associated breast cancers tend to present at an earlier age, are frequently triple-negative, and are generally more aggressive than sporadic breast cancers. Beyond breast and ovarian cancer, BRCA1 mutation carriers also face elevated risk for cancers of the fallopian tube, peritoneum, cervix, endometrium, pancreas, and, in male carriers, prostate cancer.

The tissues primarily affected are the glandular epithelium of the breast and the surface/fallopian tube epithelium of the ovary, tissues that undergo frequent hormone-driven cell division and are therefore particularly dependent on efficient DNA repair to avoid accumulating replication errors.

HBOC follows an autosomal dominant inheritance pattern with incomplete penetrance: inheriting a single pathogenic copy of BRCA1 substantially raises risk, but not every carrier develops cancer, and a "second hit" (somatic loss of the remaining normal allele in a breast or ovarian cell) is generally required for tumor initiation, consistent with the classic two-hit tumor suppressor model.

## 2. Gene and Normal Protein Function

| Item | Detail |
|---|---|
| Official gene symbol | BRCA1 |
| Chromosomal location | 17q21 |
| Gene structure | 24 coding exons spanning approximately 81 kb |
| Encoded protein | A 1,863-amino-acid nuclear phosphoprotein (~220 kDa) |
| Subcellular localization | Nucleus |

BRCA1 is a tumor suppressor gene. Its protein product functions primarily in the repair of DNA double-strand breaks through homologous recombination, and also participates in transcriptional regulation, chromatin remodeling, cell-cycle checkpoint control, and protein ubiquitination (via its N-terminal RING domain, which has E3 ubiquitin ligase activity).

BRCA1 assembles with other DNA damage response proteins into a large complex sometimes referred to as the BRCA1-associated genome surveillance complex (BASC), which coordinates the detection and repair of DNA damage to help maintain genome stability. When this repair pathway is disabled, cells accumulate DNA damage over time; if damage affects genes controlling cell division, uncontrolled proliferation and tumor formation can follow.

## 3. Documented Mutation

| Item | Correct Information |
|---|---|
| Gene | BRCA1 |
| Reference transcript | NM_007294.4 |
| HGVS nucleotide notation | c.68_69delAG (historically 185delAG) |
| HGVS protein notation | p.Glu23ValfsTer17 |
| Location | Exon 2 |
| Nucleotide change | Deletion of 2 nucleotides (AG) at CDS positions 68–69 |
| Mutation type | Frameshift deletion |
| dbSNP | rs80357914 |
| ClinVar Variation ID | 17662 (Pathogenic) |
| OMIM | 113705.0003 |
| Clinical interpretation | Pathogenic; causes autosomal dominant HBOC |

This is a well-characterized founder mutation, carried by approximately 1% of individuals of Ashkenazi Jewish descent, and also documented in other populations. Because 2 nucleotides is not evenly divisible by 3, this deletion shifts the reading frame downstream of codon 23, leading to a premature stop codon shortly afterward. Key references: ClinVar Variation ID 17662; Struewing JP, et al. (1995) *Nature Genetics* 11(2):198–200.

## 4. Hypothesis

| Item | Prediction |
|---|---|
| Mutation and nucleotide change | Deletion of nucleotides 68–69 (AG) from the BRCA1 CDS |
| Number of nucleotides affected | 2 |
| Predicted mutation type | Frameshift (2 is not divisible by 3) |
| Predicted effect on reading frame | Shift beginning at codon 23, altering every downstream codon |
| Predicted effect on protein length | Severe truncation, expected well short of the normal 1,863 amino acids |
| Predicted effect on protein function | Loss of function — truncated protein lacking nearly all downstream functional domains |

## 5. Methods

1. The BRCA1 coding sequence (CDS) was retrieved from NCBI RefSeq (NM_007294.4) using the "Send to → Coding Sequences" FASTA export option, yielding a 5,592-nucleotide sequence matching reference protein NP_009225.1.
2. The WT CDS was uploaded into a Galaxy history (Ferrer_HBOC_BRCA1_Mutation_Lab) and translated using EMBOSS transeq (Frame 1, Standard codon table).
3. A copy of the WT CDS was manually edited in a text editor to reproduce the documented c.68_69delAG deletion by removing nucleotides 68–69 (AG), producing a 5,590-nucleotide mutant CDS. This file was uploaded to Galaxy and translated using the same transeq procedure.
4. Because transeq translates through the entire input sequence in the specified frame rather than terminating at the first stop codon, the mutant translation was manually trimmed to end at the first stop codon (*) encountered, reflecting the true biological length of the protein product.
5. WT and mutant (trimmed) proteins were compared using EMBOSS Needle (global pairwise alignment, EBLOSUM62 matrix, gap open 10.0, gap extend 0.5).
6. A second, self-designed mutation (Part XI) was created by deleting a single nucleotide (C) at CDS position 500, producing a 5,591-nucleotide artificial mutant CDS. This was translated and aligned against WT following the same procedure as above.

## 6. Results — Wild-Type Control

| Item | Value |
|---|---|
| CDS length | 5,592 nt |
| Start codon | ATG |
| Stop codon | TGA |
| Reading frame | Frame 1 |
| Predicted protein length | 1,863 aa |
| First 10 amino acids | MDLSALRVEE |
| Last 10 amino acids | LIPQIPHSHY |
| Reference match | Confirmed identical to NP_009225.1 |

## 7. Results — Documented Mutant (c.68_69delAG)

| Item | Value |
|---|---|
| Mutant CDS length | 5,590 nt |
| Mutant protein length | 38 aa (then premature stop) |
| First amino-acid difference | Position 23 (Glu → Val) |
| Premature stop codon | Position 39 |
| Predicted vs. observed | Matches documented p.Glu23ValfsTer17 exactly |

## 8. Results — Artificial Mutant (c.500delC)

| Item | Value |
|---|---|
| Mutant CDS length | 5,591 nt |
| Mutant protein length | 232 aa (then premature stop) |
| First amino-acid difference | Position 167 (Thr → Lys) |
| Premature stop codon | Position 233 |

## 9. WT versus Mutant Protein Comparison

**Documented mutant (c.68_69delAG) vs. WT:** Pairwise alignment (EMBOSS Needle) confirmed the sequences are identical for the first 22 amino acids. Divergence begins precisely at position 23, consistent with the documented HGVS protein notation p.Glu23ValfsTer17. Only one amino acid (position 23) reflects a direct substitution (Glu→Val); all amino acids from position 24–38 arise from translation of a shifted reading frame and bear no relationship to the corresponding WT residues. No amino acids were cleanly deleted or inserted in-frame — this is a frameshift, not a simple indel. A premature stop codon was produced at position 39. The reading frame changed, and overall protein length dropped from 1,863 to 38 amino acids.

**Artificial mutant (c.500delC) vs. WT:** The sequences are identical through amino acid 166. Divergence begins at position 167 (Thr→Lys), followed by a shifted reading frame that continues for 65 additional residues before encountering a premature stop at position 233.

An initial alignment attempt using the full, untrimmed transeq output for the documented mutant produced a misleading result (~0.2% identity), because EMBOSS transeq continues translating past the first stop codon rather than terminating there, and the resulting long stretch of biologically meaningless "read-through" sequence caused the alignment algorithm to match unrelated regions rather than the true, short N-terminal identity. Re-running the alignment using a protein sequence trimmed at the first stop codon resolved this and produced the clean, biologically meaningful alignments summarized above.

## 10. Artificial Mutation Experiment

For the second, self-designed mutation, a one-nucleotide deletion was chosen: deletion of a single cytosine at CDS position 500 (c.500delC), located further downstream than the documented mutation, within a different exon.

**Prediction (formulated before translation):** Because 1 nucleotide is not divisible by 3, this deletion was predicted to cause a frameshift beginning at approximately codon 167, resulting in a severely truncated, non-functional protein, though the exact truncation point could not be predicted without translation.

**Observed outcome:** The prediction was confirmed. The reading frame shifted starting at codon 167, and a premature stop codon was encountered 66 codons later, at position 233, yielding a 232-amino-acid protein, compared to the documented mutation's 38-amino-acid product.

## 11. Comparing the Documented and Artificial Mutations

| Feature | WT | Documented (c.68_69delAG) | Artificial (c.500delC) |
|---|---|---|---|
| CDS length | 5,592 nt | 5,590 nt | 5,591 nt |
| Protein length | 1,863 aa | 38 aa | 232 aa |
| Mutation type | — | Frameshift deletion | Frameshift deletion |
| First divergence | — | Position 23 | Position 167 |
| Reading frame changed? | — | Yes | Yes |
| Premature stop? | — | Yes (position 39) | Yes (position 233) |

Both mutations are frameshift deletions and both are predicted to abolish protein function, since both truncate the protein well before the BRCT domains and most of the central coiled-coil region required for BRCA1's DNA repair activity. However, the two mutations produce proteins of very different lengths (38 aa vs. 232 aa) despite both being simple, small-scale deletions. This difference arises entirely from where each deletion falls within the coding sequence and how far downstream the new (shifted) reading frame must travel before encountering a stop codon in that frame.

## 12. Molecular Interpretation

Both mutations analyzed in this lab illustrate the same overall mechanism, differing only in where the disruption occurs: a small deletion in the BRCA1 coding sequence removes a number of nucleotides not divisible by three, shifting the triplet reading frame for every codon downstream of the deletion site. Because the genetic code is read in fixed groups of three nucleotides, this shift causes the ribosome to interpret all subsequent nucleotides as entirely different codons than intended, producing a stretch of essentially random, non-functional amino acid sequence until a stop codon is encountered by chance in the new frame.

The result is a truncated protein that lacks most of the C-terminal two-thirds of the normal BRCA1 protein, including the tandem BRCT domains responsible for phosphopeptide recognition during DNA damage signaling, and much of the central region involved in partner-protein interactions within the BRCA1-associated genome surveillance complex. A protein missing these domains cannot participate effectively in homologous recombination repair of DNA double-strand breaks.

At the cellular level, loss of functional BRCA1 impairs a cell's ability to accurately repair double-strand breaks that arise during normal DNA replication or from other sources of damage. Cells increasingly rely on more error-prone repair pathways, accumulating mutations over successive divisions. Because HBOC is inherited in an autosomal dominant pattern, a carrier is born with one non-functional BRCA1 allele in every cell; cancer develops when a somatic "second hit" occurs in an individual breast or ovarian cell, removing the last functional copy of this genome-stability gene in that cell lineage and allowing damaged, unstable cells to proliferate unchecked.

## 13. Limitations

All results in this lab represent predicted protein sequences derived from computational translation of a reference coding sequence. They do not demonstrate that these mutant proteins are actually expressed, stable, or degraded in a human cell; experimental evidence would be required to confirm real-world protein expression and behavior.

Nonsense-mediated mRNA decay (NMD) often degrades transcripts containing a premature stop codon before translation is completed; this lab's manual translation approach does not model NMD, so the truncated proteins predicted here may, in reality, never be substantially produced at all.

An initial technical pitfall was identified during this analysis: EMBOSS transeq does not terminate translation at the first stop codon, instead continuing through the entire input sequence. Using this untrimmed output directly in a pairwise alignment produced a misleading, artificially low identity score. This was corrected by manually trimming each mutant translation to its first stop codon before alignment, reflecting the actual predicted length of protein a ribosome would generate — a direct, concrete illustration of the distinction between raw computational output and biologically meaningful predicted protein sequence.

This analysis used only the canonical BRCA1 transcript (NM_007294.4); alternative splice isoforms were not considered.

## 14. Conclusion

This lab investigated the molecular basis of hereditary breast and ovarian cancer through the lens of a documented pathogenic BRCA1 variant (c.68_69delAG) and a self-designed artificial variant (c.500delC). Both are small frameshift deletions that disrupt the BRCA1 reading frame and lead to severely truncated, presumably non-functional proteins, despite differing considerably in their final truncation length (38 aa vs. 232 aa) due to differences in deletion position. These findings support the broader molecular mechanism by which loss-of-function BRCA1 mutations impair DNA double-strand break repair, permit genomic instability to accumulate, and, combined with a somatic "second hit," contribute to breast and ovarian tumorigenesis.

## 15. References

1. Wu, J., Lu, W., Liu, X., et al. (2022). BRCA1 and Breast Cancer: Molecular Mechanisms and Therapeutic Strategies. *Frontiers in Cell and Developmental Biology*, 10:813457.
2. Struewing, J.P., Abeliovich, D., Peretz, T., et al. (1995). The carrier frequency of the BRCA1 185delAG mutation is approximately 1 percent in Ashkenazi Jewish individuals. *Nature Genetics*, 11(2), 198–200.
3. National Center for Biotechnology Information. BRCA1 DNA repair associated (BRCA1), transcript variant 1, mRNA. RefSeq accession NM_007294.4.
4. ClinVar. BRCA1 c.68_69delAG (p.Glu23ValfsTer17). Variation ID: 17662. National Center for Biotechnology Information.
5. Online Mendelian Inheritance in Man (OMIM). BRCA1, 185DELAG. OMIM #113705.0003.
