## 12. Create Auto Scaling Group:

An `AMI` has to be created from the `vprofile-app01` ec2 instance.

#### Create Image:

| Image name           | Image description    |
| -------------------- | -------------------- |
| `vprofile-app-image` | AMI for vprofile app |

&nbsp;  
A `Launch Configuration` has to be created for the Auto Scaling Group.

#### Create launch configurations:

| Key                  | Value                            |
| -------------------- | -------------------------------- |
| Name                 | `vprofile-app-lc`                |
| AMI                  | `vprofile-app-image`             |
| Instance type        | `t2.micro`                       |
| IAM instance profile | `vprofile-artifact-storage-role` |
| Security groups      | `vprofile-app-sg`                |
| Key pair (login      | `vprofile-prod-key`              |

&nbsp;  
Now and `Auto Scaling Group` has to be created.

#### Step 1: Choose launch template or configuration:

| Name               | Launch template   |
| ------------------ | ----------------- |
| `vprofile-app-asg` | `vprofile-app-lc` |

#### Step 2: Configure settings:

Select all the `Subnets` of the default `VPC` .

#### Step 3: Configure advanced options:

| Load balancing        | Target group      | Health checks       |
| --------------------- | ----------------- | ------------------- |
| Enable load balancing | `vprofile-app-tg` | `ELB` - 300 seconds |

#### Step 4: Configure group size and scaling policies:

Adjust the `Group Size` according to your resources.

Select the `target tracking scaling policy` in the scaling policies section.

| Scaling policy name      | Metric type               | Target value |
| ------------------------ | ------------------------- | ------------ |
| `Target tracking policy` | `Average CPU utilization` | `50`         |

#### Step 5: Add notification:

Create a notification to the `SNS Topic` , to get notification whenever Amazon EC2 Auto Scaling launches or terminates the EC2 instances in your Auto Scaling Group.

#### Step 6: Add tags:

| Key     | Value          |
| ------- | -------------- |
| Name    | `vprofile-app` |
| Project | `vprofile`     |

#### Step 7: Review:

Review everything and then create auto scaling group.
