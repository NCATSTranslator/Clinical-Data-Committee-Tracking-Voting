# README

## Drug Discovery/Repurposing Working: Rare Pulmonary Disease

This folder is intended to suppport development of a ‘drug discovery/repurposing workflow’, or a minimum set of SME-informed, curated, one-hop TRAPI queries chained together as a bona fide workflow.

ARAX will invoke the workflow as a get_creative() operation in response to the high-level ‘templated’ question 'using whatever creative means necessary, find me drugs that may treat disease X' or 'what drugs may treat disease X?’.

For the initial workflow, disease X = rare pulmonary disease.

This effort is related to the TACT priority of ‘ARA Inference / Query Expansion’ and aligned with the priorities of the Operations and Workflow Working Group. It was motivated by a related 'drug target landscape workflow' (see [slides](https://docs.google.com/presentation/d/1I4Ip7BVOhMl5Qt9HFvPnUwXObrNwZnSyp1Ax8pPsXss/edit?usp=sharing), [related spreadsheet](https://docs.google.com/spreadsheets/d/1gpsO6svuLy7AghWwsfwZLbmdJtIc3Kc290F_-dDrdzQ/edit?usp=sharing), and [ticket](https://github.com/NCATSTranslator/Clinical-Data-Committee-Tracking-Voting/issues/9)).

### Rare Pulmonary Diseases

- primary ciliary dyskinesia (MONDO:0016575)
- cystic fibrosis (MONDO:0009061)
- idiopathic bronchiectasis (MONDO:0018956)
- lymphangioleiomyomatosis (MONDO:0011705)
- idiopathic pulmonary fibrosis (MONDO:0008345)

* Related CURIES: disorder of lung (SCTID: 19829001), lower respiratory tract disorder (MONDO:0000270)

### SMEs

- Dr. Michael Knowles, UNC Chapel Hill
- Dr. Margaret Leigh, UNC Chapel Hill
- Dr. Joel Moss, NHLBI

### Original Biological Relevancy Questions

1. mRNA transcript expressed in disease relevant tissues/states?
2. Protein found in literature in the context of disease-related phenotypes?
3. Protein found in literature, directly linked to the disease?
4. Pre-clinical or genetic data linking protein to indication?
5. Drugs for this target in clinical trials for this indication or in real world clinical use?
6. Is the protein a marketed drug target for this indication? If so, is there real world evidence of the drug being used?

### Adapted Biological Relevancy Questions

*Essentially reversed and modified a bit

~*Workflow Path: Option A*~

~1. What drugs are associated with Disease X in the real world?~
~2. Are there marketed drugs for Disease X? Mark and exclude.~
~3. Are there drugs in clinical trials for Disease X? Mark and exclude.~
~4. What are the gene/protein targets of the remaining drugs?~
~6. Is there pre-clinical or genetic data linking the targets to Disease X?~
~7. Is there literature linking the targets to Disease X?~
~8. Is there literature linking the targets to Disease X-related phenotypes?~
~9. Are the targets expressed in disease-relevant tissues?~

*Workflow Path: Option B*

1. What drugs are associated with Disease X in the real world?
2. Are there marketed drugs for Disease X? Mark and exclude.
3. Are there drugs in clinical trials for Disease X? Mark and exclude
4. What are the gene/protein targets of the remaining drugs?
5. Are there other drugs that target those proteins?
6. If so:
- is there pre-clinical or genetic data linking the targets to Disease X?
- is there literature linking the targets to Disease X?
- is there literature linking the targets to Disease X-related phenotypes?
- are the targets expressed in disease-relevant tissues?

~*Workflow Path: Option C*~

~1. What drugs are associated with Disease X in the real world or are known to treat Disease X?~
~2. What are the gene/protein targets of those drugs?~
~3. What tissues are those genes/proteins expressed in?~
~4. What diseases are associated with those tissues?~
~- Additional evidence from literature, etc.~

~*Workflow Path: Option D*~

~1. What drugs are associated with Disease X in the real world or are known to treat Disease X?~
~2. What genes are regulated by those drugs?~
~3. What drugs regulate those genes in the same way?~
~- Additional evidence from literature, etc.~

~*Workflow Path: Option E*~

~1. What tissues are related to Disease X?~
~2. What genes are expressed in those tissues?~
~3. What drugs target those genes?~
~- Additional evidence from literature, etc.~
