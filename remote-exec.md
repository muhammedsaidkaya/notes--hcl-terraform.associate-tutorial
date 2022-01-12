

```
resource "aws_instance" "ec2" {
    ... #other attributes not shown

    provisioner "remote-exec" {
        inline = ["sudo yum -y install httpd"]

        connection {
            type = "ssh"
            user = "ec2-user"
            private_key = file("~/.ssh/id_rsa")
            host = self.public_ip
        }
    }
}
```