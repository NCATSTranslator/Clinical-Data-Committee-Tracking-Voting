## Path C

This path of the CDC get_creative() workflow is essentially equivalent to Workflow B of the December 2021 demo. In sum, the workflow seeks biolink:DiseaseOrPhenotypicFeature related to an input CURIE for a biolink:DiseaseOrPhenotypicFeature rare pulmonary disease by way of biolink:has_real_world_evidence_of_association_with, then searches for biolink:Gene related to those diseases or phenotypic features, and finally seeks biolink:ChemicalEntity related to those genes.

### Path C Variations

Thus far, none of the Path C variations that were tested yielded promising results. In fact, most of the answer sets were very non-specific. Potential reasons why include the following:

1.  Path C workflow was promising for DILI but does not appear promising for CF

- DILI has a known treatment (i.e., xstop causal agent) but symptoms often persist and/or worsen; largely limited to liver; no definitive genes

- CF has a known treatment, but not for 10% of patients; affects numerous organ systems, but lung of primary importance; known gene

2. Path C seeks drugs to repurpose for treating phenotypes (symptoms) associated with disease, e.g., DILI; Paths A & B, which seem more promising, seek drugs to repurpose for treating the cause of disease, e.g., CF

**Example results:**

Path_C_TRAPI_QUERY_TextMiner_IsSet.json

https://arax.ncats.io/?r=63243

Path_C_TRAPI_Query_ARAX.json

https://arax.ncats.io/?r=56513 (from 8/17/2022 with NGD and Fishers)

Path_C_TRAPI_Query_WithFishers-e02-e03_NGD_IsSet.json

https://arax.ncats.io/?r=63425

Path_C_TRAPI_Query_withFishersNGD_IsSet.json

https://arax.ncats.io/?r=63649
