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

### Original Biological Relevancy Questions

1. mRNA transcript expressed in disease relevant tissues/states?
2. Protein found in literature in the context of disease-related phenotypes?
3. Protein found in literature, directly linked to the disease?
4. Pre-clinical or genetic data linking protein to indication?
5. Drugs for this target in clinical trials for this indication or in real world clinical use?
6. Is the protein a marketed drug target for this indication? If so, is there real world evidence of the drug being used?

### Adapted Biological Relevancy Questions

*Essentially reversed and modified a bit

1. Are there marketed drugs for Disease X? If so, is there real-world evidence for the use of these drugs in the treatment of Disease X?
2. Are there drugs in clinical trials for Disease X? If so, is there real-world evidence for the use of these drugs for any indication?
3. What are the protein targets of the marketed and trial drugs?
4. Is there pre-clinical or genetic data linking the targets to Disease X?
5. Is there literature linking the targets to Disease X?
6. Is there literature linking the targets to Disease X-related phenotypes?
7. Are targets expressed in disease-relevant tissues?
