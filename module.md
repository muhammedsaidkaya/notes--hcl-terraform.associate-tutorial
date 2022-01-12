
```
module "my-vpc-module" {
    source = "./modules/vpc" # Module source (mandatory)
    version = "0.0.5"
    region = var.region #Inputs (Inside module var.region)
}
```

Other allowed parameters: count, for_each, providers, depends_on

The outputs declared inside Terraform module can be fed back into the root module or your main code.

```
module.<name-of-module>.<name-of-output>
```