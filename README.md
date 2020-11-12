## MODELLING OF the BINDING OF VARIOUS SIALIC ACID-CONTAINING OLIGOSACCHARIDES TO THE NTD DOMAIN OF THE SPIKE PROTEIN OF SARS-COV2


This dataset is related to the following submitted manuscript:

**Cryptic SARS-CoV2-spike-with-sugar interactions revealed by ‘universal-STD’**

Charles J. Buchanan2, Ben Gaunt1, Peter J. Harrison3, Audrey Le Bas3, Aziz Khan2, Andrew M. Giltrap1,2, Philip N. Ward3, Maud Dumoux1, Sergio Daga5, Nicola Picchiotti8,9, Margherita Baldassarri5, Elisa Benetti7, Chiara Fallerini5, Francesca Fava5,6, Annarita Giliberti5, Panagiotis I. Koukos11, Abirami Lakshminarayanan2, Xiaochao Xue2,4, Virgínia Casablancas-Antràs2, Timothy D.W. Claridge2, Alexandre M.J.J Bonvin11, Quentin Sattentau4, Simone Furini7, Marco Gori8,10, Jiangdong Huo1,3, Raymond J. Owens1,3, Alessandra Renieri5,6, GEN-COVID Multicenter Study, James H. Naismith*1,3, Andrew Baldwin*2, Benjamin G. Davis*1,2


1. The Rosalind Franklin Institute, Harwell Science & Innovation Campus, OX11 0FA, UK.
2. Department of Chemistry, University of Oxford, Oxford, OX1 3TA
3. Division of Structural Biology, University of Oxford, The Wellcome Centre for Human Genetics, Headington, Oxford, OX3 7BN, UK.
4. Sir William Dunn School of Pathology, South Parks Road, Oxford, UK.
5. Medical Genetics, University of Siena, Siena, Italy
6. Azienda Ospedaliera Universitaria Senese, Siena, Italy
7. Department of Medical Biotechnologies, University of Siena, Siena, Italy
8. Department of Information Engineering and Mathematics, University of Siena, Italy
9. Department of Mathematics, University of Pavia, Pavia, Italy
10. Université Côte d’Azur, Inria, CNRS, I3S, Maasai
11. Bijvoet Centre for Biomolecular Research, Faculty of Science, Utrecht University, Netherlands.



### Modelling of the N-terminal domain of SARS-CoV-2

We modelled the structure of the N-terminal domain (NTD) on Protein Data Bank (PDB) [1] entry 7c2l [2] since it provided significantly better coverage of the area of interest when compared to the majority of the templates available on the PDB as of July 15th 2020. The models were created with Modeller [3], using the ‘automodel’ protocol without refining the ‘loop’. We generated 10 models and ranked them by their DOPE score [4], selecting the top 5 for ensemble docking.

### Docking

The docking was performedwith version 2.4 of the HADDOCK webserver [5, 6]. The binding site on NTD was defined by comparison with PDB entry 6q06 [7], a complex of MERS-CoV spike protein and 2,3-sialyl-N-acetyl-lactosamine. The binding site could not directly be mapped because of conformational differences between the NTDs of MERS-CoV and SARS-CoV-2, but by inspection a region with similar properties (aromatics, methyl groups and positively charged residues) could be identified. We defined in HADDOCK the sialic acid as ‘active’ and residues 18, 19, 20, 21, 22, 68, 76, 77, 78, 79, 244, 254, 255, 256, 258 and 259 of NTD as ‘passive’, meaning the sialic acid needs to make contact with at least one of the NTD residues but there is no penalty if it doesn’t contact all of them, thus allowing the compound to freely explore the binding pocket. Since only one restraint was used we disabled the random removal of restraints. Following our small molecule docking recommended settings  [7] we skipped the ‘hot’ parts of the semi-flexible simulated annealing protocol (‘initiosteps’ and ‘cool1_steps’ set to 0) and also lowered the starting temperature of the last two substages to 500 and 300K, respectively (‘tadinit2_t’ and ‘tadinit3_t’ to 500 and 300, respectively). Clustering was performed based on ‘RMSD’ with a distance cut-off of 2Å and the scoring function was modified to:

	HADDOCKscore = 1.0*E_vdW+0.1*E_elec+1.0*E_desol+0.1*E_AIR
 
All other settings were kept to their default values.


### Data files in this archive

Docked models are provided for the following systems:

 - SIA
 - SIA-23-GAL-14-BGC
 - SIA-23-GAL-14-BGC-seed (same as previous, but different random seed)
 - SIA-23-GAL-14-BGC-ens (same as 2nd, but using an ensemble of 5 conformations for the oligosaccharide)
 - SIA-26-GAL-14-BGC-ens (using an ensemble of 5 conformations for the oligosaccharide)
 
Each directory contains:

 - complex_XXXw.pdb 						: models corresponding to the final, refined HADDOCK models
 - file.list 							: list of PDB filenames including the HADDOCK score, ranked based on the HADDOCK score)
 - file.nam_clustX and file.list_clustX	: list of PDB filenames belonging to a specific cluster X)
 - clusters_haddock-sorted.stat_best4	: file containing the cluster statistics (HADDOCK score and various energetics terms)
 - structures_haddock-sorted.stat		: file containing the single models statistics (HADDOCK score and various energetics terms)

Self-contained HADDOCK json files allowing to repeat the docking throught the submit_file interface of the HADDOCK2.4 server are provided in the HADDOCK-server-files directory.


### References

	1. http://dx.doi.org/10.1093/nar/28.1.235
	2. http://dx.doi.org/10.1126/science.abc6952
	3. https://doi.org/10.1016/S1357-4310(95)91170-7
	4. https://dx.doi.org/10.1110%2Fps.062416606
	5. https://doi.org/10.1021/ja026939x
	6. https://doi.org/10.1016/j.jmb.2015.09.014
	7. https://doi.org/10.1038/s41594-019-0334-7 
	8. https://doi.org/10.1007/s10822-018-0148-4
