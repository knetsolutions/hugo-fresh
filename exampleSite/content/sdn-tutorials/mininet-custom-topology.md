---
title: Part3 - Mininet Custom Topology
sidebar: true
sidebarlogo: fresh-white-alt
---


<br><br>
{{% title4 "1. Writing Custom Topology in Mininet" %}}
<br>
mininet exposes the python API. We can create a custom topologies using the python API with few lines of code.  
<br>

{{% title5 "A. How to write Custom Topology in Mininet" %}}
<br>
Steps are below.
<br>

1. Import the python required libraries

<br>

``` 
from mininet.topo import Topo
from mininet.net import Mininet
```
<br>

2. Write the Topology definition class

<br>

``` 
 class SingleSwitchTopo(Topo):
    def build(self):
        s1 = self.addSwitch('s1')

        h1 = self.addHost('h1')
        h2 = self.addHost('h2')
        h3 = self.addHost('h3')
        h4 = self.addHost('h4')  

        self.addLink(h1, s1)
        self.addLink(h2, s1)
        self.addLink(h3, s1)
        self.addLink(h4, s1)
 ```
<br>


Important Topology definition APIs:

	addSwitch
	addHost
	addLink

<br>

3. Run the Topology as below,
 - Create the Topology object
 - Create the Mininet with Topology object
 - Start the Mininet

<br>

``` 
if __name__ == '__main__':
    topo = SingleSwitchTopo()
    c1 = RemoteController('c1', ip='127.0.0.1')
    net = Mininet(topo=topo, controller=c1)
    net.start()
```
<br><br>


{{% title4 "2. How to Run" %}}

<br>
1. start the RYU SDN Controller

```
ryu-manager ryu.app.simple_switch_13

```
<br>
2. Run the Mininet topology file

```
sudo python <topology file name>

```


<br><br>
{{% title5 "Continue with next part" %}}
<a href="/sdn-tutorials/testing-ipv6-in-mininet">Part4 - Testing IPv6 in Mininet</a>
<br>


