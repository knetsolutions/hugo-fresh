---
title: PART1 - Mininet Introduction
sidebar: true
sidebarlogo: fresh-white-alt
---

{{% title5 "Mininet creates a realistic virtual network, running real kernel, switch and application code, on a single machine (VM, cloud or native), in seconds, with a single command 'mn'." %}}

{{< figure src="/mininet/mininet_1.png" >}}


<br><br>
{{% title4 "1. Installation" %}}


O.S :  UBUNTU 18.04


<br>
{{% title5 "A. RYU installation" %}}


```
sudo pip install ryu
```
<br>

To verify :

```
ryu-manager --version
```

Example:

```
suresh@suresh-vm:~$ ryu-manager --version
ryu-manager 4.31
suresh@suresh-vm:~$ 
```
<br>

Note: Make sure you do with "sudo pip install ryu" . ryu package will install ryu-manager binary in /usr/local/bin folder. Hence installation requires sudo access. 

<br><br>


{{% title5 "B. Mininet installation" %}}



```
sudo apt-get install mininet
```

To verify :

```
mn --version
```

Log:

```
suresh@suresh-vm:~$mn --version
2.2.2
suresh@suresh-vm:~$ 
```
<br><br>


{{% title4 "2. Basic Topologies" %}}
<br>
{{% title5 "A. Single Topology" %}}

Topology with Single Switch and 4 Nodes.

{{< figure src="/mininet/simple_topology.png" >}}



RYU SDN Controller 

```
ryu-manager ryu.app.simple_switch_13
```

Mininet Topology

```
sudo mn --controller=remote,ip=127.0.0.1 --mac -i 10.1.1.0/24 --switch=ovsk,protocols=OpenFlow13 --topo=single,4
```


|  options    |    Description                                                        |
|-------------|-----------------------------------------------------------------------|
|--controller | type of controller local/remote and remote controller ip.             |
|             |  																	  |
|--mac        | mac address starts with 00:00:00:00:00:01							  |
|             |																		  |
|-i           | IP Subnets for the Topology 										  |
|             |																		  |
|--switch     | Switch type (ovsk - openvswitch kernel module), and openflow version. |
|             |																		  |
|--topo       | topology type(linear,minimal,reversed,single,torus,tree) and params.  |



Once you are done, make sure "exit" the mininet shell,
>exit

Example:

```
mininet> exit
*** Stopping 1 controllers
c0 
*** Stopping 4 links
....
*** Stopping 1 switches
s1 
*** Stopping 4 hosts
h1 h2 h3 h4 
*** Done
completed in 2.604 seconds
suresh@suresh-vm:~$ 
```

<br><br>
{{% title5 "B. Linear Topology" %}}

linear topology (where each switch has one host, and all switches connect in a line)

{{< figure src="/mininet/linear_topology.png" >}}

```
sudo mn --controller=remote,ip=127.0.0.1 --mac -i 10.1.1.0/24 --switch=ovsk,protocols=OpenFlow13 --topo=linear,4
```
<br><br>

{{% title5 "B. Tree Topology" %}}

{{< figure src="/mininet/tree_topology.png" >}}

```
sudo mn --controller=remote,ip=127.0.0.1 --mac -i 10.1.1.0/24 --topo=tree,depth=2,fanout=3

```

fanout : each switch is connected to these many childs
depth : depth of the tree

<br><br>

{{% title4 "3. Mininet Basic Shell Commands" %}}
<br>
{{% title5 "Informative commands" %}}

```
help
dump
net
links
```

{{% title5 "Action commands" %}}

```
pingall
```



{{% title5 "Execute the commands in HOST/Node" %}}


Option1:
<br>

we can login to each host using 'xterm' command

```
mininet>xterm h1
```

It will open a xterm terminal for the host. Now we can execute the command inside that terminal


Option2:
<br>
we can directly execute from the mininet shell. 

```
mininet><hostname> command
```

Example:

```
mininet>h1 ifconfig
mininet>h1 ping h2
mininet>h1 ip route
```

we can use either method to run the Traffic tests or executing the commands.
<br><br>
{{% title5 "Continue with next part" %}}
<a href="/sdn-tutorials/mininet-traffic-tests">Part2 - Running Traffic Tests</a>
<br>
