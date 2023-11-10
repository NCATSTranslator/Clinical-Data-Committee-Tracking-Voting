## README

## MVP2 Path A

The purpose of the proposed MVP2 Path A workflow query is to leverage causal activity models (CAMs) as a source of mechanistic insights to explain clinical observations. The basic idea is to create one or more two-hop MVP2 queries, with the first hop asking for clinical observations from the clinical KPs (icees-kg, cohd, multiomics-ehr-risk-kp) and the second hop asking cam-kp for biological mechanisms to explain those observations. The demonstration query asks for chemical entities associated with disease diagnoses in the real world and then asks for genes or gene products that are affected by those chemicals.
