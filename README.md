# HyperFlex vCenter Server Registration Script

## Purpose
This script will register one or more Cisco HyperFlex clusters with a VMware vCenter server of your choosing. The registration process adds an extension to VMware vCenter and serves as the integration point between Cisco HyperFlex and VMware vCenter.


## Files
`hx_vcenter_register.py` - the python script which performs the registration operation(s) via Cisco HyperFlex APIs

`hx_vcenter_register_input.xlsx` - excel spreadsheet which is used to provide the inputs required for the registration operation(s). This is particularly useful when multiple Cisco 
HyperFlex clusters need to be registered with VMware vCenter. Fill in the HyperFlex cluster information and VMware vCenter information in this spreadsheet, each row represents a different HyperFlex Cluster and corresponding VMware vCenter server.

`requirements.txt` - list of python package dependencies required to run the "hx_vcenter_register.py" python script. Use can use python pip to install these dependencies by using the command `pip install -r requirements.txt`.


## Notes
- This script was developed and tested with Python 3.9
- The vCenter registration API was introduced in HyperFlex Data Platform (HXDP) version 4.5(1a). The script first checks to make sure the HyperFlex cluster is on version 4.5(1a) or newer. Any cluster on an older version of HXDP will be skipped.


## Script Usage

`hx_vcenter_register.py -f <path to hx_vcenter_register_input.xlsx file>`

The below example shows the registration of two HyperFlex clusters using the script...the first shows a cluster that has a version of HXDP that is not supported, the second cluster shows a successful registration.

```
$> ./hx_vcenter_register.py

    USAGE: hx_vcenter_register.py -f <excel_data_file.xlsx>

$> hx_vcenter_register.py -f ./hx_vcenter_register_input.xlsx

--------------------------------------------------------------------------------------------
HyperFlex Cluster FQDN/IP: 10.1.25.13
HyperFlex Cluster UUID: 3029990785758872471:5276190994489465083
HyperFlex Cluster Version: 5.0.1a
vCenter Register API Supported: Yes
VMware Datacenter: rtp
VMware ESXi Cluster: Groot
vCenter Registration Status: Registered
Note: None

--------------------------------------------------------------------------------------------
HyperFlex Cluster FQDN/IP: 10.1.20.13
HyperFlex Cluster UUID: 1934524996551949088:5642413616398644456
HyperFlex Cluster Version: 4.0.2b
vCenter Register API Supported: No
vCenter Registration Status: Not Registered
Note: HyperFlex software version does not support vCenter registration API, must use "stcli cluster reregister" command
```