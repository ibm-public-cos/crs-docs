---
title: Using Node.js with IBM COS
keywords: 
last_updated: November 18, 2016
tags: 
summary: 
sidebar: crs_sidebar
permalink: node
folder: api-reference
---

IBM COS is compatible with most available node packages intended for use with the S3 API, provided they allow for the setting of a custom endpoint.  

By default, access keys are sourced from `~/.aws/credentials`, but can also be set as environment variables. Minimum required `~/.aws/credentials` file:

```
[default]
aws_access_key_id = {Access Key ID}
aws_secret_access_key = {Secret Access Key}
```

The `aws-sdk` package provides complete access to the S3 API and can source credentials from the `~/.aws/credentials` file referenced above.  The IBM COS endpoint must be specified when creating a client as shown in the following basic example. 

{% include note.html content="The AWS SDK for Java is comprehensive, and has features and capabilities not described in this guide.  For detailed class and method documentation, as well as the source code, see the [GitHub repository](https://github.com/aws/aws-sdk-js)." %}


### Creating a new bucket

```node
var AWS = require('aws-sdk')
var config = {
    endpoint: "https://s3-api.us-geo.objectstorage.softlayer.net"
};

AWS.config.update(config);
var cos = new AWS.S3();

// this assumes credentials are located in ~/.aws/credentials


var bucketParams = {
    Bucket : 'my-new-bucket',
    CreateBucketConfiguration: {
        LocationConstraint: 'us-standard'
    },
};

// Call S3 to create the bucket
cos.createBucket(bucketParams, function(err, data) {
    if (err) console.log(err, err.stack);
    else console.log(data);
});

```


