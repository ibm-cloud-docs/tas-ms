---

copyright:
  years: 2022
lastupdated: "2023-07-24"

subcollection: tas-ms

keywords: tririga-ms

---

{{site.data.keyword.attribute-definition-list}}

# Single Sing ON
{: #singlesignon}


TAS-MS supports Single Sign On (SSO) authentication via SAML 2.0. 
This is the most common method of authentication to IBM Cloud environments and can be configured after the initial customer environments have been provisioned and considered best practice. 
In a SAML scenario, the customer is the Identity Provider (IdP) and IBM Cloud is the Service Provider (SP). SAML authentication runs over the internet using HTTPS (Port 443), eliminating the need for a VPN or other special connectivity. 
IBM Cloud Delivery Services leverages the IBM WebSphere Trust Association Interceptor to enable SAML authentication for TRIRIGA.
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


1.	Browser user follows a link to the target IBM Cloud environment URL
2.	Within IBM WebSphere, SAML TAI redirects user to Customer's IdP and they authenticate.
3.	A signed SAML response is created by Customer's IdP and sent by HTTP post to IBM Cloud
4.	SAML TAI consumes response and logs in the user. An LTPA2 Token is created
5.	Assertion consumer service redirects user to correct landing page within TRIRIGA 

## Multi-factor authentication (MFA) or Two-factor authententication (2FA) Support
{: #mfa2fa}

The TAS-MS offering support multiple forms of SSO, including SAML, which relies on the customers chosen on-premise or cloud based identity provider to authenticate the user. In this flow, the identity provider is responsible for implementing any and all authentication factors required by the customers security policy. The TAS-MS environment does not itself implement MFA/2FA.


See below IBM Knowledge Center links for further requirements and limitations of single sign-on requests for TRIRIGA Application Platform:

https://www.ibm.com/support/knowledgecenter/SSHEB3_3.6.0/com.ibm.tap.doc/sso_topics/c_sso_reqs.html

If you would like to configure any of the above, please submit a case (https://www.ibm.com/mysupport) to the IBM Support Community with your specific environment details to IBM for review.

## Single Sign On (SSO) and OpenID Authentication
{: #singlesignonoid}

### OpenID
{: #singlesignonoidd}

TAS-MS supports OpenID for authentication. This is done by leveraging OpenID Connect (OIDC) capabilities within IBM WebSphere. In this scenario, IBM is the relying party (RP) and the customer is the OpenID Provider (OP).

 For further information, see the following links:

WebSphere specific information:

https://www.ibm.com/support/knowledgecenter/SSAW57_9.0.5/com.ibm.websphere.nd.multiplatform.doc/ae/csec_oiddesc.html 

TRIRIGA specific information:
https://www.ibm.com/support/knowledgecenter/SSHEB3_3.7/com.ibm.tap.doc/sso_topics/m_sso_config_websphere_trad_azu_oidc.html

## OAuth
{: #singlesignonoiddoa}

OpenID Connect (OIDC) is a layer that sits on top of OAuth 2.0 that adds authentication, i.e. login. OAuth 2.0 is designed only for authorization, i.e. for granting access to data and features. The IBM SRE Team only support using these capabilities for authentication at this time, all authorization is still performed within the product via membership to security groups.

