
```
terraform {
    required_providers {
        docker {
            source = "kreuzwerker/docker"
        }
    }
    required_version = ">= 0.13"
    backend "s3" {
        profile = "demo"
        region = "us-west-2"
        key = "terraform.tfstate"
        bucket = "myawesomes3bucket3344"
    }
}
```