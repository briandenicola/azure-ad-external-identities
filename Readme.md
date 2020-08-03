# Overview
Azure AD External Identities with Direct Federation is new feature of Azure AD that allows users from any external SAML2.0 or WS-Fed Identity provider into an Azure AD tenant as guest users.

This repo is a walk though on how to setup Azure AD External Identities with an ADFS environment 

## Limitations 
* The sign in user's domain (somebody@_domain.com_) and authentication URL (https://sts._domain.com_) must match or the authentication URL matches a list of allowed providers such as OKTA
* The external domain has not already been associated with another Azure AD tenant. If it has then Azure AD B2B federation can be utilized instead. 

## Pre-requisties 
* An Azure AD tenant 
* An Azure Subscription which will host the ADFS server. 
    * Could also be an AWS Account or GCP Project
* Ownership of or access to a public DNS domain.  
    * This domain will be used as the Authication URL and will be associated with the ADFS server
    * Will be referenced as _adfsdomain_ in the documentation

## Notes
* This walk through does not go into details on the differents between Azure AD tenants, B2B vs B2C, etc. It assumes a foundational understanding of Azure AD and Azure in general 
* Direct Federation is still in preview and still evolving so is the dcumentation 
* Useful links:
    * https://docs.microsoft.com/en-us/azure/active-directory/b2b/compare-with-b2c#external-identities-scenarios
    * https://docs.microsoft.com/en-us/azure/active-directory/b2b/direct-federation
    * https://docs.microsoft.com/en-us/azure/active-directory/b2b/direct-federation-adfs
    * https://github.com/acmesh-official/acme.sh
    * https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings

# Steps
1. [Create ADFS VM and Intial ADFS Install](./adfs-configuration.md)
2. [Configure ADFS Claims](./adfs-setup.md)
3. [Confiugre Azure AD](./azure-ad-confiugration.md)
4. [Test and Validate](./logon-experience.md)