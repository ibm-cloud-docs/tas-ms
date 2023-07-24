---

copyright:
  years: 2022
lastupdated: "2023-07-24"

subcollection: tas-ms

keywords: tririga-ms

---

{{site.data.keyword.attribute-definition-list}}

# Single Sign ON
{: #singlesignon}


IBM TRIRIGA on Cloud support Single Sign On (SSO) authentication via SAML 2.0. This is the most common method of authentication to IBM Cloud environments and can be configured after the initial customer environments have been provisioned and considered best practice. In a SAML scenario, the customer is the Identity Provider (IdP) and IBM Cloud is the Service Provider (SP). SAML authentication runs over the internet using HTTPS (Port 443), eliminating the need for a VPN or other special connectivity. IBM Cloud Delivery Services leverages the IBM WebSphere Trust Association Interceptor to enable SAML authentication for TRIRIGA.
The basic steps involved in setting up SAML Authentication with TRIRIGA on Cloud environment are as follows:

1.	Customer initiates the SAML configuration by submitting a case to the IBM Support Community indicating the target environment(s) in which they would like to configure SAML

2.	IBM performs initial SAML configuration on the requested environment and generates a metadata file
3.	Metadata file is sent to the customer

4.	Customer uses metadata file to configure the IdP (metadata contains ACS URL and EntityID)

5.	Customer performs IdP configuration and generates a metadata file

6.	Metadata file is sent back to IBM. Please note:

    o	Customer Metadata must contain the Token Signing Certificate
    o	IdP should be configured to send an outgoing NameID claim in the Assertion (this is the only required value)
    o	NameID should use an AD attribute to match the username field (configured in TRIRIGA)

7.	IBM imports customer metadata and finalizes the target environment configuration

8.	A call between customer and IBM is scheduled to enable the configuration and test user authentication. 30mins - 1 hour is usually sufficient

After the above configuration steps have been completed, user authentication flow will work similar to what is diagrammed below.
