---
layout: default
title: Lessons Learned
permalink: /lessonslearned/
---

Federal agencies have shared these E-PACS procurement lessons learned:

## Planning
- Identify all stakeholders upfront, to include an Executive Sponsor.
- Designate staff to fill key roles (e.g., architect, engineers, operators, etc.)
- Engage CIO/CISO representatives early. (_Remember: A PACS is an IT System._)
    - For example, work with the IT department to plan for and support certificate validation, which requires internet connectivity to work
- As an IT system, a PACS must complete Certification and Accreditation (C&A) and obtain an Authority to Operate (ATO) before connecting to the network.
- Create, maintain, and share an integrated master schedule that presents project phases, tasks, resources, and dependencies.
- Build the cost of software licensing and system sustainment into your project budget.
- Work with facility engineers to identify constraints specific to your workplace (e.g., mandatory construction requirements). These constraints may limit solution offerings.
- Legacy system hardware (e.g., credential readers) may not support FICAM compliant modes of operation. Review your system hardware capabilities after identifying desired authentication mechanisms to determine if upgrades are necessary. 
- Legacy credentials and non-FICAM compliant modes of operation should be utilized only in a migration strategy, not as the end state.
    - For example, multi-mode credential readers
- Retire and phase out secondary, legacy credentials.
- Use your agency IDMS as the canonical source for all user records in the PACS.
- Some PACS allow access levels to be assigned at time of credential registration. Plan the method of assignment before provisioning/registration. Common methods include:
    - Import credentials and access privileges from a previous system.
    - Automatically provision access privileges during credential issuance.  
    - Manually re-enroll user credentials and assign privileges in the new PACS.
    - Allow users to use a self-service web enrollment process to register their new credential. Allow newly registered credentials to inherit access privileges based on authoritative sources using the principle of least privilege. 
- Understand that PKI is the foundation for high assurance PACS implementations


## Procurements
- Use consistent terms and recommended procurement language within Requirements Documents, Specifications, SOWs, RFIs, RFPs, and RFQs. 
- Leverage agency subject matter experts to review SOWs, RFPs, and RFQs before releasing them for contractors' bids.
- Resolve SOW and PACS compliance issues as soon as they are recognized.
- Have your integrator provide copies of all relevant FIPS 201-2 compliance and functionality testing documentation.
- Specify personnel roles, responsibilities, and training requirements within the SOW (e.g., all E-PACS engineers must be CSEIP certified).
- Language should be consistent and not be conflicting nor contradictory.  
- Ensure qualified professionals and/or subject matter experts (SME) review the design documents before releasing for bid or formal contractor response
    - Consider hiring an SME capability to augment agency staff as a "buyer’s agent" during these activities
- Consider looking for evidence of qualified and or registered personnel certifying the proposed solution (submittals) prior to approval or notice to proceed and not just a CSEIP for field configuration post acquisition
- Do not procure non-compliant PACS technologies (e.g., “Prox” Cards)
- Compliant PACS validate credentials. Credential validation requires internet access.  Ensure the SOW incorporates requirements from the IT department to facilitate this in particular. 
- User records and credential information provisioned into the PACS must be from an authoritative source (not a manual entry of card serial number or FASC-N)
- FICAM mode operation implies using PKI-based “authentication” mechanisms and on-line identity “validation” (revocation status)
- Ensure PACS is configured and maintained in FICAM mode
- Engage CIO/CSO representatives early (PACS is an IT System)
- Legacy credentials and non-FICAM mode operation should be utilized only in a migration strategy and not as the end state
- Avoid acts of “omission” that create non-compliance (non-actions creating a non-compliant condition)
    - PACS acquired from the APL but not correctly enabling FICAM Mode
    - Cable and power calculations not performed for FICAM PACS
    - Application software options not configured for FICAM PACS
    - CIO and CSO representatives not engaged for cooperative implementation (CIO has compliance requirements reporting)



## Operations
- Provision only assured identities sourced from an agency authoritative source into your PACS.
- Provision only valid PIV cards and PIV technology cards you have established local trust for into your PACS.
- For any PIV card that becomes invalid (expired, placed on CRL, etc.), the PACS administrator may wish to disable the credential in the PACS immediately rather than waiting for it to happen automatically through the routine credential validation recheck process.  It is important to disable identity and credential records rather than remove them.  This is critical to enabling investigations should it become necessary later.
- For any identity terminated in the agency authoritative source, implement PACS to automatically disable the identity record in the E-PACS or all PACS.
- To protect privacy, remove all PII from PACS endpoints.
- Work with your IT Department to ensure your PACS can perform online certificate validation.
- If your PACS is limited to offline certificate validation, manually load CRLs into the PACS daily.  PDVAL operations can be similarly accomplished in offline environments by creating daily trust lists comprised of all roots in all chains necessary to authenticate any credential in the PACS credential store.  With the trust list created, load it into the appropriate trust store on the PACS’ validation server.
- Ensure a PACS is configured and maintained to operate in FICAM mode. FICAM mode implies using PKI-based authentication mechanisms and online identity validation.
- Work closely with legal to define a SOW that contains unambiguous responsibilities for the integrator and appropriate cures for non-performance.
- Consider hiring a third-party SME after installation to ensure the system implemented is compliant with the SOW.  Minimally the agency should verify that the correct number of factors are being challenged for at all places new readers were installed or configured.  Consider using test credentials which have expired or been revoked to further ensure correct operation.
- Other common issues that impact compliant PACS: The validation server is not going out to the internet; the PIV cards are not being electronically validated or the card serial number is being used for PACS card number.

## Training
- Train all agency stakeholders (e.g., HR, IT, Security) to use the E-PACS correctly for their roles.
- Fully document training plan and requirements.
- Training plan should include requirements broken out by end user categories, who writes the user guides, who provides training, and where (remote or on-site) training occurs.

The next section, [Standards, Policies, and Guidance]({{site.baseurl}}/standards/) lists relevant public law, policies, regulations, standards, guidance, and publications relevant to PACS/E-PACS.