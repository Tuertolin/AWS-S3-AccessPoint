# AWS-S3-AccessPoint
AWS S3 Access Point configuration using AWS CLI

First of all update your AWS CLI version
``` $ pip install --upgrade awscli
    $ aws --version                                       │
    aws-cli/1.17.15 Python/2.7.17 Linux/4.4.0-17763-Microsoft botocore/1.14.15 
```

Then you will be able to create the s3 Access Point using:

```
    $ aws s3control create-access-point --name example-vpc-ap --account-id 1234567890ab --bucket your-bucket-name --region us-west-1
```
```
$ aws s3control list-access-points --account-id 1234567890ab --region us-west-1 --output json
{
    "AccessPointList": [
        {
            "Bucket": "gastogonreplica",
            "Name": "example-vpc-ap",
            "NetworkOrigin": "Internet"
        }
    ]
}
```

```$ aws s3control get-access-point --account-id 1234567890ab --name example-vpc-ap --region us-west-1 --output json
{
    "Name": "example-vpc-ap",
    "PublicAccessBlockConfiguration": {
        "IgnorePublicAcls": true,
        "BlockPublicPolicy": true,
        "BlockPublicAcls": true,
        "RestrictPublicBuckets": true
    },
    "CreationDate": "2020-02-12T00:58:28Z",
    "Bucket": "your-bucket-name",
    "NetworkOrigin": "Internet"
} ```



