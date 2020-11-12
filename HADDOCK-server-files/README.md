This directory contains the HADDOCK server json files with all parameters and input data to submit the docking runs on the HADDOCK2.4 webserver through the submit_file interface:

	https://wenmr.science.uu.nl/haddock2.4/submit_file
	
Note that because of the chaotic nature of the computations and also the distributed grid of computers used, results might slighty differ from run to run.

Each json file starts with the name of the oligosaccharide docked.
Addition keyword are:

- _ens_: Docking from an ensemble of 5 starting conformation for the oligosaccharide
- _seed_: Different random seed (to check the consistency of the results)



	
