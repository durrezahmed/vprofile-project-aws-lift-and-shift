## 11. Map ELB Endpoint to website name in DNS Records:

Now copy the `Elastic Load Balancer` endpoint and make a `CNAME` record in the domain's `DNS` records.

| Type  | Name          | Data                   | TTL    |
| ----- | ------------- | ---------------------- | ------ |
| CNAME | `vprofileapp` | `ELB's endpoint` value | 1 Hour |
