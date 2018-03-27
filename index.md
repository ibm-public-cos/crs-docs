---
title: IBM Cloud Object Storage
keywords:
tags:
sidebar: crs_sidebar
permalink: index.html
redirect_from:
  - /crs-other-offerings
  - /crs-other-offerings.html
redirect_to:
  - https://console.bluemix.net/docs/services/ibm-cos/index.html
summary:
toc: false
---

{% include custom/deprecation.html %}

Information stored with IBM Cloud Object Storage is encrypted and dispersed across multiple geographic locations, and accessed through an implementation of the S3 API. This service makes use of the distributed storage technologies provided by IBM's Cloud Object Storage System (formerly Cleversafe).

IBM COS is available in two configurations: Cross Region and Regional.  Cross Region service provides higher durability and availability than using a single region at the cost of slightly higher latency, and is available today in the US and EU. Regional service reverses those tradeoffs, and distributes objects across multiple availability zones within a single region, and is available in the US South. If a given region or availability zone is unavailable, the object store continues to function without impediment, and any missed changes are applied when the data center comes back online.

Developers use IBM COS's implementation of the S3 API to interact with their storage accounts. This documentation provides support to get started with provisioning accounts, to create buckets, to upload objects, and to use a reference of common API interactions. This offering is managed through the IBM Bluemix Infrastructure (formerly SoftLayer) Control portal.

### Other IBM object storage services

In addition to COS, IBM Cloud currently provides two additional object storage offerings for different user needs, all of which are accessible through web-based portals and REST APIs.

| Offering | Interface | Defining advantage |
|-- |-- |-- |
| IBM Cloud Object Storage | S3 API | -- Highest availability, durability and resiliency<br> -- Encryption at rest and in flight|
| OpenStack Swift Object Storage | Swift API | -- Native integration with OpenStack clouds <br> -- Choice of 20 geographic regions|
| Object Storage for IBM Bluemix Developer Services | Swift API | -- Native integration with Bluemix services |
{:.overviewtable}

#### OpenStack Swift Object Storage

Information stored with OpenStack Swift Object Storage is located in one of 20 global data centers. Developers use the community Swift API to interact with their storage accounts. This offering is managed through the IBM Bluemix Infrastructure Control portal and does not provide encryption at-rest.

#### Object Storage for IBM Bluemix Developer Services

Information stored with Object Storage for IBM Bluemix is located in either Dallas or London data centers, and storage accounts are available for binding to Bluemix services. Based on the OpenStack Swift platform, developers use the community Swift API to interact with their storage accounts. This offering is managed through the IBM Bluemix console and does not provide encryption at-rest.

### About this documentation

This documentation is for anyone interested in learning about how to use IBM COS to manage unstructured data IO in their cloud applications, to store large files for machine learning and data analysis, or simply as a tool for backup and other IT services. For more detailed documentation about the other OpenStack Swift based IBM object storage services, please visit the links found under **Documentation** in the header of this site.

{% include custom/prereqs.md %}

Please contact `nicholas.lange@ibm.com` with questions or suggestions about the documentation itself.
