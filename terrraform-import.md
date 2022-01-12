

Maps existing resources to Terraform using an "ID"

"ID" is dependent on the underlying vendor, for example to import an AWS EC2 instance you'll need to provide its instance ID.

Importing the same resource to multiple Terraform resources can cause unknown behavior and is not recommended.

```
terraform import RESOURCE_ADDRESS ID
```