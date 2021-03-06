# Intro

This is a vagrant environment for demoing the SSVMEthernet (Shared memory ethernet) functionality in FD.IO's VPP.

The demo will walk you through setting up two docker containers, running VPP within them and then communicating between them using the SSVMEthernet interface.

![SSVMEthernet Demo Setup](./ssvm_demo.png)

## Note
The demo has been updated to use the AF_PACKET interface between VPP and the linux kernel (in each NetNS / Container).
Demo2 still uses the original TUN/TAP style configuration. However AF_PACKET is known to be more performant. By Default, please use demo3.

# Use

```
https://github.com/matjohn2/fdio-ssvmethernet-demo.git
cd fdio-ssvmethernet-demo
vagrant up
vagrant ssh

vagrant$ /vagrant/demo3.sh
```

The demo script will walk you through the rest.

# Prerequisites
* vagrant installed on your local machine
* Virtualbox installed on your local machine

### VM PARTICULARS:

By default, the VM created is/has:
- Ubuntu 14.04
- 2 vCPUs
- 4G of RAM
- 2 NICs (1 x NAT - host access, 1 x VPP DPDK enabled)
