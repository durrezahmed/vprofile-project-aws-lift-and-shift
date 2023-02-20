## 2. Create Certificate for Domain using ACM (AWS Certificate Manager):

Choose the following certificate type.

| Certificate Type             |
| ---------------------------- |
| Request a public certificate |

&nbsp;  
Then enter the details according to your domain.

| Domain Names           | Select Validation Method     | Tag Key | Tag Value            |
| ---------------------- | ---------------------------- | ------- | -------------------- |
| `*.<your-domain-name>` | DNS validation - recommended | Name    | `<your-domain-name>` |

&nbsp;  
Now a `CNAME` record has to be created in the domain's `DNS` records with the `CNAME name` and `CNAME value` of the certificate that is created in the previous step. The value of both the fields can be found inside the certificate details page.

| Type  | Name               | Data                | TTL    |
| ----- | ------------------ | ------------------- | ------ |
| CNAME | `CNAME name` value | `CNAME value` value | 1 Hour |
