
## References

See Scheduled Workflow (SWF) in [IHE Radiology (RAD) Technical Framework - Volume 1 IHE RAD TF-1 Integration Profiles](https://www.ihe.net/uploadedFiles/Documents/Radiology/IHE_RAD_TF_Vol1.pdf). 
Interactions in [IHE Radiology (RAD) Technical Framework - Volume 2 IHE RAD TF-2 Transactions](https://www.ihe.net/uploadedFiles/Documents/Radiology/IHE_RAD_TF_Vol2.pdf) use HL7 v2.3.1 and v2.5.1 (this will be used for mapping to FHIR)

## Actors and Transactions

<figure>
{%include SWF-component.svg%}
<p id="fX.X.X.X-X" class="figureTitle">IHE SWF and SINR Actor Diagram</p>
</figure>
<br clear="all">

### Report Sharing Options

Alternatives to HL7 v2 ORU_R01

> NHS England is currently looking at options for sharing reports via IHE XDS/NRL. This may differ from the options outlined below.

| FHIR Interaction                                                        | Standard                                                                                                                                                                           | Pro                                                                                                                                                                                                                                                                                                                            | Con                                                                                                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Document](https://www.hl7.org/fhir/R4/documents.html)                  | [HL7 Europe Imaging Study Report](https://build.fhir.org/ig/hl7-eu/imaging/branches/initial-version/index.html)                                                                    | Suitable option for Health Document Sharing systems such as IHE XDS/MHDS <br/>Replaces CDA) <br/> Supports both html and structured which gives consuming systems options. <br/> Suitable for cross border sharing.                         | Longer development time <br/> Requires enterprise infrastructure.                                                                                                                                                                                                                                                                            |
| [Message](https://www.hl7.org/fhir/R4/messaging.html)                   | NHS England North West Genomics [Laboratory Results R01](https://interop-nwengland.github.io/LTW-Genomics/LAB-3.html#laboratory-results)                                           | Easy transform from/to HL7 v2 ORU_R01 (near 1to1 mapping and so backwards compatible) <br/> Easier for modern application to support.<br/> Suitable for use with Enterprise Service Bus (ESB)/Trust Integration Engines (TIE) <br/> Can be used a base to introduce [FHIR Workflow](https://www.hl7.org/fhir/R4/workflow.html) | Messages can be long and require collaboration to define payloads. <br/>                                                                                                                                                                                                                                                                     |                                                                                            |
| [RESTful search and read](https://www.hl7.org/fhir/R4/http.html#search) | [IHE Radiology Technical Framework Supplement - Imaging Diagnostic Report (IDR)](https://www.ihe.net/uploadedFiles/Documents/Radiology/IHE_RAD_Suppl_IDR_Rev1-0_PC_2024-05-09.pdf) | Most common way of implementing FHIR. <br/> Suitable for local/regional data sharing.                                                                                                                                                                                                                                          | IHE IDR is draft and leaning towards the same use case as EU Laboratory Report. <br/> NHS England North West Genomics [DiagnosticReport](https://interop-nwengland.github.io/LTW-Genomics/StructureDefinition-DiagnosticReport.html) has been influenced by Royal College of Radiologists existing HL7 guidance and so may be more suitable. |


## Model 

Ref : https://pmc.ncbi.nlm.nih.gov/articles/PMC10287854/

<figure>
{%include model-rad.svg%}
<p id="fX.X.X.X-X" class="figureTitle">National Laboratory of Medicine - Proposed FHIR solution for linking annotations, findings, reports, and medical images</p>
</figure>
<br clear="all">
