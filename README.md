# HMatch 

HMatch is a hybrid approach which combines statistical and symbolic methods for entity matching. Two directions have been investigated:
- Direction 1: Extraction of link keys (axioms for entity matching resulting from Linkex (symbolic approach)) deploying a sampling method for the original datasets that is guided by the links generated by a statistical method.
- Direction 2: Selecting a set of high quality link keys which describes the links given by a statistical method.

# Dataset Description

This repository contains the original DB15PK multi-lingual datasets and the sampled datasets which are derived from them.
The original datasets are four: French (fr), English (en), Chinese (zh) and Japanese (ja).

The refined datasets, refinedXXX, presented here are sampled from the original datasets using various statistical methods such as BERT, and TransEdge.

# Settings
For DB15PK KGs the alignments whose value of confidence exceeds 0.99 are used for sampling. 

# Running
Direction 1:

- Step 1: Sampling of the datasets using sampling.py passing as arguments the path to the source KG, the path to the target KG, the path to the identity links, the path to the sampled source KG, the path to the sampled target KG.
- Step 2: Launching Linkex on the sampled KGs https://gitlab.inria.fr/moex/linkex.
  
Direction 2:
- Step 1: linkex is an alias, in bash you have to write first : alias  linkex='java -mx12G -jar  /PATH/TO/LINKEX//LinkkeyDiscovery-1.0-SNAPSHOT-jar-with-dependencies.jar'.
- Step 2:   linkex  -t in -f testselect -e path/to/identitylinks path/to/sampledSourceKG path/to/sampledTargetKG
