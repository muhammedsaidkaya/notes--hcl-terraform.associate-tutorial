

Taints a resource, forcing it to be destroyed and recreated

Modifies the state file, which causes the recreation workflow

Tainting a resource may cause other resources to be modified

```
terraform taint RESOURCE_ADDRESS
```