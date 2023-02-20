## 5. Launch Instances with User Data (Bash Scripts):

&nbsp;  
Clone the Repository for the `userdata` scripts:

```bash
git clone https://github.com/durrezahmed/vprofile-project-aws-lift-and-shift.git
```

```bash
cd vprofile-project-aws-lift-and-shift/userdata
```

---

Create `vprofile-db01` instance for mysql service:

#### Name and Tags:

| Key     | Value           |
| ------- | --------------- |
| Name    | `vprofile-db01` |
| Project | `vprofile`      |

#### Application and OS Images (Amazon Machine Image):

Select `CentOS 7 (x86_64) - with Updates HVM` AMI from the AWS Marketplace AMIs

#### Instance Type:

Select `t2.micro` instance type from the dropdown box for instance types.

#### Key Pair (login)

Select `vprofile-prod-key` key pair from the dropdown box of key pair name.

#### Network Settings:

Select `vprofile-backend-sg` security group from the dropdown box of existing security groups.

#### Advanced Details:

Add the `mysql-setup.sh` script to the user data text field of the Advanced details section.

And `Launch` the Instance.

---

Create `vprofile-mc01` instance for memcache service:

#### Name and Tags:

| Key     | Value           |
| ------- | --------------- |
| Name    | `vprofile-mc01` |
| Project | `vprofile`      |

#### Application and OS Images (Amazon Machine Image):

Select `CentOS 7 (x86_64) - with Updates HVM` AMI from the AWS Marketplace AMIs

#### Instance Type:

Select `t2.micro` instance type from the dropdown box for instance types.

#### Key Pair (login)

Select `vprofile-prod-key` key pair from the dropdown box of key pair name.

#### Network Settings:

Select `vprofile-backend-sg` security group from the dropdown box of existing security groups.

#### Advanced Details:

Add the `memcache-setup.sh` script to the user data text field of the Advanced details section.

And `Launch` the Instance.

---

Create `vprofile-rmq01` instance for memcache service:

#### Name and Tags:

| Key     | Value            |
| ------- | ---------------- |
| Name    | `vprofile-rmq01` |
| Project | `vprofile`       |

#### Application and OS Images (Amazon Machine Image):

Select `CentOS 7 (x86_64) - with Updates HVM` AMI from the AWS Marketplace AMIs

#### Instance Type:

Select `t2.micro` instance type from the dropdown box for instance types.

#### Key Pair (login)

Select `vprofile-prod-key` key pair from the dropdown box of key pair name.

#### Network Settings:

Select `vprofile-backend-sg` security group from the dropdown box of existing security groups.

#### Advanced Details:

Add the `rabbitmq-setup.sh` script to the user data text field of the Advanced details section.

And `Launch` the Instance.

---

Create `vprofile-app01` instance for memcache service:

#### Name and Tags:

| Key     | Value            |
| ------- | ---------------- |
| Name    | `vprofile-app01` |
| Project | `vprofile`       |

#### Application and OS Images (Amazon Machine Image):

Select `Ubuntu Server 18.04 LTS (HVM), SSD Volume Type` AMI from the dropdown box of Amazon Machine Image (AMI).

#### Instance Type:

Select `t2.micro` instance type from the dropdown box for instance types.

#### Key Pair (login)

Select `vprofile-prod-key` key pair from the dropdown box of key pair name.

#### Network Settings:

Select `vprofile-app-sg` security group from the dropdown box of existing security groups.

#### Advanced Details:

Add the `tomcat-ubuntu-setup.sh` script to the user data text field of the Advanced details section.

And `Launch` the Instance.
