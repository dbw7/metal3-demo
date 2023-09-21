# This directory contains the scripts for the automated deployment of Metal3 as well as virtual bare metal hosts.

## This scripts are specific to fresh Equinix Ubuntu 22.04LTS servers. The scripts will fail with other network or resource configurations.
- m3.small.x86 is the weakest configuration that will support the Metal3 deploy, but not recommended if deploying virtual bare metal hosts.
- c2.medium.x86 will support a Metal3 deploy with several virtual bare metal hosts.

### The quickest setup for Metal3 is to deploy an Equinix server with the previously mentioned configurations, then run the following commands below which will automate the entire deployment.


1. The following commands deploy Metal3
```
cd ~; git clone https://github.com/suse-edge/metal3-demo.git
cd ~/metal3-demo/scripts/bash-scripts/
```
To deploy Metal3 without Sylva enabled, run:
```
./m3.sh
```
To deploy Metal3 with Sylva enabled, pass the `-s` flag like so:
```
./m3.sh -s
```

2. This script creates 3 virtual bare metal hosts and then provisions them.
```
cd ~/metal3-demo/scripts/bash-scripts/
./vm.sh
```