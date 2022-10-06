---

copyright:
  years: 2022
lastupdated: "2022-10-03"

subcollection: tas-ms

keywords: tririga-ms

---

{{site.data.keyword.attribute-definition-list}}

# Architecture
{: #architecture}

Tririga Application Suite (TAS) is a feature rich suite of applications that uses key IBM and Red Hat technologies.  The TAS Managed Service delivers this functionality on the IBM Cloud.
 
The current IBM Cloud data centers being leveraged for TAS-MS are:
 
- Washington, DC, United States

- Dallas, TX, United States

- Amsterdam, Netherlands

- Frankfurt, Germany

- Sydney, Australia
 
On site customer visits to IBM Cloud data centers are not allowed for security reasons. Street address locations of data centers are not disclosed. This is in accordance to IBM's NIST guidelines and AICPA Trust Services criteria.
Below are two video tours of IBM Cloud Data Centers that describe general layout and architecture. Please note IBM acquired SoftLayer in 2013 and it is now referred to as "IBM Cloud"

https://www.youtube.com/watch?v=U1ROjNxTcqQ

https://www.youtube.com/watch?v=-sk-zjRfXSk


## Network Architecture
{: #net-architecture}

IBM Cloud has a unique Triple Network architecture.  Every server provisioned in the IBM Cloud has 3 distinct networks:

### Public Network
{: #pub-architecture}

Two network interfaces are dedicated to the public network.  This network serves as the internet facing network for the server.  IBM TAS-MS uses this network as the way for external clients to access the application. This network is also secured by a firewall pair managed by IBM Cloud Delivery Services. 

### Private Network
{: #net-private}

Two network interfaces are dedicated to the private network.  This network serves as a secure private network dedicated to IBM Cloud.  IBM Cloud uses this network for secure server to server communication as well as data center to data center communications.  This network has no access to the internet.

### Management Network
{: #net-mgnte}

One network interface is dedicated to the Management network.  This secure out-of-band network is accessible via an IBM managed VPN.  It is used by IBM Cloud staff for maintenance and administration purposes such as firmware updates, OS reloads, power-cycle or other IPMI functions like keyboard, video, mouse control (KVM over IP).
For the TAS Managed Service each client is provisioned with their own application instance and dedicated namespace(s).  The IBM TAS-MS team will provision and configure all necessary underlying infrastructure and components.
IBM Cloud Data Centers are SOC compliant and have full hardware redundancy implemented for all servers. All data centers have an N1 redundant power and cooling infrastructure, including backup power generators. All servers have redundant power supplies, NICs and use SAN based RAID storage. 

## TRIRIGA Application Suite Managed Service Architecture highlights:
{: #net-highlights}

* TAS MS customers are provisioned two (2) environments by default: PROD and NON-PROD

* All clients will be provisioned in their own application instance using dedicated namespace(s).

* IT Administration for the PROD and NON-PROD environments is solely managed by IBM's Cloud Delivery Services (CDS) and Development Operations (DevOps) teams

* Clients can access PROD and NON-PROD systems via URL

* TAS-MS is an internet based offering that runs over HTTPS. There is no private cloud or direct connect option for TAS MS.

* Clients are provided application administrator access for all applications they have ordered.

* All Servers are Red Hat Linux O/S

* Databases are DB2.  Oracle and SQLServer are not currently supported. 
