
## Path C

The intent of this path is to take the output biolink:ChemicalEntity from Path A and biolink:Drug, SmallMolecule from Path B and use those CURIES as inputs for a one-hop query that asks for evidence of how these chemical entities / drugs / small molecules are used in the real world: (biolink:ChemicalEntity, Drug, SmallMolecule) - biolink:has_real_world_evidence_of_association_with - (biolink:DiseaseOrPhenotypicFeature).

Note that the expectation is that the output from Path A should return an empty answer set in Path C for those chemical entities that are associated with the input CURIES by way of RWE and thus excluded from the final answer set from Path A; whereas the output from Path B should return insights into how those candidate drugs and small molecules are used in the real world.
