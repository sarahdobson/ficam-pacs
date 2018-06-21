---
layout: default
title: Aligning Facility Security Level (FSL) and Authentication
permalink: /alignfslandauth/
---
<_"Aligning Facility Security Level (FSL) and Authentication" is new section title. This section combines "Determine Facility Risk" and "Select Appropriate Authentication Mechanism" from the ACC Playbook v6 (11/2017), per LaChelle's recommendation and new navigation.  Comments are in italics <_comment_> from LaChelle, Rachel Flagg, and Celeste; edits are substantially LaChelle's and Rachel's + a few from Celeste._>

# Aligning Facility Security Level (FSL) and Authentication 

## Determine Facility Risk

The risk to facilities and security areas is driven by the sensitivity of an agency's assets (databases, equipment, and people). To reduce the risk to critical assets, agencies must limit physical access to only those individuals who can prove their identities and demonstrate a valid need for access.

To determine facility risk:

* Identify potential threats to critical assets.
* Determine how likely it is that a particular threat will occur.
* Identify the potential impact if an asset is damaged, destroyed, stolen, or compromised. Examples of impacts could be financial loss or sensitive data loss caused by a security breach.

NIST SP 800-116, _A Recommendation for the Use of PIV Credentials in Physical Access Control (PACS)_ recommends a risk-based approach to managing physical access to Federal Government facilities and assets. This standard also allows you to tailor a PACS implementation to your agency's physical access control policies, practices, and procedures.

In addition, the Department of Homeland Security's (DHS) Interagency Security Committee (ISC) publishes [ISC policies, standards, and best practices](https://www.dhs.gov/isc-policies-standards-best-practices){:target="_blank"} that:

* Establish criteria and define the process for determining a Facility Security Level
* Present a single source of physical security countermeasures for all Federal Government facilities
* Offer guidance for customizing facility countermeasures and integrating new standards and concepts 

## Select Authentication Mechanism

Conduct a risk analysis for each access point (door) to determine how many authentication factors are required. The diagram below outlines the multi-step process for selecting which mechanism to use for authentication.

![Process for selecting authentication mechanism](../img/auth_mech_select.png){:style="width:80%;float:center;"}

**Figure 1. Authentication Mechanism Selection Process**

<_Rachel: Present each step as an action the reader needs to complete. Recommend using the following structure and text to replace the information starting with "1. Asset Risk Assessment" (marked off in bordered area below)._>
* **Step 1 - Assess Risk.** Evaluate the likelihood and effect of losing or compromising each asset within a security area, and document the risk levels (LOW, MODERATE, HIGH) for each asset.
* **Step 2 - Categorize Security Areas.** Assign a risk level to the security area. The risk should be equal to the asset with the highest risk within the area. For example, if you have several assets within the area (including both LOW- and HIGH-risk assets), classify it as a HIGH-risk security area. You can also split the area into separate security areas, each with a different risk categorization.
* **Step 3 - Determine Authentication Factors.** Identify the minimum number of authentication factors required for access. Authentication is based on verifying one, two, or three of the following factors:<br> 
> _Something you have (e.g., a PIV card)_<br>
> _Something you know (e.g., a PIN)_<br>
> _Something you are (e.g., a fingerprint or iris scan)_<br/>
* **Step 4 - Assign Authentication Mechanisms.** Determine the appropriate authentication mechanism(s) based on the number of authentication factors required for the security area.
<_Rachel: Present additional information in following sections about the steps above that the reader needs to complete._>

### Assess Risk

_Add additional information here._

### Categorize Security Areas 

<_Celeste: The FM has been deprecated by the Dept. of the Army. Refer to NIST SP 800-116 only._>
NIST SP 800-116 defines three security area categories:

* **Exclusion (Authentication Factors - 3)**. An area in which uncontrolled movement would permit direct access to a security asset or interest.
* **Limited (Minimum Required Authentication Factors - 2)**. An area close to a security asset or interest.  Uncontrolled movement within a limited area may permit access to the asset.  Escorts and other internal restrictions can prevent access. 
* **Controlled (Minimum Required Authentication Factors - 1)**. An area close to or surrounding a limited or exclusion area.  Entry to a controlled area is restricted to personnel who need access.  Movement of authorized personnel within this area is not necessarily controlled, since entry to the area does not provide immediate access to any security assets or interests.  A controlled area provides administrative control, or safety, or acts as a buffer zone for embedded limited or exclusion areas. 

