---
title: Mininet Cluster
sidebar: true
sidebarlogo: fresh-white-alt
---

{{< figure src="/mininet/cluster_header.jpg" >}}



{{% title3 "1. Introduction" %}}

Generally we use mininet to simulate the topology in a single system/computer/virutal machine. The System resources limits our topology size.

Suppose, we want to build the large topology with 1000s of switches and nodes. We cannot build this topology in single system. The solution is, we can build the subset of the topology in mulitiple systems and connect each other system via GRE Tunnel.

<br>

{{% title3 "2. Demonstration" %}}

Lets take the simple topology and demonstrated on deploying on two VMs, interconnect the topology and ping the nodes.

This is original topology.

{{< figure src="/mininet/cluster1.jpg"  >}}

The deployment model of this topology is as below.

{{< figure src="/mininet/cluster2.jpg"  >}}


<ul>

<li>1. We are going to split the original topology in to two small topologies.</li>
<br>
<li>2. In our diagram, S1, h1, h2 will be considered as topology1, will be  deployed in computer1.</li>
<br>
<li>3. S2, h3, h4 will be considered as topology2, will be deployed in computer2.</li>
<br>
<li>4. We must note down the IP Address of the both computers for establishing GRE Tunnel.  This IP Address details will be used in the topology file.</li>
<br>
<li>5. The example topology files can be downloaded from here. (Computer1 IP : 192.168.122.1,  Computer2 IP: 192.168.122.2)
<br>

<a href="/files/cluster_topo1.py.txt">Topology1</a>
<br>
<a href="/files/cluster_topo2.py.txt">Topology2</a>

<br>

</li>
<br>
<li>6. Both topology is connected to the one RYU SDN controller (we run RYU SDN controller on computer1).</li>
<br>

</ul>


{{% title4 "In Computer1" %}}


1. Start the RYU SDN Controller with simple switch application

```
ryu-manager ryu.app.simple_switch_13
```


2. Start the mininet topology
```
sudo python cluster_topo1.py
```
<br>
s
{{% title4 "In Computer2" %}}

1. Start the mininet topology
```
sudo python cluster_topo2.py
```
2. From computer1 mininet shell, ping h1, h2, h3, h4 host IPs.

3. you can also verify the GRE interface of both computers using "ifconfig" command.
