#### Migrating/recovering disk

for pvc,and pv
storageClassName should be ""

Alternatively, if you're re-creating
this config from scratch the key is that the 
volumeName of the PVC needs to be set to that of the PV,
the claimRef of the PV needs to reference the PVC names and namespaces,
and both have the storageClassName = ""


![../images/pv-and-pvc.png](./../pv-and-pvc.png)
