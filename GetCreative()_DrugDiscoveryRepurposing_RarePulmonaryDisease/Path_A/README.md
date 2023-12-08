## Path A

This path of the CQS MVP1 workflow is intended to first identify biolink:ChemicalEntity associated with a biolink:Disease input CURIE for a rare pulmonary disease and targeting the clinical KPs (COHD, icees-kg, Multiomics EHR Risk Provider), then identify genes affected by those chemical entities, and finally identify new chemical entities that are not in the first set of chemical entities but that affect the same gene set and are related to the input CURIE.

The Path A TRAPI query was re-engineered by Abrar M. and Max W. in October 2023 to remove dependencies on sequential fill operations (fill->bind->complete_results) and reduce the complexity such that the query relies on only a lookup operation (lookup->bind->complete_results) with an allowlist parameter specified on e0 to target the clinical KPs. The re-engineered Path A TRAPI query runs successfully when using the following input CURIES: Asthma: MONDO:0004979; CF: MONDO:0009061; and EDS: MONDO:0020066.

The query has since been refined to (1) improve the quality of answers and (2) constrain the responses to each hop via allowlist parameters. In addition, timeout issues will be addressed by caching responses to the full workflow in ARAGORN. The complete list of input CURIEs for testing is:

    asthma (MONDO:0004979)
    primary ciliary dyskinesia (MONDO:0016575)
    cystic fibrosis (MONDO:0009061)
    idiopathic bronchiectasis (MONDO:0018956)
    lymphangioleiomyomatosis (MONDO:0011705)
    idiopathic pulmonary fibrosis (MONDO:0008345)
    EDS: (MONDO:0020066)

   **CURIEs that are starred will be prioritized*


## Path A variations - DEPRECATED, 10.17.2023

### Path_A_no_overlay_chem_+reg_gene.json

[ARAX results](https://arax.ncats.io/?r=63042)

[ARAX results Feb 2023](https://arax.ncats.io/?r=127997)

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
![image](https://user-images.githubusercontent.com/7217210/216733867-3636deac-03ec-48e0-ae82-ef00276c8025.png)
 
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
![image](https://user-images.githubusercontent.com/7217210/216733996-904da776-954f-4bf6-b74b-4c2407d4065d.png)


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
