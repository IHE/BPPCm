## Proposed Scope

Much like BPPC does for XDS community. This Implementation Guide (IG) would do for FHIR community. This IG could be used with MHDS, which already has some of the framework for more specific Consents, but BPPCm would be more complete than what is indicated in MHDS. This IG could also be used for organization use or community use beyond MHD/XDS, which would include use-cases like QEDm, and IPA. This would leverage BasicAudit to record access control decisions and recording of consents.

This IG would

1. Define a set of privacy policies with canonical URI and/or code.
1. Define a set of Consent patterns that are foundational.
1. Define actors for creation/update of Consent, Registry of Consents, Decision actor, and Enforcement actor.


See article - https://healthcaresecprivacy.blogspot.com/2022/05/explaining-fhir-consent-examples.html
and - https://healthcaresecprivacy.blogspot.com/2019/11/fhir-consent-mapped-with-bppc.html

## Use-cases

This section includes explanation of some example scenarios and points at example 
Consent resources for them. 
These example scenarios are provided for educational use only, they are not an 
endorsement of these scenarios. 

### Consent Policy 

some policy URI could be defined for common consent terms. Not clear that these will be detailed enough to use in practice, but would be useful catigorization of policy types.

* Authorize Clinical actors access appropriate for Treatment use-cases of Normal data
* Authorize Clinical actors access appropriate for Treatment use-cases of Normal and Restricted data
* Do NOT authorize Treatment outside the host organization without Break-Glass support
* Do Not authorize Treatment outside the host organization with exception for Break-Glass support
* Patient given explict consent for given PurposeOfUse to a given organization for a given timeframe (e.g. non-treatment)

In each of these cases the provisions of the instance of Consent could further constrain.

### Notice of Privacy Policy

Some realms only require that the patient be given access to the organizations privacy policy. 
In these realms the patient is not given the choice to accept, reject, or change the terms of privacy policy. 
The expectation is that the patient can stop the engagement with the healthcare provider if they don't like the privacy policy (yes, we know this is a fallacy in many situations). 


### Basic signed acknowledgement

This section covers the most basic of privacy consents, that simply records an acknowledgement to a given privacy policy permitting data sharing. 
This is only slightly different than the Notice of Privacy Policy, in that with this example, there is some evidence captured from the ceremony. 
Such as a patient initialing or signing a form indicating they have received the Privacy Policy. 
Similar to the Notice of Privacy Policy, the Patient is not given a choice to reject or change the terms of the privacy policy.
The specific version of privacy policy recorded can also be helpful to know when a given patient needs to be presented with the new version of the privacy policy.

### Change to deny sharing

This section covers the case where a basic permit has been used, but for some reason the authorization is revoked or rejected. 
An example might be where the organization does allow the patient to reject a previously permitted action, and the patient has expressed they want to deny sharing now. 
Another example might be where legal action has happened compelling an organization to revoke the consent.


### Some patient specific provisions

Authorizing or Denying access to:
* who by a given Practitioner, CareTeam, RelatedPerson
* why by a given Purpose Of Event codes 
  * why by a given named Research projects
* data by Confidentiality class (Normal, but not Restricted)
  * data by sensitivity class 
* data by authoried timeframe
* data by authorship (authored by someone in organization XYZ)
* data by identifier (explicit reference)
* when specific period of time data can be accessed


