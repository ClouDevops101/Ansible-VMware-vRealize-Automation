<a href="http://bitly.com/2grT54q"><img src="https://cdn.codementor.io/badges/i_am_a_codementor_dark.svg" alt="I am a codementor" style="max-width:100%"/></a><a href="http://bitly.com/2grT54q"><img src="http://blogs.vmware.com/management/files/2015/02/vRA-Product-Icon-Mac_0.png" height="50"> 
 [![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.me/HAAW)


# Ansible roles for vRealize Automation - VMware vCloud IaaS solution


Description : vRA-deploy-VM is a playbook that use ansible uri core module to request a VM from vRealize automation solution, the Vmware Cloud Automation Center (vCAC)
This script is built to be run from a jenkins slave with a minmal installation in order to create an ephemeral deployement machine to deploy test and destroy the machines after testing. 

HOW It WORKS
================
vRA-deploy-VM is a playbook that use ansible uri core module to request a VM from vRealize automation solution, the vmware cloud.
This script can either be played form jenkins with ansible or in adhoc mode.

requierement : ** A valid vRA account able to create/destroy machines **

As you can see there is two main role file : 

## vRA-deploy-VM.yml :
This file is used to request a VM to vRealize Automation it will play a full mimed json request to ask ressource from vcloud and then get ip and hostname.
Please store user and password in a separate yml vault file

### HOW to use it 
```
ansible-playbook vRA-deploy-VM.yml --ask-vault-pass 
```

###### Input : 
   ```
   VRA_HOST: {{ VRA_HOST}}
   VRA_USER: {{ VRA_USER }}
   VRA_PASS: {{ VRA_PASS }}
   VRA_TENANT: {{ VRA_TENANT }}
   ```

###### Output :
  ```
  VM_Destroy_id="{{ list.json.content[item].id }}" 
  VM_name="{{ list.json.content[item].name }}"  
  VM_IP="{{ list.json.content[item].resourceData }}
 ```

## vRA-destroy-VM.yml : 

### HOW to use it 
```
ansible-playbook vRA-destroy-VM.yml --ask-vault-pass 
```

###### Input : 
   ```
   VRA_HOST: {{ VRA_HOST}}
   VRA_USER: {{ VRA_USER }}
   VRA_PASS: {{ VRA_PASS }}
   VRA_TENANT: {{ VRA_TENANT }}
   {{  DESTROY_ID  }}
   ```
###### Output :
  NONE




