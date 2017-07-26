---
title: Frequently asked questions
keywords: 
last_updated: November 18, 2016
tags: 
summary: 
sidebar: crs_sidebar
permalink: faq
folder: help
toc: false
---

# IBM Cloud Object Storage FAQ 


## API Questions

Q:  Are COS global bucket names case sensitive?
A:  Bucket names are required to be DNS addressable, and thus not case sensitive.

Q:  What is the maximum number of characters that can be used in an Object name?  Current filesystem limits are 255 characters.  
A:  1024

## Offering Questions

Q:  Do we offer a free tier option for IBM Cloud Object Storage?
A:  Yes, use promo code `COSFREE` to obtain 25 GB of storage and a bunch of operations per month. 

Q:  Is there a 100-bucket limit to an account?  What happens if we need more?
A:  Yes, 100 is the current bucket limit.  Generally, prefixes are a better way to group together objects in a bucket, unless the data needs to be in a different region or storage class.  For example, to group patient records, you would use one prefix per patient. If this is not a workable solution, contact customer support.

Q:  If I want to store my data using IBM COS Vault or Cold Vault, do I need to create another account?
A:  No, storage classes (and regions as well) are defined at the bucket level.  Simply create a new bucket that is set to the desired storage class.

Q:  When I create a bucket using the API, how do I set the storage class?
A:  The storage class (eg `us-flex`) is assigned to the `LocationConstraint` configuration variable for that bucket.  This is because of a key difference between the was AWS S3 and IBM COS handle storage classes.  IBM COS sets storage classes at the bucket level, while AWS S3 assigns a storage class to an individual object.

Q:  Can the storage class of a bucket be changed?  For example, if you have production data in 'standard', can we easily switch it to 'vault' for billing purposes if we are not using it frequently?
A:  Today changing of storage class requires manually moving or copying the data from one bucket to another bucket with the desired storage class. 


## Performance Questions

Q:  Does data consistency in COS come with a performance impact?
A:  Consistency with any distributed system comes with a cost, but the efficiency of the IBM COS dispersed storage system is higher, and overhead is lower compared to systems with multiple synchronous copies.  

Q:  Aren't there performance implications if my application needs to manipulate large objects?
A:  For performance optimization, objects can be uploaded and downloaded in multiple parts, in parallel. 

 
## Encryption Questions

Q:  Does IBM COS provide encryption at rest and in motion?
A:  Yes.  Data at rest is encrypted with automatic provider side Advanced Encryption Standard (AES) 256-bit encryption and Secure Hash Algorithm (SHA)-256 hash. Data in motion is secured by using built-in carrier grade Transport Layer Security/Secure Sockets Layer (TLS/SSL) or SNMPv3 with AES encryption.

Q:  What is the typical encryption overhead if a customer wants to encrypt their data?
A:  Server side encryption is always on for customer data.  Compared to the hashing required in S3 authentication and the erasure coding, encryption is not a big part of the processing cost of COS.

Q:  Does IBM COS encrypt all data?  
A:  Yes, IBM COS encrypts all data.  

Q:  Does IBM COS have FIPS 140-2 compliance for the encryption algorithms?
A:  The algorithms are FIPS 140-2 ready but testing / certification is still pending.

Q:  Will client-key encryption be supported?
A:  Yes, client-key encryption will be supported in 2017.  

## General questions

Q: How many objects can fit in a single bucket?
A: There is no practical limit to the number of objects in a single bucket.

Q: Can I nest buckets inside one another?
A: No, buckets can not be nested.  If a greater level of organization is required within a bucket, the use of prefixes is supported: `{endpoint}/{bucket-name}/{object-prefix}/{object-name}`.  Note that the object's key remains the combination `{object-prefix}/{object-name}`.

Q: What is the difference between 'Class A' and 'Class B' requests?
A:'Class A' requests are operations that involve modification or listing.  This includes creating buckets, uploading or copying objects, creating or changing configurations, listing buckets, and listing the contents of buckets.'Class B' requests are those related to retrieving objects or their associated metadata/configurations from the system. There is no charge for deleting buckets or objects from the system.

Q:  What is the best way to structure your data using Object storage such that you can 'look' at it and find what you are looking for?  Without a directory structure, having 1000s of files at one level seems hard to view.
A:  You can use metadata associated with each object to find the objects you are looking for. The biggest advantage of object storage is the metadata associated with each object. Each object can have up to 4 MB of metadata in IBM COS.  When offloaded to a database, metadata provides excellent search capabilities.  A large number of (key, value) pairs can be stored in 4 MB.  You can also use Prefix searching to find what you are looking for. For example, if you use buckets to separate each customer data, you can use prefixes within buckets for organization. For example:  /bucket1/folder/object where 'folder/' is the prefix.

Q: Can you confirm that IBM COS is ‘immediately consistent’, as opposed to ‘eventually consistent’? 
A:  COS is ‘immediately consistent’ for data and ‘eventually consistent’ for usage accounting.

Q:  Does data stored on IBM COS need backup?  
A:  Most likely not, especially if you are using IBM COS Cross Region resiliency option to store your objects.   We have multiple IBM COS offerings in the Cloud, some with regional resiliency and others with Cross-Region resiliency.    All offerings use erasure coded slices to distribute data across multiple sites –  our Regional offerings will do this distribution across data centers within a region and our Cross-Region offerings will do this distribution across data centers that span multiple regions.   For example, US Cross Region will distribute erasure coded object slices across Dallas, San Jose, and Washington DC data centers.

Q:  Can IBM COS partition the data automatically for me like HDFS, so I can read the partitions in parallel, e.g. with Spark?
A:  IBM COS supports a ranged GET on the object, so an application can do a distributed striped read type operation.  Doing the striping would be on the application to manage.  

