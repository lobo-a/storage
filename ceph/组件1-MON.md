# 概述

ceph monitor负责监控整个集群的监控状态。

他们以守护进程的形式存在

这些守护进程通过存储集群的关键信息来维护集群成员状态、对等节点状态，以及集群配置信息

## map种类

- MON map：它维护了节点间端到端的信息，其中包括ceph集群ID、Monitor主机名、IP地址、端口号。ceph mon dump
- OSD map：它存储了一些常见的信息，如集群ID、创建版本和最后一次修改信息、池相关的信息。ceph osd dump
- PG map：它存储了归置组的版本、时间戳、最新OSD map版本、容量充满的比列以及容量接近充满的比列等信息
- Crush map：它存储了集群的设备信息、故障层次结构、故障域中定义如何存储数据的规则。ceph osd dump
- MDS map：它存储了当前MDS map的版本、map的创建和修改时间，数据和元数据池的ID，集群中MDS的数目、MDS的状态。ceph mds dump
