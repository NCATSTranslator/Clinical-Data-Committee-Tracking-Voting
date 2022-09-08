## Path C

This path of the CDC get_creative() workflow is essentially equivalent to Workflow B of the December 2021 demo. In sum, the workflow seeks biolink:DiseaseOrPhenotypicFeature related to an input CURIE for a biolink:DiseaseOrPhenotypicFeature rare pulmonary disease by way of biolink:has_real_world_evidence_of_association_with, then searches for biolink:Gene related to those diseases or phenotypic features, and finally seeks biolink:ChemicalEntity related to those genes.

### Path C Variations

Thus far, in the absence of a functional ```overlay_fisher_exact_test operation```, none of the Path C variations that were tested yielded promising results. In fact, most of the answer sets were very non-specific.

**Example results:**

Path_C_TRAPI_QUERY_TextMiner_IsSet.json
https://arax.ncats.io/?r=63243

Path_C_TRAPI_Query_ARAX.json
https://arax.ncats.io/?r=56513
