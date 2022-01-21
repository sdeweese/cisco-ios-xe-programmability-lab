# Welcome to the Cisco IOS XE Programmablity Lab

## Version 17.7 SEVT

[Looking for the previous version of the lab?](https://github.com/jeremycohoe/cisco-ios-xe-programmability-lab)

# Lab Introduction
To access the lab, you will need to use a Remote Desktop connection to the specific jump host. The jump host is used to allow remotes access into all lab devices within the given pod envrionment.

The services, features, and technologies that are enabled with the lab envrionment are shown below:

![](./imgs/pod_details.png)

The modules below enable IOS XE Device Lifecycle Management:

![](./imgs/device_lifecycle.png)

# Lab Modules

Lab modules can be completed in any order. Mark the lab completed in the [SmartSheet](https://app.smartsheet.com/b/form/134240eac2d84a57acd4efc24fd8f3d0) form once you have successfully completed each module. 

## [YANG Suite Module](YANG_Suite.md)

[YANG Suite](https://github.com/CiscoDevNet/yangsuite) is HTML5 based tooling that is available for working with the YANG based programmable interfaces on Cisco IOS XE, XR, and NX Network Operating Systems. It has plugins that allow for interacting with the programmable interfaces and supports downloading YANG files directly from network devices.



## [Terraform Module](Terraform.md)
Terraform is a cloud native, open-source infrastructure provisioning tooling similar to Ansible. IOS XE Terraform utilizes RESTCONF + YANG to configure devices using a single binary file. Terraform is declarative, meaning that it defines the desired state. It has commercial support from HashiCorp.



## [CLI to YANG Module](CLI2YANG.md)
CLI to YANG is an IOS XE feature that converts currently configured features to either XML to use with NETCONF or JSON to use with RESTCONF.



## [gNOI reset.proto Module](gNOI_reset_proto.md)
Reset.proto also known as the Factory Reset API is the latest addition to the gNOI operations interface within the gNMI.

The factory reset API as described at [openconfig/gnoi](https://github.com/openconfig/gnoi/blob/master/factory_reset/​) with tooling from [google/gnxi](https://github.com/google/gnxi/tree/master/gnoi_reset).



# Feedback
 Mark the lab completed and provide any feedback and comments in the [SmartSheet](https://app.smartsheet.com/b/form/134240eac2d84a57acd4efc24fd8f3d0) form once you have successfully completed the modules above. 
