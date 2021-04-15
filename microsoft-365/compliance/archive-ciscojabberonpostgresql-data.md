---
title: 设置连接器以在 Microsoft 365 中存档 PostgreSQL 数据上的 Cisco Jabber
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 了解如何在 Microsoft 365 合规中心设置和使用连接器，以将数据从 PostgreSQL 上的 Cisco Jabber 导入和存档到 Microsoft 365。
ms.openlocfilehash: 47cd3c7e9d3717426fbcf43bf1b0df16bbe2cf80
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767073"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a>设置连接器以在 PostgreSQL 数据上存档 Cisco Jabber， (预览) 

使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Cisco Jabber 平台导入并存档到 Microsoft 365 组织的用户邮箱。 Microsoft 在 [PostgreSQL](https://www.veritas.com/insights/merge1/jabber) 连接器上提供了 Cisco Jabber，配置为定期捕获第三方数据源 (中的项目) 将这些项目导入到 Microsoft 365。 连接器将内容（如消息、聊天和共享内容）从 PostgreSQL 上的 Cisco Jabber 转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

在 PostgreSQL 上的 Cisco Jabber 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 PostgreSQL 连接器上的 Cisco Jabber 在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>对 PostgreSQL 数据存档 Cisco Jabber 概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 PostgreSQL 数据上的 Cisco Jabber 的过程。

![针对 PostgreSQL 数据的 Cisco Jabber 存档工作流](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. 贵组织与 PostgreSQL 上的 Cisco Jabber 合作，在 PostgreSQL 网站上设置和配置 Cisco Jabber。

2. 每 24 小时一次，PostgreSQL 项上的 Cisco Jabber 将复制到位于以下位置的 Cisco Merge1 网站： 连接器还将 PostgreSQL 项上的 Cisco Jabber 转换为电子邮件格式。

3. 在 Microsoft 365 合规中心创建的 PostgreSQL 连接器上的 Cisco Jabber 每天连接到一个 Microsoft Merge1 网站，将 Jabber 内容传输至 Microsoft 云中的安全 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 PostgreSQL 上名为 **Cisco Jabber** 的收件箱文件夹中的子文件夹是在用户邮箱中创建的，并且项目会导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个 Jabber 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Merge1 帐户。 若要进行此操作，请联系["用户支持人员"。](https://www.veritas.com/content/support/en_US) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须将在步骤 1 (中的 PostgreSQL 连接器上创建 Cisco Jabber 并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中任何角色组。 可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>步骤 1：在 PostgreSQL 连接器上设置 Cisco Jabber

第一步是访问 Microsoft 365 合规中心的"数据连接器"页面，并创建用于 Jabber 数据的连接器。 

1. 转到 <https://compliance.microsoft.com>  &gt; **PostgreSQL，然后单击"数据连接器""Cisco Jabber"。**

2. 在 **PostgreSQL 产品说明页上的 Cisco Jabber 上**，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>步骤 2：在位于百度合并 1 网站的 PostgreSQL 上配置 Cisco Jabber

第二步是配置位于以下位置的 Cisco Jabber：位于"一线"上的"Iss Merge1"站点上的 PostgreSQL 连接器。 若要了解如何在 PostgreSQL 连接器上配置 Cisco Jabber，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：

1. 在 **PostgreSQL 用户映射到 Microsoft 365 用户的"将 Cisco Jabber 映射到 Microsoft 365** 用户"页上，启用自动用户映射。 PostgreSQL 项上的 Cisco Jabber 包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>步骤 4：监视 PostgreSQL 连接器上的 Cisco Jabber

在 PostgreSQL 连接器上创建 Cisco Jabber 后，可以在 Microsoft 365 合规中心查看连接器状态。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **PostgreSQL** 连接器上的 Cisco Jabber 以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目，但稍后会提供对较大项目的支持。
