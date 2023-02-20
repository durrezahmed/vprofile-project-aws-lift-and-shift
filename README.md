# DevOps Project - Vprofile Project AWS Lift and Shift

This is a DevOps project for vprofile app deployment on AWS cloud with Lift and Shift approach using Manual Provisioning.

[Link](https://github.com/durrezahmed/vprofile-project-devops) for vprofile app repository.

## Usage (Flow of Execution): Manual Provisioning

#### 1. Login to AWS Account

[Link](https://aws.amazon.com/marketplace/management/signin) to Login to your AWS Account.

#### 2. Create Certificate for Domain using ACM (AWS Certificate Manager)

Follow the steps in the `create-acm-certificate` directory's readme file to create an ACM certificate.

#### 3. Create Key Pairs

Follow the steps in the `create-key-pairs` directory's readme file to create a key pair.

#### 4. Create Security Groups

Follow the steps in the `create-security-groups` directory's readme file to create security groups.

#### 5. Launch EC2 Instances with User Data (Bash Scripts)

Follow the steps in the `launch-ec2-instances` directory's readme file to launch EC2 instances for services.

#### 6. Update IP to Name Mapping in Route 53

Follow the steps in the `ip-name-mapping-route-53` directory's readme file to create an IP Address to name mapping in Route 53.

#### 7. Build Application from Source Code

Follow the steps in the `build-app-from-source` directory's readme file to build the app from the source code locally.

#### 8. Upload to S3 Bucket

Follow the steps in the `upload-to-s3` directory's readme file to upload the artifact from the local system to an S3 bucket.

#### 9. Download Artifact to Tomcat EC2 Instance

Follow the steps in the `app-instance-setup` directory's readme file to download artifact and setup the app EC2 instance.

#### 10. Setup ELB (Elastic Load Balancer) with HTTPS (Cert from Amazon Certificate Manager)

Follow the steps in the `elb-with-https` directory's readme file to setup the ELB (Elastic Load Balancer) with HTTPS (Cert from Amazon Certificate Manager).

#### 11. Map ELB Endpoint to website name in Domain's DNS Records

Follow the steps in the `elb-endpoint-dns` directory's readme file to map ELB endpoint to website name in domain's DNS Records.

#### 12. Create Auto Scaling Group

Follow the steps in the `create-auto-scaling-group` directory's readme file to create an auto scaling group for the app ec2 instance.

#### 13. Verify

The interface of the vprofile app is then available at `vprofileapp.<your-domain>` and we can verify if all the services are working.
