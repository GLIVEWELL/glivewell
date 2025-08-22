[TOC]

#### 解决方案整体架构

**GLIVEWELL™**解决方案整体架构基于云原生解决方案，分为如下几层：

```
+---------------------------------------------------+
|                     SaaS                          |
|   (软件即服务: any software based k8s：IoT，        |
|       blockchain、BigData etc)                    |
+---------------------------------------------------+
                        ▲
                        │
+---------------------------------------------------+
|                     PaaS                          |
|   (平台即服务: AAA、、Router(Istio)、CI/CD etc)      |
|                                                   |
+---------------------------------------------------+
                        ▲
                        │
+---------------------------------------------------+
|                     CaaS                          |
|   (容器即服务: Kubernetes)                          |
+---------------------------------------------------+
                        ▲
                        │
+---------------------------------------------------+
|                     IaaS                          |
|   (基础设施即服务: 计算、存储、网络，虚拟机、裸机)       |
+---------------------------------------------------+

```

#### GLIVEWELL™技术选型

##### IaaS技术选型

- 基于主流的openstack开源IaaS平台
- 存储采用分布式ceph
- openstack的网络技术基于OVN，利用网络技术提供IaaS平台的Load Balance方案

##### CaaS技术选型

- 基于主流的kubernetes开源平台
- CNI基于Cilium
- CSI基于openstack的CSI提供统一存储

##### PaaS技术选型

- Router基于Istio提供，并提供统一的微服务框架，替代Spring Cloud方案
- AAA基于IBM开源的keycloak方案
- CI/CD基于jenkins+Argo方案
- 集群管理基于Rancher统一管理
- 子集群基于Cluter API一键式生成和管理

##### SaaS技术选型

- 集成IoT，基于hono+thingsbox
- 集成blockchain，基于etherum/quorum/solana
- 集成大数据，基于zone/spark etc

