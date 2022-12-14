# WorqHat AWS S3 setup to store call recordings

This project was created to help developers move faster. Our team has created a GitHub repo with 
a custom script that will configure your S3 bucket for WorqHat Call recordings.

## Setup

- Run `npm install`.
- [Setup your AWS credentials](https://docs.aws.amazon.com/sdk-for-java/v1/developer-guide/setup-credentials.html) on your development machine or you 
  can visit our [Support Docs](https://support.worqhat.com/en/support/solutions/articles/84000371663-storing-worqhat-video-call-recordings-in-a-custom-amazon-s3-bucket).

## Instructions

- `npx cdk bootstrap --context worqhatSubdomain=[worqhat_subdomain] --context s3bucketName=[bucket_name] --context  s3bucketRegion=[bucket_region]`
- `npx cdk deploy --context worqhatSubdomain=[worqhat_subdomain] --context s3bucketName=[bucket_name] --context s3bucketRegion=[bucket_region]`

The output of the `cdk deploy` command will include the names of the
s3 bucket and the IAM role configured for WorqHat.
You'll use these to configure your WorqHat Workspaces for
outputting recordings.

## Note

Bucket is created with basic configuration, you may want to configure differently, e.g.

- adding versioning
- encryption keys
- public/private settings
- cors settings

It can be done by modifying the `aws_s3.Bucket` in the [libs](./lib/worqhat-recordings-bucket-stack.ts).

## Contact us

In case you face any issues while setting up your AWS S3 Bucket with WorqHat, please contact us 
at [WorqHat Email](mailto:support@worqhat.com) or log in a Support Request at [WorqHat Support](https://support.worqhat.com/en/support/home).
