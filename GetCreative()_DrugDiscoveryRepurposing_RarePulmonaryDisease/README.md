# README

## CDC get_creative() Drug Discovery/Repurposing Working: Rare Pulmonary Disease

This folder is intended to suppport development of a Translator Clinical Data Committee (TCDC) drug discovery/repurposing get_creative() workflow, or a minimum set of SME-informed, curated, TRAPI queries.

TCDC partnered originally with Team ARAX to execute this workflow as a TCDC get_creative() 'ARA'. Specifically, the initial plan was for Team ARAX to standup an 'ARA' endpoint to support the workflow. This would have allowe the TCDC 'ARA' endpont to respond to ARS get_creative() MVP1 TRAPI queries during the SME - UI relay sessions at the SEP2022 relay meeting. The intent was to structure the queries as a high-level ‘templated’ question: 'using whatever creative means necessary, find me drugs that may treat disease X' or 'what drugs may treat disease X?’.

However, after the SEP2022 relay meeting, the TCDC and the SRI team discussed whether it makes sense for the TCDC to stand up their own skeletal Curated ARA (CARA) and for this effort to move under the umbrella of the SRI for development and long-term maintenance, potentially serving as an exemplar for other committees/WGs/teams to stand up their own specialized get_creative() 'ARA' to execute curated, SME-informed workflows. The decision was made to move forward with the TCDC CARA. See [issue #10](https://github.com/NCATSTranslator/Clinical-Data-Committee-Tracking-Voting/issues/17) for details. Jason R. is leading the development of the TCDC CARA.


For the initial CDC get_creative() workflow, disease X = rare pulmonary disease.

### Rare Pulmonary Diseases

The relevant CURIES for which the CDC workflow should be able to respond to include the following:

- primary ciliary dyskinesia (MONDO:0016575)
- cystic fibrosis (MONDO:0009061)
- idiopathic bronchiectasis (MONDO:0018956)
- lymphangioleiomyomatosis (MONDO:0011705)
- idiopathic pulmonary fibrosis (MONDO:0008345)

### SMEs

- Dr. Michael Knowles, UNC Chapel Hill
- Dr. Margaret Leigh, UNC Chapel Hill

### Overall Structure

The current workflow is comprised of three main paths, as depicted at a high level in the image below and described in greater detail under directories Path_A, Path_B, and Path_C.

Note that the RWE predicate has been replaced with the following predicates:

    associated_with
    
      associated_with_increased(decreased)_likelihood_of

      correlated_with

        positively_correlated_with

        negatively_correlated_with


![image](https://user-images.githubusercontent.com/26254388/189464364-3d6824ce-7ee2-4d0e-9128-3d6c06588f5e.png)


