---
title: Part2 - Mininet Traffic Tests
sidebar: true
sidebarlogo: fresh-white-alt
---

{{% title4 "1. TCP Traffic Tests" %}}
<br>






{{% title5 "A. Start the Mininet Topology" %}}

<br>
{{< figure src="/mininet/linear_topology.png" >}}
<br>

```
sudo mn --controller=remote,ip=127.0.0.1 --mac -i 10.1.1.0/24 --switch=ovsk,protocols=OpenFlow13 --topo=linear,4  -x
```

<br>

{{% title5 "B. Run the IPERF TCP Server" %}}

<br>
```
h2 iperf -s

```
-s means server mode

<br>

{{% title5 "C. RUN IPERF TCP Client" %}}

<br>

```
h1 iperf -c 10.1.1.4 -i 10 -t 30
h1 iperf -c 10.1.1.4 -i 10 -b 10m -t 30
h1 iperf -c 10.1.1.4 -i 10 -P 10 -t 30

```
<br>
-c means client mode.

-i means reporting interval

-t means test duration in seconds

-b means bandwidth 10m means 10Mbps

-P means parallel connections
<br><br>

{{% title4 "2. UDP Traffic Tests" %}}
<br>
{{% title5 "A. Run the IPERF UDP Server" %}}

```
iperf -u -s 

```
-u means udp 
<br>
{{% title5 "B. RUN IPERF UDP Client" %}}

```
iperf -u -c 10.1.1.4 -b 10m -i 10 -t 30
iperf -u -c 10.1.1.4 -b 10m -i 10 -P 10 -t 30

```
-b means bandwidth 10m means 10Mbps
<br><br>




{{% title4 "3. HTTP Tests" %}}

<br>
Run Python Simple Web Server in h4
<br>

```
python -m SimpleHTTPServer 80

```
<br>
From H1, Access the Web server

```
curl http://10.1.1.4/

```
<br>
curl utility used as web client to access the web server. 


If we want to simulate the 1000s users accessing the web server on the same time (load), we can use ab(apache bench) tool
<br>
```
ab -n 500 -c 50 http://10.1.1.4/
```

-c  50  means parallel request per second (50 Requests per second)

-n 500  means total request for this test (500 requests)


Apache bench tool have lot more options , More details can be found from the below link

https://httpd.apache.org/docs/2.4/programs/ab.html
<br>
<br>


{{% title5 "Continue with next part" %}}
<a href="/sdn-tutorials/mininet-custom-topology">Part3 - Writing Custom Topology</a>
<br>