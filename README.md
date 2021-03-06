# lvs-dpdk

This project has ported LVS-FULLNAT to OpenFastPath(base on odp-dpdk).

LVS-FULLNAT origin source code is from https://github.com/alibaba/LVS

OpenFastPath source code is on https://github.com/lvsgate/ofp.git

# Build steps
##1. Get and compile OpenFastPath
    The ofp depend on odp-dpdk (https://git.linaro.org/lng/odp-dpdk.git) 
    See the documents on https://github.com/lvsgate/ofp.git
    I have compiled and tested it on centos 7.2

## 2. Compile ofp_vs 
		cd $(topdir)/ofp/examples/ofp_vs
		make

## 3. Get lvs-dpdk source code
		git clone https://github.com/lvsgate/lvs-dpdk.git

## 4. Compile keepalived
  	cd $(topdir)/lvs-dpdk/tools/keepalived
		./configure
		make
		make install

## 5. Compile ipvsadm
		cd $(topdir)/lvs-dpdk/tools/ipvsadm
		make
		make install
		
## 6. Configure ofp_vs
    Edit ofp_vs/ofp.conf
    
## 7. Run ofp_vs
    ./start.sh

## 8. Telnet and Configure network
    telnet localhost 2345
    type in help for more infomation


## 9. Use ipvsadm and keepalived to configure virtual server on ofp_vs
    The usage is unchanged.
    ipvsadm and keepalived will comunicate with ofp_vs process but not the kernel module.

## 10. More details
    http://www.openfastpath.org/
    http://opendataplane.org/
    https://github.com/OpenFastPath/ofp
