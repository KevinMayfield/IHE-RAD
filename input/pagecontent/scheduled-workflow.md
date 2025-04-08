
## References

See Scheduled Workflow (SWF) in [IHE Radiology (RAD) Technical Framework - Volume 1 IHE RAD TF-1 Integration Profiles](https://www.ihe.net/uploadedFiles/Documents/Radiology/IHE_RAD_TF_Vol1.pdf). 
Interactions in [IHE Radiology (RAD) Technical Framework - Volume 2 IHE RAD TF-2 Transactions](https://www.ihe.net/uploadedFiles/Documents/Radiology/IHE_RAD_TF_Vol2.pdf) use HL7 v2.3.1 and v2.5.1 (this will be used for mapping to FHIR)

## Actors and Transactions

<figure>
{%include SWF-component.svg%}
<p id="fX.X.X.X-X" class="figureTitle">IHE SWF and SINR Actor Diagram</p>
</figure>
<br clear="all">

Alternative formats to HL7 v2 ORU_R01 include:

- [HL7 Europe Imaging Study Report](https://build.fhir.org/ig/hl7-eu/imaging/branches/initial-version/index.html)
- NHS England North West Genomics have [Laboratory Results](https://interop-nwengland.github.io/LTW-Genomics/LAB-3.html#laboratory-results) which is a one-2-one map of HL7 v2 ORU_R01
