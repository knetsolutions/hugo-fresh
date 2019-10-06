---
title: Software Defined Networking (SDN) Project Ideas
draft: false
---


{{% title3 "1. Addressing the Flow table fullfill(flow table exhaust) issue" %}}
In Hardware Openflow switches, Flow table suffers from the limited storage due to the use of TCAM — on which the flow table is realized in the majority of existing equipments in industry to achieve fast forwarding. As a result, after the flow table is full filled, the switch behavior is unexpected on both forwarding and control plane.

The reason of the fast flow entry occupation is due to the fine-grained flow entry storage of SDN.Flow tables to be monitored regurlarly and updated with fine-grained to coarse-grained flows, which should reduce the number of flows drastically .

<br>

{{% title3 "2. DDoS Detection/Mitigation" %}}
Early detection of DDoS, and mitigation is challenging and ongoing research activity in SDN security area.

<br>

{{% title3 "3. Policy based Forwarding" %}}
Policy based forwarding enables the network wide policy, which controls the service access based on various policy parameters such as time bounded, application specific, user specific.

For Example: -user1 allow to access Internet without any limitation -user2 allow to access Internet only morning 8AM to 10AM, daily -user3 allow to use the webservice(port 80) from WebServer-A -user4 can access user1,2 machines. -All other access requests are denied such policy can be defined and modified. 

<br>



{{% title3 "4.SDN BGP Speaker usecases in hybrid networks" %}}
Some of usecase/research topics are below,

- SDN BGP Router
- BGP Load balancing/Multipath
- Addressing BGP Prefix/Route Hijacking issues
references: https://en.wikipedia.org/wiki/BGP_hijacking

<br>

{{% title3 "5. QoS SDN Networks" %}}

- Bandwidth allocation/reservation for VOIP Traffic
- Dynamic bandwidth allocation
- DSCP Marking & Queuing based usecases
- QoE
- Bandwidth optimization

<br>

{{% title3 "6. Firewall Implementation" %}}

- Stateful(TCP) firewall
- ARP Inspector(To prevent ARP Poisoning, Man in the Middle attack)
- DNS Defender

<br>


{{% title3 "7. Multicontroller environment" %}}

- Building Fault Tolerance, Scalable, High available Multicontroller environemnt
- Data Synchoranization in Multicontroller environment
- Master/Slave role selection in distributed Multicontroller environment

<br>


{{% title3 "8. SDN Controller security issues" %}}
Compromised/hijacked/malfunctioned controller breaks the network topology. Identifying and removing the compromised controller is an intersting topic.


<br>

{{% title3 "9. Multipath/Loadbalancing in Datacenter topology" %}}
To be updated


{{% title3 "10. Segment Routing (MPLS)" %}}
To be updated
