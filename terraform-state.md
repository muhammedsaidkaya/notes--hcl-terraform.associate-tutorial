

* List resources in the state
```
terraform state list
```

* Show a resource in the state
```
terraform state show 'packet_device.worker'
```

* Show a module resource in the state
```
terraform state show 'module.foo.packet_device.worker'
```