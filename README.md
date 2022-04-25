# HyperFlex vCenter Server Registration Script

## Purpose:
This script will register one or more Cisco HyperFlex clusters with a VMware vCenter server of your choosing. The registration process adds an extension to VMware vCenter and serves as the integration point between Cisco HyperFlex and VMware vCenter.

## Files:
hx_vcenter_register.py - the python script which performs the regsitration operation(s) via Cisco HyperFlex APIs
hx_vcenter_register_input.xlsx - excel spreadsheet which is used to provide the inputs required for the registration operation(s). This is particularly useful when multiple Cisco HyperFlex clsuters need to be registered with VMware vCenter.
requirements.txt - a file which provides the python pacakage dependencies required to run the "hx_vcenter_register.py" python script.