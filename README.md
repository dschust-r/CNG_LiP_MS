# LiP MS on native rod outer membrane samples

This repository contains all files relevant for the data analysis of the publication (doi_here). 

The experimental setup, as well as the LC-MS/MS conditions for the experiment can be found in the methods section and/or on PRIDE (PXD038768). 
Raw files, FASTA files and search results can be found on PRIDE (PXD038768).

The main files relevant to the analysis are: 
  * 221205_C07_CaM_LiP.Rmd
  * 221129_C07_CaM_TC.Rmd
 
 # Aims
 
 The aims of the experiment were to identify conformational changes on the bovine rod cyclic nucleotide-gated channel (CNG) upon addition of calmodulin. 
 
 # Experiment 
 
The experiment was conducted in quadruplicates. 

**LiP-MS:** 
Membrane pellets were produced as mentioned [here](https://www.nature.com/articles/s41594-021-00700-8). They were resuspended in LiP-buffer with 1 mM CaCl2.
Calmodulin was added in increasing concentrations (0, 0.01, 0.1, 0.5, 1, 2, 3 ug) to 50 uL of membrane suspension at 2 ug/uL protein.
The samples were incubated for 10 min at 25°C, followed by an unspecific digest with proteinase K (1 ug) for 5 min at 25°C. 
The digest was quenched by boiling the samples (99°C) for 5 min, then cooling them down and adding sodium deoxycholate to a final % of 5%. 
Disulfide bonds were reduced (5 mM TCEP-HCl) and free cysteines were alkylated (40 mM iodoacetamide). 
The proteins were digested overnight with Lys-C and trypsin and desalted (C18 cleanup) the next day.

**Trypsin controls:**
Trypsin control samples were produced to check for unwanted protein abundance changes. They were treated the same way as the LiP-MS samples, except that instead of proteinase K water was added.

# LC-MS/MS
Samples were reconstituted in 5% ACN, 0.1% FA + iRT peptides (Biognosys). 

**LC:** Easy-nLC 1200 (Thermo Scientific), in-house packed C18 column (40 cm x 0.75 um i.d.; 3 um Dr. Maisch ProntoSIL-200 C18-AQ beads) heated to 50°C. 
Linear gradient was from 3-35% B (A: 0.1% FA, B: 95% ACN, 0.1% FA) over 120 min. 

**MS:** Orbitrap Exploris 480 mass spectrometer (Thermo Scientific). 
DIA method: 41 variable window DIA method (1 m/z overlap) ovr a mass range from 350-1150 m/z. MS1 Orbitrap resolution was set to 120,000, MS2 Obitrap resolution was set to 30,000. Maximum injection time was 264 ms with a normalized AGC target of 200%. 

Pooled samples of all conditions were prepared for library generation. 

# Data processing
Raw data was searched with Spectronaut (v.15), against a contaminant FASTA file (MaxQuant) and the bovine proteome (reviewed and unreviewed entries). 
Single hits were excluded, min peptide length was set to 5 amino acids, imputation was switched off. Protease-specificity for LiP samples was set to semi-specific. Peptides were grouped by their modified sequences for quantification. 
Data was exported from Spectronaut and further analyzed in R.
