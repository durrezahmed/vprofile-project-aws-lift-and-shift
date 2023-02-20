## 8. Upload to S3 Bucket:

Now the `artifact` will be uploaded to an S3 bucket. For this `AWS CLI` will be used and a AWS IAM user should be created with `programmatic access` and `AmazonS3FullAccess` policy. Do not expose the key credentials for this user anywhere.

&nbsp;  
Configure the AWS CLI with `Access Key ID`, `Secret Access Key`, `default region` and `default output format` :

```bash
aws configure
```

&nbsp;  
Create an S3 Bucket:

```bash
aws s3 mb s3://<s3-bucket-name>
```

&nbsp;  
Copy the Artifact to S3 Bucket:

```bash
cd vprofile-project-devops/target/
```

```bash
aws s3 cp vprofile-v2.war s3://<s3-bucket-name>/vprofile-v2.war
```
