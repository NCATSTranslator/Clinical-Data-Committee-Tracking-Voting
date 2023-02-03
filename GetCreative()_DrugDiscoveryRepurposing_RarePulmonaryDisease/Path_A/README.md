## Path A

This path of the CDC get_creative() workflow is intended to first identify biolink:ChemicalEntity associated with a biolink:Disease input CURIE for a rare pulmonary disease by way of biolink:has_real_world_evidence_of_association_with, then identify biolink:Gene associated with those chemical entities, and finally identify new chemical entities that are not in the first set of chemical entities but that act on the same gene set.

## Path A variations

### Path_A_no_overlay_chem_+reg_gene.json

[ARAX results](https://arax.ncats.io/?r=63042)
[ARAX results Feb 2023](https://arax.ncats.io/?r=127993)

The relationships between the chemical nodes (`n1` & `n3`) and the gene/protein are matched so that they are both some form of positive regulation, thus constraining the repurposed chemical (`n3`) to influence the gene in the same way as the known chemical (`n1`). 
  * predicates used to indicate positive regulation include:
    * biolink:increases_activity_of
    * biolink:increases_expression_of
    * biolink:increases_abundance_of
    * biolink:decreases_metabolic_processing_of
    * biolink:increases_secretion_of
    * biolink:increases_transport_of
    * biolink:entity_positively_regulates_entity
    
 **Note that the `exclude=True` parameter is indicated by the red edge in the figure below**
![image](https://user-images.githubusercontent.com/7217210/216713110-4d45f14d-cc28-4d07-8141-f98022d154ff.png)
 
### Path_A_no_overlay_chem_-reg_gene.json

[ARAX results](https://arax.ncats.io/?r=63044)
[ARAX results Feb 2023](https://arax.ncats.io/?r=127999)

This workflow is identical to the `Path_A_no_overlay_chem_+reg_gene.json` workflow, except that the chemical-to-gene relationships have been constrained to some form of negative regulation.

* The relationships between the chemical nodes (`n1` & `n3`) and the gene/protein are matched so that they are both some form of negative regulation, thus constraining the repurposed chemical (`n3`) to influence the gene in the same way as the known chemical (`n1`). 
  * predicates used to indicate negative regulation include:
    * biolink:decreases_activity_of
    * biolink:decreases_expression_of
    * biolink:decreases_abundance_of
    * biolink:increases_metabolic_processing_of
    * biolink:decreases_secretion_of
    * biolink:decreases_transport_of
    * biolink:entity_negatively_regulates_entity
    
 **Note that the `exclude=True` parameter is indicated by the red edge in the figure below**
![image](https://user-images.githubusercontent.com/7217210/216713463-4ff683b9-d1e8-42b2-b894-3ddbb6e28b4b.png)


### (DEPRECATED) Path_A_TRAPI_Query_Affects_NGD_TextMiner

This modification uses biolink:affects instead of the directional affects predicates, uses the same n0-n2 edge Bill added, and overlays NGD between n3 (the answer ChemicalEntity node) and the disease (cystic fibrosis in these examples) to increase relevance of results.

In comparison with previous results, we do get some proposed drugs that would have the opposite of the desired effect (decreases CFTR activity for CF, e.g., crofelmer, bumetanide, etc), but the results also include other drugs where the direction of the effect was not captured, and many of which treat / have been studied for treating CF (ataluren, galicaftor, bamocaftor, cysteamine). Ibuprofen is also used for slowing lung damage in CF patients, but the results propose it for the "wrong" reason (decreasing activity of CFTR)

https://arax.ncats.io/?r=63114

### Path A Comparison Testing

https://docs.google.com/spreadsheets/d/1BqeN6G98bhLSDQkTtiU6qqm8NEVHl6Ngd8-FPIciY2c/edit?usp=sharing

### Path A Proposed Variations

~~1. Using Bill's directed predicates, we can probably filter out any ICEES KG exposures from the first hop by leveraging the fact that these are mapped to both biolink:ChemicalEntity and biolink:EnvironmentalExposure. So, adding an ```exclude edge``` : ```(n0: rare lung disease)-[RWE]->(biolink:EnvironmentalExposure)```.

*FIXED on ICEES KG side*

***Priority**

2. Again using Bill's directed predicates, we can seek chemical entities that might reduce the negative impact of environmental exposures, whether that be inducing disease, accelerating disease progression, or contributing to disease severity. In other words, we can seek ```biolink:EnvironmentalExposures``` in n1 and then seek ```biolink:ChemicalEntity``` in n3 that act in the opposite direction on shared ```biolink:Gene``` in n2. 

***Defer to next get_creative() workflow**
