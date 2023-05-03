# S3(simple storage service)
## Cloud storage provide a web services where your data can be stored , accessed and easily backed up by users over the internet .
:- it is reliable , Scalable and Secure.

## Types of storages:
+ S3(simple storage service)
+ EBS (elastic block storage) : it  can access from ec2   
+ EFS(elastic file system ) :it can be access from multiple ec2
+ Glacier
+ Snowball:
AWS Snowball is a service that provides secure, rugged devices, so you can bring AWS computing and storage capabilities to your edge environments, and transfer data into and out of AWS



# S3
Simple storage service
+ S3 is a storage for the internet . it has a simple web service interface for simple storing and retrieving  any amount of data , anytime from any where on the internet .
+ We can not install OS in S3
+ Data store in bucket.
+ S3 has a distributed data store architecture where objects are redundantly store  in a multiple location (min 3 location but in same region)
+ A bucket is flat container of objects
+ Max capacity of bucket is 5TB
+ You can create folders in your bucket .
+ Bucket Ownership is non-tranferable 
+ S3 bucket is Region Specified 
+ You can have upto 100 bucket per account (may scalable )


# S3 naming rules
+ S3 bucket names (key) are globally Unique across all AWS Regions .
+ Bucket names must be between 3 (min) and 63 (max) characters long.
+ Bucket names can consist only of lowercase letters, numbers, dots (.), and hyphens (-).
+ Bucket names must begin and end with a letter or number.
+ Bucket names must not be formatted as an IP address (for example, 192.168.5.4).
+ Bucket names must not start with the prefix xn--.
+ Bucket names must not end with the suffix -s3alias. This suffix is reserved for access point alias names. For more information, see Using a bucket-style alias for your access point.
+ Bucket names must be unique across all AWS accounts in all the AWS Regions within a partition. A partition is a grouping of Regions. AWS currently has + three partitions: aws (Standard Regions), aws-cn (China Regions), and aws-us-gov (AWS GovCloud (US)).
+ A bucket name cannot be used by another AWS account in the same partition until the bucket is deleted.
+ Buckets used with Amazon S3 Transfer Acceleration can't have dots (.) in their names. For more information about Transfer Acceleration, see Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration.





# S3 versioning
## Versioning provides several benefits, including:
+ Protection against accidental deletions: With versioning, you can restore a previous version of an object if it was accidentally deleted or overwritten.

+ Recovery of data: If your data is lost or corrupted, you can recover the previous version of the object.

+ Compliance and auditability: Versioning helps you comply with regulatory requirements for data retention and provides an audit trail of changes to your data.

+ Rollback to previous versions: You can rollback to a previous version of an object if you discover an issue with the current version.

# Storage class of S3

+ Standard :- suitable for use case where the latency should be low.
+ Standard for infrequent data access: can be use where the data is long lived and less frequently accessed
+ Amazon Glacier:  Can be used where the data has to be archived and high performance is not re required
+ One Zone -IA :  can be used where the data is infrequently accessed  and stored in a single region .
