
```
> max(5,3,1,4,5)

> timestamp()

> join("_", ["acloud", "guru"])

> contains(["acloud", "guru", 1,2,3], "guru")
```

Built-in functions are extremely useful in making Terraform code dynamic and flexible.

```
variable "project-name" {
    type = "string"
    default = "prod"
}

resource "aws_vpc" "my_vpc" {
    cidr_block = "10.0.0.0/16"
    tags = {
        Name = join("-", ["terraform", var.project-name])
    }
}
```