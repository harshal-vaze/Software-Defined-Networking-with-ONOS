# Software-Defined-Networking-with-ONOS

The aim of this thesis was to study the functionalities of software-defined networks and practically develop the real-world resembling environment in the network emulator environment to evaluate the performance of differ-ent SDN components.

With the advancement of software-defined networks, several network components were developed by different communities. The main component of the SDN architecture, SDN controller gained several production competi-tors for its development. Even though these controllers support the similar network services and try to overcome the same difficulties, many differences are observed in the development and functionality of the component. Few of the open-source SDN controllers well-known amongst researchers, developers, and commercial users gained more popularity because of being readily available, and flexible when it comes to self-developed chang-es and upgrades. These controllers gained more popularity also from the other communities for the software upgradation and modification from their base versions. Various SDN controllers were developed based on the framework designed by different controllers. These evolved versions of controllers were found to be rich in fea-tures and functionality along with solving the problems faced by the base controller. Other components of SDN such as software switches and their supported protocols also received several opponents for their development. Before implementing all these components of SDN in real-world networks, the detailed performance analysis of each component is crucial. To evaluate the functionality of SDN, various testbeds are available with promising real-world network resemblance in emulation environment. All these different aspects of SDN were researched over the course of this thesis.

********************************
## *Use Case-1: ONOS Controller with Isolated Layer 2 Overlay Networks*

The ONOS controller was examined with the Layer 2 VPN service VPLS to isolate the layer 2 overlay networks present in the same subnet. Different configuration methods were tested and the functioning of the VPLS application was evaluated in the first use case. The ONOS controller was able to read the configuration file via VPLS application and successfully install the forwarding flow rules on the created testbed of network devices.


![](VPLS.png)

********************************
## *Use Case-2: Cluster of Multiple ONOS Controllers*

To create the reliable SDN network, ONOS controller was analyzed with the distributed implementation of the ONOS controllers. In this use case, three ONOS controllers were deployed to form a cluster and control the underlying network. The communication within the cluster of controllers and distribution of network devices among themselves was evaluated in the second use case. Also, proof and validation of functioning failover of an instance of controller, network device and links between network devices was carried out to examine the resilience of the ONOS controller.


![](Cluster-1.png)

![](Cluster-2.png)

********************************
## *Use Case-3: ONOS Controller with IPv6 Addressing*
The ONOS controller was tested with IPv6 addressing scheme. This use case was evaluated with both IPv6 and IPv4 addressing scheme simultaneously and working of Neighbour discovery through OpenFlow protocol was studied. In addition, to answer the challenges faced by Internet Service Providers, the IPv6 enabled SDN network was deployed to demonstrate the IPv6 tunnelling over the IPv4 network which eventually help in migration of IPv4 based networks to IPv6 networks.


![](IPv6-1.png)

One of the issues faced by ISPs while migrating the network from IPv4 to IPv6 addressing scheme is integrating the IPv6 subnets with IPv4 subnets. Migrating a IPv4 addressing network to IPv6 addressing is not a single step process. The migration takes place in specific stages, beginning with developing small subnets of IPv6 addresses within the IPv4 network and progressively transferring all the services to IPv6 in the network. But during this transition, the IPv6 subnets should be able to communicate over the IPv4 infrastructure. The IPv6 subnets can be configured to transmit packets over IPv4 network by IPv6 over IPv4 tunnelling. IPv6 over IPv4 tunnels are point-to-point tunnels created by encapsulating IPv6 packets within IPv4 headers to carry them over IPv4 network.
In this use case, another network was implemented in GNS3 environment to test the functioning of ONOS con-troller for IPv6 over IPv4 tunnelling. The isolated IPv6 subnets were created and IPv4 network was configured between these subnets. The Open vSwitches and ONOS controller were located in the IPv4 network. The Cisco routers (Cisco IOS Software, 7200 Software (C7200-ADVENTERPRISEK9-M), Version 12.4(24)T5) were uti-lized to configure the IPv6 over IPv4 tunnels. 


![](IPv6-2.png)

********************************
## *Use Case-4: Integrating Software-defined Network with the Legacy Networks*

To illustrate the integration of SDN network with the legacy networks and evaluate routing with the ONOS controller, a fourth use case was implemented. In this use case, assessment of how routing information is exchanged between the networks via SDN-IP application using BGP was carried out. The process of migration from legacy-based networks to SDN network was examined which provides the feasible solution of migration to service providers.


![](SDN-IP.png)
