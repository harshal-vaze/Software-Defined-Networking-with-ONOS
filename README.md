# Software-Defined-Networking-with-ONOS

The aim of this thesis was to study the functionalities of software-defined networks and practically develop the real-world resembling environment in the network emulator environment to evaluate the performance of differ-ent SDN components.

With the advancement of software-defined networks, several network components were developed by different communities. The main component of the SDN architecture, SDN controller gained several production competi-tors for its development. Even though these controllers support the similar network services and try to overcome the same difficulties, many differences are observed in the development and functionality of the component. Few of the open-source SDN controllers well-known amongst researchers, developers, and commercial users gained more popularity because of being readily available, and flexible when it comes to self-developed chang-es and upgrades. These controllers gained more popularity also from the other communities for the software upgradation and modification from their base versions. Various SDN controllers were developed based on the framework designed by different controllers. These evolved versions of controllers were found to be rich in fea-tures and functionality along with solving the problems faced by the base controller. Other components of SDN such as software switches and their supported protocols also received several opponents for their development. Before implementing all these components of SDN in real-world networks, the detailed performance analysis of each component is crucial. To evaluate the functionality of SDN, various testbeds are available with promising real-world network resemblance in emulation environment. All these different aspects of SDN were researched over the course of this thesis.

********************************
## *Use Case-1: ONOS Controller with Isolated Layer 2 Overlay Networks*

In this use case ONOS controller was implemented with the VPLS L2VPN service. The aim was to connect mul-tiple end-users in an OpenFlow network to create the layer 2 broadcast overlay network. Virtually separate paths were created to isolate the traffic flow between the endpoints. VPLS application is by default included in the ONOS platform.

![](VPLS.png)

********************************
## *Use Case-2: Cluster of Multiple ONOS Controllers*

n this use case, a cluster of three ONOS controllers was formed and tested on the network. A single instance of ONOS installed on a virtual machine consumes 3-4 GB of RAM and a minimum of 3 CPUs, and due to limited availability of resources on the host machine, implementation of this use case was not possible using the stand-ard installation process. Hence, the ONOS controllers were installed on the Docker containers for this use case. Three Docker instances were created to build the cluster of three ONOS controllers. The network of Open vSwitches was created using the Mininet emulator.
ONOS is built to deploy the collection of servers, which can communicate with each other to perform the same tasks, distribute responsibilities, and control the same underlying network. The physically-distributed and logical-ly-centralised architecture of ONOS answers the problems of network scalability and high availability. The dis-tributed ONOS environment provides the fault-tolerance and resilience even if a controller instance from the cluster fails.


![](Cluster-1.png)

![](Cluster-2.png)

********************************
## *Use Case-3: ONOS Controller with IPv6 Addressing*

IPv6 was introduced in OpenFlow version 1.2 and some additional features were added in OpenFlow version 1.3. IPv6 address mechanism is supported by ONOS platform since version Blackbird 1.1.0. IPv6 feature is explicitly required to be configured on the ONOS controller. 
For testing the ONOS controller functionality with the IPv6 addressing this use case was implemented. In this use case, the network was created consisting of four Open vSwitches and four endpoints (hosts) in the GNS3 emula-tion software. The network was simultaneously tested for both IPv6 and IPv4 addressing scheme. The NAT interface was used to connect the Open vSwitches with the ONOS controller which was installed and running on VM outside the GNS3 environment. The following figure shows the implemented network consisting of four endpoints, two endpoints (H1 and H4) just using IPv6 addressing scheme and two endpoints (H2 and H3) using both IPv6 and IPv4 addressing scheme.

![](IPv6-1.png)

One of the issues faced by ISPs while migrating the network from IPv4 to IPv6 addressing scheme is integrating the IPv6 subnets with IPv4 subnets. Migrating a IPv4 addressing network to IPv6 addressing is not a single step process. The migration takes place in specific stages, beginning with developing small subnets of IPv6 addresses within the IPv4 network and progressively transferring all the services to IPv6 in the network. But during this transition, the IPv6 subnets should be able to communicate over the IPv4 infrastructure. The IPv6 subnets can be configured to transmit packets over IPv4 network by IPv6 over IPv4 tunnelling. IPv6 over IPv4 tunnels are point-to-point tunnels created by encapsulating IPv6 packets within IPv4 headers to carry them over IPv4 network.
In this use case, another network was implemented in GNS3 environment to test the functioning of ONOS con-troller for IPv6 over IPv4 tunnelling. The isolated IPv6 subnets were created and IPv4 network was configured between these subnets. The Open vSwitches and ONOS controller were located in the IPv4 network. The Cisco routers (Cisco IOS Software, 7200 Software (C7200-ADVENTERPRISEK9-M), Version 12.4(24)T5) were uti-lized to configure the IPv6 over IPv4 tunnels. 


![](IPv6-2.png)

********************************
## *Use Case-4: Integrating Software-defined Network with the Legacy Networks*

With the applications developed for ONOS controller, it supports the migration process of legacy networks to the SDN. ONOS controller is capable of performing and exchanging the routing information with the legacy routers using the SDN-IP application. SDN-IP is an ONOS application developed and implemented over ONOS control-ler to connect to the external networks on the legacy networks using the standard Border Gateway Protocol (BGP) [100]. The SDN network acts as an Autonomous System (AS) to the legacy routers in the network. The SDN network consists of Open vSwitches, ONOS controller and BGP-Speakers. BGP-Speakers are used to estab-lish the peering with the external gateway routers by acquiring route information from the ONOS controller. This configured SDN network serves as a transit network communicating with other legacy networks.
In this use case a SDN network was implemented in the GNS3 network emulator consisting of 8 Open vSwitches, one BGP-Speaker and the ONOS controller. The following figure displays the implemented network in GNS3 emulator. The ONOS controller was running inside the GNS3 emulator in this use case to set up the iBGP peering with the BGP-speaker (BGP-SP1). The eth0 management interfaces of all Open vSwitches were connected to the ONOS controller through a hub. Different Autonomous Systems were implemented (coloured ovals), each with one border gateway router and a host PC. 


![](SDN-IP.png)
