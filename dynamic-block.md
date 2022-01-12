

Used to make your code look cleaner

Dynamic blocks expect a complex variable type to iterate over

It acts like a for loop and outputs a nested block for each element in your variable

```
resource "aws_security_group" "my_sg" {
    name = "my-aws-security-group"
    vpc_id = aws_vpc.my-vpc.id
    dynamic "ingress" {
        for_each = var.rules
        content {
            from_port = ingress.value["port"]
            to_port = ingress.value["port"]
            protocol = ingress.value["proto"]
            cidr_blocks = ingress.value["cidrs"]
        }
    }
}
```

```
variable "rules" {
    default = [
        {
            port = 80
            proto = "tcp"
            cidr_blocks = ["0.0.0.0/0"]
        },
        {
            port = 22
            proto = "tcp"
            cidr_blocks = ["1.2.3.4/32"]
        }
    ]
}
```