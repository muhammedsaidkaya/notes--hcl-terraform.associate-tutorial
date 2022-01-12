

```
resource "aws_instance" "my-instance" {
    ami = data.aws_ssm.parameter.ami_id.value
    subnet_id = module.vpc.public_subnets[0]
    instance_type = t3.micro
    security_groups = [aws.security_group.my-sg.id]
    user_data = fileexists("script.sh) ? file("script.sh") : null
}

```