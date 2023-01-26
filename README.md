# nutanix-prune-vms

Prune expired VMs from Nutanix clusters

This uses Prism Central API to remove VMs after a certain time. This is currently set at 48hrs. To change time adjust varible called `overtimetotal`.

**For this code to be tested. You will need to run this on the bastion host of the Nutanix cluster.**

```bash
export ANSIBLE_HASHI_VAULT_ADDR=<DPP Vault Server>
export ANSIBLE_HASHI_VAULT_ROLE_ID=<DPP approle role-id>
export ANSIBLE_HASHI_VAULT_SECRET_ID=<DPP approle secret-id>
export REQUESTS_CA_BUNDLE="${REQUESTS_CA_BUNDLE:-/etc/pki/tls/certs/ca-bundle.crt}"
```

*** ansible-playbook nutanix_vm_delete.yml -i inventory.yml***

There is a directory call **skipvmuuid** which contains the UUID of VMs running in the cluster.

**Do not modify allprismcentrals.yml unless you know what you are doing.**

Add files to this directory to skip vms from deletion. Please look at allprismcentrals.yml for example configuration.

There is a scheduled worflow job template in AAP to run at a specific time.

