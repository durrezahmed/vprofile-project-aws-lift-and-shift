## 10. Setup ELB (Elastic Load Balancer) with HTTPS (Cert from Amazon Certificate Manager):

Now a `Target Group` has to be created for Elastic Load Balancer.

#### Basic Configurations:

| Choose a target type | Target group name | Protocol : Port |
| -------------------- | ----------------- | --------------- |
| Instances            | `vprofile-app-tg` | HTTP : `8080`   |

#### Health Checks:

| Health check protocol | Health check path |
| --------------------- | ----------------- |
| HTTP                  | `/login`          |

#### Advanced Health Checks:

| Port            | Healthy threshold |
| --------------- | ----------------- |
| Override `8080` | `3`               |

Then select the `vprofile-app01` instance as target.

&nbsp;  
Now an `Elastic Load Balancer` has to be created.

| Load balancer types       |
| ------------------------- |
| Application Load Balancer |

#### Basic Configurations:

| Load balancer name  | Scheme          | IP address type |
| ------------------- | --------------- | --------------- |
| `vprofile-prod-elb` | Internet facing | IPv4            |

#### Network Mapping:

Select all availability zones in the `us-east-1` region.

#### Security Groups:

| Security groups   |
| ----------------- |
| `vprofile-elb-sg` |

#### Listeners and Routing:

| Protocol | Port | Default action                |
| -------- | ---- | ----------------------------- |
| HTTP     | 80   | Forward to: `vprofile-app-tg` |
| HTTPS    | 443  | Forward to: `vprofile-app-tg` |

Select the certificate for the `HTTPS` listener that was created at the start of the project.
