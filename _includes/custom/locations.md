
{% include note.html content="Using third-party tools or SDKs may enforce manually setting a `LocationConstraint` when creating a bucket. Unlike AWS S3, IBM COS uses this value to indicate the storage class of an object. This field has no relation to physical geography or region - those values are provided within the endpoint used to connect to the service. Currently, the only permitted values for `LocationCostraint` are: <br>
&emsp;&emsp;  `us-standard` / `us-vault` / `us-cold` / `us-flex` <br>
&emsp;&emsp;  `us-south-standard` /
`us-south-vault`  /
`us-south-cold` /
`us-south-flex` <br>
&emsp;&emsp;  `eu-standard` / 
`eu-vault` / 
`eu-cold` / 
`eu-flex` <br>


"%}