## Docker CE Provision

### Requeriments

* 1 Disk /dev/sdb (~60GB)

If you device is diferent to sdb, change:

```
docker_lvm_device: sdX
``` 

If you prefer don't use lvm, then change:

```
docker_lvm_storage: no
```