### Determine Authentication Factors

_Add additional information here._

### Assign Authentication Mechanism

PIV and PIV-I cards are provisioned (encoded) with both identifiers and cryptographic data objects that can be used to support authentication. Identifiers can include a Federal Agency Smart Credential Number (FASC-N) and Global Unique ID (GUID); data objects can be public and private keys or digital certificates.  FIPS 201<!--Should reference FIPS 201-2--> and NIST SP 800-116 list the following electronic authentication methods using the PIV card:

- PKI authentication using the PIV Authentication Certificate (PKI-AUTH)
- PKI authentication using the Card Authentication Certificate (PKI-CAK)
- Authentication using the Symmetric Card Authentication Key (SYM-CAK)
- Unattended authentication using off-card biometric comparisons (BIO)
- Attended authentication using off-card biometric comparisons (BIO-A)
- Either attended or unattended authentication using off-card biometric comparisons (BIO(-A))
- Authentication using on-card biometric comparisons (OCC-AUTH)

FIPS 201 and NIST SP 800-116 exclude automated Card Holder Unique Identifier (CHUID) authentication and visual inspection of the PIV card because they offer little or no authentication assurance for access control.

Table 3 lists the candidate authentication mechanisms for each of the three security area categories.

**Table 3. Candidate Authentication Mechanisms**

| **Category**  | **No. Factors<br>Required** | **Acceptable Factors** | **PIV Mechanism:<br>Contact Interface**  |  **PIV Mechanism:<br>Contactless Interface** |
| :-------- | :------: | :----- | :-----  | :-----     |
| **Controlled**   | 1 | Something you have OR<br>Something you know OR<br>Something you are  |  PKI-CAK<br>SYM-CAK<br>BIO  | PKI-CAK<br> SYM-CAK   |
| **Limited**   | 2 |Something you have AND<br>something you know, OR<br>Something you have AND<br>something you are, OR<br>Something you know AND<br>something you are  | PKI-AUTH,<br>BIO-A,<br> OCC-AUTH  |  |
| **Exclusion**  | 3 | Something you have AND<br>something you know AND<br>something you are | PKI-CAK + BIO(-A),<br>SYM-CAK + BIO(-A)  |   |

When using SYM-CAK, PKI-CAK, and PKI-AUTH authentication mechanisms, certificates should be validated when possible. Verify the certificate against a certificate revocation list (CRL) or online certificate status protocol (OCSP) server, and verify the origin of the certificate through the trust chain of issuing certificate authorities to the root certificate authority, using certificate path validation.

