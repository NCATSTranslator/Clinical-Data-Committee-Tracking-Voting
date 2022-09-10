# README

## CDC get_creative() Drug Discovery/Repurposing Working: Rare Pulmonary Disease

This folder is intended to suppport development of a Clinical Data Committee (CDC) drug discovery/repurposing get_creative() workflow, or a minimum set of SME-informed, curated, TRAPI queries.

The CDC has partnered with Team ARAX to execute this workflow as a CDC get_creative() 'ARA'. Specifically, Team ARAX will standup a'ARA' endpoint to support the workflow during the September 2022 Translator relay meeting. This will allow the CDC ARA to respond to ARS get_creative() TRAPI queries during the SME - UI relay sessions. For the relay meeting these will be structured as a high-level ‘templated’ question: 'using whatever creative means necessary, find me drugs that may treat disease X' or 'what drugs may treat disease X?’.

Post relay meeting, the CDC will discussion with the SRI team on whether it makes sense to move this effort under the umbrella of the SRI for long-term maintenance and to serve as an exemplar for other committees/WGs/teams to stand up their own CDC get_creative() ARA specialized to run curated, SME-informed, specialized workflows


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

![image](https://user-images.githubusercontent.com/26254388/189464364-3d6824ce-7ee2-4d0e-9128-3d6c06588f5e.png)


