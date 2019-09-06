---
title: Mininet Basics
sidebar: true
sidebarlogo: fresh-white-alt
---

1. To check the mininet version

```
mn --version
```

2. To clean up the existing ovs bridges and namespaces

Note: sometime we mistakenly closed the mininet shell, or mininet crashed. But the topology components will continue to exists. To clean such stuff, cleanup command is used.