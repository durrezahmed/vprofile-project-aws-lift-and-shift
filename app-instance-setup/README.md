## 9. Download Artifact to Tomcat EC2 Instance:

Now an IAM Role `vprofile-artifact-storage-role` has to be created for the Tomcat EC2 instance with `AmazonS3FullAccess` policy. Then attach that IAM Role to the `vprofile-app01` instance.

&nbsp;  
Delete the default application of Tomcat:

```bash
systemctl stop tomcat
systemctl status tomcat

rm -rf /usr/local/tomcat8/webapps/ROOT*
```

&nbsp;  
Copy the Artifact from S3 Bucket and Start the Tomcat Service:

```bash
apt install awscli -y

aws s3 cp s3://<s3-bucket-name>/vprofile-v2.war /tmp/vprofile-v2.war

cp /tmp/vprofile-v2.war /var/lib/tomcat8/webapps/ROOT.war

systemctl start tomcat8
```
