## 6. Update IP to Name Mapping in Route 53:

Create a `Hosted Zone` in the Route 53 Service DNS Management.

#### Hosted Zone Configuration:

| Domain Name   | Description                              | Type                |
| ------------- | ---------------------------------------- | ------------------- |
| `vprofile.in` | Hosted Zone for vprofile backend servers | Private hosted zone |

#### VPCs to associate with the hosted zone:

| Region      | VPC ID                      |
| ----------- | --------------------------- |
| `us-east-1` | Select the Default `VPC ID` |

#### Configure Records:

Add Simple Routing Records for the three backend services.

| Record Name       | Type | Value/Route Traffic to                  | TTL (seconds) |
| ----------------- | ---- | --------------------------------------- | ------------- |
| db01.vprofile.in  | A    | private IP of `vprofile-db01` instance  | 300           |
| mc01.vprofile.in  | A    | private IP of `vprofile-mc01` instance  | 300           |
| rmq01.vprofile.in | A    | private IP of `vprofile-rmq01` instance | 300           |
