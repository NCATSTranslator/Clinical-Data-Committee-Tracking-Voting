## Path_A_no_overlay_chem_+reg_gene.json

[ARAX results](https://arax.ncats.io/?r=63042)

This workflow builds off of Casey's original workflow that does not use the overlay operations.
Changes from the original:
* For edge `e2`, the subject and object nodes have been swapped such that the `Gene/Protein` is the object and the `Chemical` is the subject
* A link between the `Gene/Protein` and the `Disease` has been added - this may not be crucial for cystic fibrosis since the CFTR gene is so prominent, but I think it will be important as we experiment with other diseases.
  * predicates used to link the gene/protein to the disease include:
    * biolink:contributes_to
    * biolink:associated_with
    * biolink:gene_associated_with_condition
* The relationships between the chemical nodes (`n1` & `n3`) and the gene/protein are matched so that they are both some form of positive regulation, thus constraining the repurposed chemical (`n3`) to influence the gene in the same way as the known chemical (`n1`). 
  * predicates used to indicate positive regulation include:
    * biolink:increases_activity_of
    * biolink:increases_expression_of
    * biolink:increases_abundance_of
    * biolink:decreases_metabolic_processing_of
    * biolink:increases_secretion_of
    * biolink:increases_transport_of
    * biolink:entity_positively_regulates_entity

## Path_A_no_overlay_chem_-reg_gene.json

[ARAX results](https://arax.ncats.io/?r=63044)

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
