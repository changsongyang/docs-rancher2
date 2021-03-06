---
title: 管理节点模版
description: 在新节点上启动集群时，需要用到创建集群内的节点。每个节点都是一台主机。这些模板使用 Docker Machine 支持的配置选项来定义主机操作系统镜像和主机配置。创建节点模板的方式有两种：创建节点池集群的同时，创建节点模板；或通过 UI 界面菜单栏的用户设置，创建节点模板。
keywords:
  - rancher 2.0中文文档
  - rancher 2.x 中文文档
  - rancher中文
  - rancher 2.0中文
  - rancher2
  - rancher教程
  - rancher中国
  - rancher 2.0
  - rancher2.0 中文教程
  - 用户设置
  - 管理节点模版
---

## 概述

[在新节点上启动集群](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index)时，需要用到[节点模板](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index#节点模板)创建集群内的节点。每个节点都是一台主机。
这些模板使用 Docker Machine 支持的配置选项来定义主机操作系统镜像和主机配置。创建节点模板的方式有两种：

- 创建节点池集群的同时，创建节点模板，详情请参考[创建带有节点池的集群](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index)。
- 通过 UI 界面菜单栏的[用户设置](#通过用户设置创建节点模板)，创建节点模板。

节点模板与用户绑定，用户之间不可共享节点模板。当您不再使用某些节点模板时，您可以通过**用户设置**删除这些模板。

> 提示：
> _自 v2.3.3 起可用_
> 系统管理员可以控制所有节点模板。系统管理员现在可以在 Rancher 中维护所有节点模板。当节点模板所有者不再使用 Rancher 时，系统管理员可以管理由它们创建的节点模板，因此可以继续更新和维护集群。

## 通过用户设置创建节点模板

1. 进入用户设置页面，单击页面右上方的 **用户头像**，选择 **节点模板**。
1. 单击**添加模板**。
1. 选择云服务提供商，按照页面提示配置节点模板。

**结果：**创建了一个节点模板，完成节点模板配置。[创建支持节点池的集群](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index)时，可以使用这个模板。

## 更新节点模板

1. 进入用户设置页面，单击页面右上方的 **用户头像**，选择 **节点模板**。
1. 选择需要更新的节点，单击 **... > 编辑**。

   > **说明：** 在 v2.2.0 版本中，默认状态为`active` 的[节点驱动](/docs/rancher2/admin-settings/drivers/node-drivers/_index)，和节点模板中有字段被标记为`password`的节点驱动，必须使用[云凭证](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index#cloud-credentials)。如果您使用的 Rancher 是 v2.2.0 之前的版本，升级到 v2.2.0 后，原有的节点模板不会受到这条规则约束，仍然可以正常使用。但是当您更新这些节点模板时，您需要创建云凭证。完成模板更新后，这些节点模板使用云凭证。

1. 更新模板信息，单击**保存**，完成修改。

**结果：** 完成节点模板更新。在使用该节点模板的节点池中添加节点时，节点池会自动使用更新后的模板。

## 克隆节点模板

创建节点模板的时候，您可以克隆已有的节点模板，然后在这个模板的基础上修改参数。相较从头开始创建模板而言，这种方式更加简单快捷。请参考以下步骤克隆节点模板。

1. 进入用户设置页面，单击页面右上方的 **用户头像**，选择 **节点模板**。
1. 选择需要克隆的节点，单击 **... > 克隆**。
1. 填写表格上所需的其他信息。

**结果：**成功克隆了一个节点模板，完成了该模板的配置更新。您可以使用这个模板[创建支持节点池的集群](/docs/rancher2/cluster-provisioning/rke-clusters/node-pools/_index)。

## 删除节点模板

您不再使用某个节点模板的时候，可以在用户设置页面删除节点模板。

1. 进入用户设置页面，单击页面右上方的 **用户头像**，选择 **节点模板**。
1. 勾选一个或多个节点模板，单击**删除**。页面弹出确认是否删除的信息后，单击**确认**，完成删除。
