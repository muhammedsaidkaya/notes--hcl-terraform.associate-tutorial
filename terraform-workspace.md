
The Terraform Workspaces are alternate state files within the same working directory.

Terraform starts with a single workspace that is always called default. It cannot be deleted.


```
terraform workspace new  WORKSPACE_NAME
terraform workspace select WORKSPACE_NAME
```

* Conditional Usage of workspace

```
resource "aws_instance" "example" {
    count = terraform.workspace == "default" ? 5 : 1
}
```