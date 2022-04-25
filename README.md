# HyperFlex vCenter Server Registration Script

## Purpose
This script will register one or more Cisco HyperFlex clusters with a VMware vCenter server of your choosing. The registration process adds an extension to VMware vCenter and serves as the integration point between Cisco HyperFlex and VMware vCenter.


## Files
`hx_vcenter_register.py` - the python script which performs the registration operation(s) via Cisco HyperFlex APIs

`hx_vcenter_register_input.xlsx` - excel spreadsheet which is used to provide the inputs required for the registration operation(s). This is particularly useful when multiple Cisco 
HyperFlex clsuters need to be registered with VMware vCenter. Fill in the HyperFlex cluster information and VMware vCenter information in this spreadsheet, each row represents a different HyperFlex Cluster and corresponding VMware vCenter server.

`requirements.txt` - list of python pacakage dependencies required to run the "hx_vcenter_register.py" python script. Use can use python pip to install these dependencies by using the command `pip install -r requirements.txt`.


## Script Usage
`hx_vcenter_register.py -f *<path to hx_vcenter_register_input.xlsx file>*`