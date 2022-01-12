

There are three ways to set or override defaults, or in the absence or a default, set the value. These are

* terraform.tfvars files
* Environment variable prefixed with TF_VAR, e.g TF_VAR_my_var = bar
* Flags passed to the terraform command terraform apply -var "my_var=bar"


Type constraints control the type of variable values.

Primitive(Single type value): number, string, bool

Complex(Multiple types in a single variable): list, tuple, map, object

```
varible "data" {
    type = list(any)
    default = [1, 42, 7]
}
```

```
variable "rules" {
    type = list(object({
        port = number
        proto = string
        cidr_blocks = list(string)
    }))
    default = [
        {
            port = 80
            proto = "tcp"
            cidr_blocks = ["0.0.0.0/0"]
        }
    ]
}
```

```
variable "external_port" {
    type = number
    default = 8080
    validation {
        condition = can(regex("8080|80", var.external_port))
        error_message = "Port values can only be 8080 or 80."
    }
}
```