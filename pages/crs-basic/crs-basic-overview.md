---
title: Introduction
keywords: 
tags:
sidebar: crs_basic_sidebar
permalink: crs-basic-overview.html
summary: 
folder: crs-basic
---

> IBM COS Standard Cross Region is currently in open trial. 
> 
> Please visit [IBM Cloud](https://www.softlayer.com/Store/orderService/objectStorage) to participate.

## Understanding IBM Cloud Object Storage
IBM Bluemix Infrastructure currently offers three unique object storage offerings for different user needs, all of which are accessible through a web-based portal and RESTful APIs.

| Offering | Interface | Defining advantage |
|-- |-- |-- |
| IBM COS Standard Cross-Region | S3 API | Highest availability and encryption at rest |
| IBM COS Standard Regional | Swift API | Native integration with OpenStack clouds |
| Object Storage for IBM Bluemix | Swift API | Native integration with Bluemix services |
{:.overviewtable}

### IBM COS Standard Cross-Region

Information stored with IBM COS Cross-Region is encrypted and dispersed across three geographic regions (Dallas, San Jose, and Washington, DC) and accessed through an implementation of the S3 API. This is the first offering that makes use of the distributed storage technologies provided by IBM's Cloud Object Storage System.

Standard Cross-Region service provides higher durability and availability than using a single region at the cost of slightly higher latency.  If a given data center is unavailable, the object store continues to function without impediment, and any missed changes are applied when the data center comes back online.

Developers use IBM COS's implementation of the S3 API to interact with their storage accounts. This documentation provides support to get started with provisioning accounts, to create buckets, to upload objects, and to use a reference of common API interactions. This offering is managed through the IBM Bluemix Infrastructure (formerly SoftLayer) Control portal.

### IBM COS Standard Regional

Information stored with IBM COS Standard Regional is located in one of 20 global data centers. Based on the OpenStack Swift platform, developers use the community Swift API to interact with their storage accounts. This offering is managed through the IBM Bluemix Infrastructure (formerly SoftLayer) Control portal and does not provide encryption at-rest.

### Object Storage for IBM Bluemix

Information stored with Object Storage for IBM Bluemix is located in either Dallas or London data centers, and storage accounts are available for binding to Bluemix services. Based on the OpenStack Swift platform, developers use the community Swift API to interact with their storage accounts. This offering is managed through the IBM Bluemix console and does not provide encryption at-rest.