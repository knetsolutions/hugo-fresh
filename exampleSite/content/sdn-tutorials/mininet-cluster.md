---
title: Mininet Cluster
sidebar: true
sidebarlogo: fresh-white-alt
---

{{% title3 "1. Introduction" %}}

Generally we use mininet to simulate the topology in a single system/computer/virutal machine. The System resources limits our topology size.

Suppose, we want to build the large topology with 1000s of switches and nodes. We cannot build this topology in single system. The solution is, we can build the subset of the topology in mulitiple systems and connect each other system via GRE Tunnel.
