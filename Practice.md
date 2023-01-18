## {{page-title}}

 # Virtual Wards Interop Implementation Guidance

 >UK FHIR CORE Bundle will include Patient Resource and Document Reference Resource.

 ## Summary
 
 
 This implementation guide can be used to deploy a FHIR bundle containing a Patient Resource and Document Reference Resource in UK FHIR Core for a virtual ward solution. The Patient Resource will contain information relating to the patient's demographics for use by the NHS and the Document Reference will contain a link to PDF, containing a Virtual Ward Care Record Summary (End of Stay). 

  ## StructureDefinition-UKCore-Patient


### Definition
Demographics and other administrative information about an individual receiving care or other health-related services. The data in the Resource covers the "who" information about the patient: its attributes are focused on the demographic information necessary to support the administrative, financial and logistic procedures. A Patient record is generally created and maintained by each organization providing care for a patient. A patient or animal receiving care at multiple organizations may therefore have its information present in multiple Patient Resources.

### Minimum Viable Content
A minimum viable content that all provider and consumer systems should support is the following elements.

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Required?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Patient.identifier</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.identifier:nhsNumber</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.active</td>
            <td>x</td>
        </tr>        
        <tr>
            <td>Patient.name</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.telecom</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.gender</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.birthDate</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.deceased[x]</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.address</td>
            <td></td>
        </tr>
        <tr>
        <tr>
            <td>Patient.maritalStatus</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.multipleBirth[x]</td>
            <td></td>
        </tr>        
        <tr>
            <td>Patient.photo</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact</td>
            <td></span></td>
        </tr>
        <tr>
            <td>Patient.contact.relationship</td>
            <td></td>
        </tr>        
        <tr>
            <td>Patient.contact.name</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact.telecom</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact.address</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact.gender</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact.organization</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.contact.period</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.communication</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.communication.language</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.communication.preferred</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.generalPractitioner</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.managingOrganization</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.link</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.link.other</td>
            <td></td>
        </tr>
        <tr>
            <td>Patient.link.type</td>
            <td></td>
        </tr>
    </tbody>
</table>

### identifier

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>identifier</td>
      <td>Optional</td>
      <td>0:*</td>
      </tr>
    </tbody>
</table>

An identifier for this patient.

#### Example
```json
 "id":"44f85d15-8744-47c2-a790-4f5e38aacdb0" 
```

### NHS Number

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>NHS Number</td>
      <td>Optional</td>
      <td>0:1</td>
      </tr>
    </tbody>
</table>

NHS Number for the patient

#### Example
```json
        {
                "id": "Patient.identifier:nhsNumber",
                "path": "Patient.identifier",
                "sliceName": "nhsNumber",
                "short": "The patient's NHS number",
                "max": "1"
            }
```