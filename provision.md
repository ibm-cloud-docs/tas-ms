---

copyright:
  years: 2023
lastupdated: "2023-04-19"

subcollection: tas-ms

keywords: tririga-ms

---

{{site.data.keyword.attribute-definition-list}}

# Provisioning
{: #provisioning}

This page describes the provisioning process when a client orders the TRIRIGA Application Suite Managed Services option.

Important:

Customers must purchase (or own) App Points for TAS prior to (or in conjunction with) ordering the IBM Managed Service. The managed service provides IBM Cloud based hosting, product installation, operation, maintenance and support for TAS.
 
The provisioning process is invoked when a client has placed an order using TAS-MS part numbers. 

There are three (3) part numbers:

D05UTZX- Capacity

D05USZX  - Data

D05URZX - VPC (Virtual Processor Core)

 
Each client is provisioned in an environment that is separate and distinct from other clients.  The provisioning is done to meet the specific customer requirements for a specific order.  This means there is no pre-provisioning done and client environment provisioning begins when an order is placed. 
 
The provisioning process has several steps, most of them automated, but some that require a manual update(s) to complete.  The timeframe to complete a new provisioning will depend on several factors including:
 
* The size of the order

*  The order complexity

* Availability of bare metal servers

* The number of orders in the queue ahead of the order

In general, allow for at least 10 business days for provisioning to be completed.
 
## Deployment on Shared Cluster
{:deployment-shared-cluster}

TAS MS is deployed in a Shared Cluster and is subject to the TAS MS offering software upgrade policy that is set by IBM. IBM will determine and communicate when upgrades will occur, and no deferrals or exceptions will be allowed.

In the Shared Cluster deployment, IBM Red Hat OpenShift on IBM Cloud and IBM Cloud Pak for Data will be shared across multiple Production Instance(s) and Non-Production Instance(s) and Clients. 



The provisioning itself can be broken down into a number of steps:
 
1. Order validation
2. Information gathering
3. Initial provisioning of TAS base environment
4. Provisioning of the individual TAS products the clients has requested
5. Internal IBM verification of the provisioned environments
6. Welcome letter sent to the client / designated contacts indicating provisioning is complete

## Order Validation
{: #order-validation}

Once an order has been placed, the initial step is to validate the order and the information submitted.  This includes checking the part numbers, ensuring the provisioning form has been completed, performing IBM internal financial checks and setting up the order to be provisioned.  In general this can take 1 to 2 days to complete.
 
Once this is complete, the order is sent to the IBM TAS Managed Services Provisioning team to begin the provisioning of the order.
 
## Information Gathering
{: #information-gather}

Once the order has been placed into the provisioning queue, additional information needs to be validated and gathered.  This includes preparing the final architecture for the order; specifying the infrastructure needed to meet the order requirements; ensuring requested URL(s) are valid and available; detailed review of the order to ensure completeness; meeting or clarifying specific items with the sales person or client as required and setting up the provisioning parameters.
 
This step can take a few hours to several days depending on the initial quality and completeness of the information.  Critical information that is needed includes:
 
- products that to be deployed (not all products will be deployed by default).
- anticipated sizing information for each product - this can be based on users, I/O or other metrics specific to each product
- URL's being requested
- Languages required
- Add On and/or Industry Solutions required
- location of the majority of users to determine optimal placement of the Suite in the proper IBM Cloud data center
 
If this information is missing or incorrect it can cause delays in the provisioning process while this information is being confirmed.
 
## Initial Provisioning
{: #initial-provisioning}

The initial provisioning covers several key aspects of the TRIRIGA Application Suite deployment.
 
The base architecture is finalized regarding the size and number of OpenShift clusters needed.  The provisioning of all based components and configuration is performed and the initial DNS registration for the TRIRIGA Application Suite done.  A temporary license file is installed.  The client will need to supply the final license file (described below).
 
## Provisioning of the Individual Products
{: #provisioning-products}

At this point, the products the client has selected is provisioned based on the sizing parameters that were specified.  This includes deploying the appropriate containers within OpenShift and configuring the products to be available to the client.  This includes the application, database, any network configuration required, DNS registrations and set up of client administration users. 
 
At this stage, all operational configuration is finalized including ensuring backups are configured properly, monitoring in place and security scans completed.  Alerting is configured and the sites added to the TAS-MS escalation process.
 
## Final Verification of the Provisioning
{: #provisioning-verification}

A final review of the install is done to ensure what has been deployed meets the order and the additional information gathered.  At this point, the order is marked complete.
 
## Welcome Letter sent to the client
{: #welcome-letter}

A welcome letter is then sent to the client which will include the URL's to access each environments, usernames and instructions on how to supply the license file the customer would have received when they purchased the TRIRIGA Application Suite product.
 
The letter will contain similar instructions to below:
* Some IBM products require license keys to use them. The [IBM License Key Center](https://licensing.subscribenet.com/control/ibmr/login) is an online software license key delivery tool that provides easy access to your license keys 24 hours a day, 7 days a week. 

## How to log in
{: #how-to-login}
 
* To access your license keys:
    * Please click [here](https://urldefense.proofpoint.com/v2/url?u=https-3A__licensing.subscribenet.com_service_ibmr_passwordfindertoken-3Ftoken-3DiBQqgLdNUxyuxE8Ik8PMKSMDo79ubDnPVuLzb6G50e8V6us7ubXZDYizfshmUft4n9qHifp1xZluaMEBCauDmw-253D-253D&d=DwMDaQ&c=jf_iaSHvJObTbx-siA1ZOg&r=bSeOIO3coRE67_IGnJbSkmdGrML0r3fDG4JKYOYSpt4&m=vXEs4tQw0jGZbxoe8CB4_ay45BzQckFiKIIZfFXQ8oI&s=sUdq8LY1rpYBZyrgdqQXnmvo4BePM0scOTmmhvZXUzE&e=) to create your Password
    * Once you have created your password click on the Attempt to Login link.
    * Select the link to log in to the License Key Center.
    * Select Continue to navigate to the IBM Rational License Key Center.
    * Log in to the License Key Center using your email address as your ID and your password.
    * If you do not create your password and log in within 72 hours of receiving this e-mail, you will need to request a new email by clicking  [here](https://urldefense.proofpoint.com/v2/url?u=https-3A__licensing.subscribenet.com_service_ibmr_passwordfindertoken-3Ftoken-3DiBQqgLdNUxyuxE8Ik8PMKSMDo79ubDnPVuLzb6G50e8V6us7ubXZDYizfshmUft4n9qHifp1xZluaMEBCauDmw-253D-253D&d=DwMDaQ&c=jf_iaSHvJObTbx-siA1ZOg&r=bSeOIO3coRE67_IGnJbSkmdGrML0r3fDG4JKYOYSpt4&m=vXEs4tQw0jGZbxoe8CB4_ay45BzQckFiKIIZfFXQ8oI&s=sUdq8LY1rpYBZyrgdqQXnmvo4BePM0scOTmmhvZXUzE&e=t)

Once the client has logged in and obtained their license key, this must be sent to the TAS MS Provisioning team who will install it in the customer instance.