**<_Rachel recommends replacing the following text with the above structure and text (i.e., remove all text below in bordered area._>**
------
**1. Asset Risk Assessment.** Evaluate the likelihood and effect of losing or compromising each asset within a security area and assign a risk of LOW, MODERATE or HIGH. <_LaChelle: This paragraph is an example of slimming down the text. Include link to ISC info for risk assessment_>. 

**2. Security Area Categorization.**  Next, assign to the security area the same risk level as the highest risk asset within the area.  For example, say there are three assets within a designated security area:  a LOW-risk asset, a MODERATE-risk asset, and a HIGH-risk asset.  The security area must be classified as a HIGH-risk security area.  As an alternative, split the security area into separate security areas, or a set of embedded security areas, each with a different risk categorization.<Rachel: _How does this relate to the asset risk assessment? Once they designate something as "low" risk, does that mean they need to establish a controlled environment for that asset? Does "high" equal "exclusion?" (The "step" is about assessing "low or high" but those terms are not used further on in the process. There is something missing here (do you need another step?)_.>

NIST SP 800-116 defines three security area categories:<_Celeste: The FM has been deprecated by the Dept. of the Army. Refer to SP 800-116 only. See http://usacac.army.mil/sites/default/files/misc/doctrine/CDG/fms.html for Army's list of Active FMs._>Exclusion, Limited, and Controlled. The categories distinguish how immediately accessible the security assets (or security interests) are within the security area. (See Table 1.)  

**Table 1.  Security Area Categories**

| **Category** | **Description**  |
| :----------- | :-------------------------------     |
| **Controlled**  |  An area close to or surrounding a limited or exclusion area.  Entry to a controlled area is restricted to personnel who need access.  Movement of authorized personnel within this area is not necessarily controlled, since entry to the area does not provide immediate access to any security assets or interests.  A controlled area provides administrative control, or safety, or acts as a buffer zone for embedded limited or exclusion areas. |  
| **Limited**   | An area close to a security asset or interest.  Uncontrolled movement within a limited area may permit access to the asset.  Escorts and other internal restrictions can prevent access. |  
| **Exclusion**   | An area in which uncontrolled movement would permit direct access to a security asset or interest. |  

You can also define your own categorizations to reflect your particular security needs and/or physical security policies and practices.

**3. Authentication Factor Selection.** Authentication is based on verifying one, two, or three of the following factors:

- Something you have (e.g., a PIV card)
- Something you know (e.g., a PIN)
- Something you are (e.g., a fingerprint or iris scan)

NIST SP 800-116 recommends the minimum number of authentication factors required to access controlled, limited, and exclusion areas. (See Table 2.)

**Table 2. Number of Required Authentication Factors**    

| **Security Area** | **Minimum No. Required<br>Authentication Factors** |
| :----------- | :-------------------------------: |
| **Controlled**  |  1 |  
| **Limited**   | 2 |  
| **Exclusion**   | 3 |  
  

**4. Authentication Mechanism Assignment.**  Once you know how many authentication factors are required for a security area, you can determine the appropriate authentication mechanisms.  NIST SP 800-116 describes available authentication mechanisms and provides guidance on how they can be applied.  But you can choose to deviate from the NIST SP 800-116 recommended authentication mechanisms and select solutions that fit your particular agency’s needs.

<_Rachel suggested removing above text to here._>
------
<_LaChelle: Suggest moving the checklist to be up-front for the agency reader. It can be used to find the supporting information as needed?_>
## What Do I Need in My Site/Agency?

Use the following checklist to guide PACS policy, planning, and technical implementation when you are going to implement an approved, PIV-enabled PACS.

- Consider an agency-wide “enterprise PACS” approach, and designate a chief PACS officer to define agency-specific PACS policies and oversee the implementation of the enterprise PACS solution.
- Review PIV-related Office of Management and Budget and agency policies:&nbsp;&nbsp;OMB M-06-18 and OMB M-11-11. <_LaChelle: Move all of these policies to a separate page for policies and references. Celeste: Standards and Policies identifiers and reference information have been moved to Standards and Policies section._>
- Review PACS standards and guidance:&nbsp;&nbsp;NIST SP 800-116<_800-116-1 is not Final_>; _Federal Identity, Credential, and Access Management (FICAM) Roadmap and Implementation Guidance_; and _PIV in Enterprise Physical Access Control Systems (E-PACS)_. <_LaChelle: Move all of the standards and guidance documents to a separate page for policies and references. Celeste: Standards and Policies identifiers and reference information have been moved to Standards and Policies section._>
<_LaChelle: Update this list to be a checklist?_>
- Review current and new or planned PACS installations. Agency PACS that are currently using non-PIV tokens must be replaced or upgraded to use PIV cards for authentication.
> Current agency PACS based on a PIV CHUID authentication must be upgraded to use the candidate authentication mechanisms.
> New agency PACS must be PIV-enabled, using the candidate authentication mechanisms.<br>
- Implement a common procurement process and purchase approved PACS systems and equipment from the GSA Approved Products List (APL).

## Technical Implementation
<_LaChelle: Update this list to be a checklist?_>
* Decide whether the PACS back-end system should be Cloud-based or local.
* Determine the security area category for each access point.
* Select the authentication mechanism to be used at each access point’s PIV card reader.
* Consider a PACS with external connections to validate PIV digital certificates using an external certificate revocation list or online certificate status protocol services and certificate path validation.
