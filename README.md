# nutanix-prune-vms
remove vms from nutnaix cluster


This uses PrismCentral API to remove VMs after a certain time. This is currently set at 48hrs.
There is a directory call skipvmuuid which contains the UUID of VMs running in the cluster.
Do not modify allprismcentrals.yml unless you know what you are doing.
Add files to this directory to skip vms from deletion.
