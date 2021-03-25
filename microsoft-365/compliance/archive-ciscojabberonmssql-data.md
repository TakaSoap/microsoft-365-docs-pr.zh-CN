---
title: 在 Microsoft 365 中设置连接器以在 MS SQL上存档 Cisco Jabber
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
ms.collection: M365-security-compliance
description: 管理员可以设置连接器以在 Microsoft 365 中导入和存档来自 Microsoft 365 的 Cisco Jabber 数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 7465d1f8d80d67e2a284200cbf1628178609b3c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164402"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>设置连接器以存档 Cisco Jabber 数据

使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Cisco Jabber 平台导入并存档到 Microsoft 365 组织的用户邮箱。 Microsoft 为您提供了一个 [Cisco Jabber](https://globanet.com/jabber/) 连接器，该连接器配置为从 Jabber 的 MS SQL 数据库中捕获项目，例如一对一聊天消息和群聊，然后将这些项目导入到 Microsoft 365。 连接器从 Cisco Jabber 的 MS SQL 数据库中检索数据，处理这些数据，并将内容从用户的 Cisco Jabber 帐户转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

Cisco Jabber 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Cisco Jabber 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-cisco-jabber-data"></a>存档 Cisco Jabber 数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Cisco Jabber 数据的过程。

![Cisco Jabber 数据的存档工作流](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 你的组织与 Cisco 合作，在 MS 数据库上设置和配置 Cisco Jabber SQL数据库。

2. Cisco Jabber 项目每 24 小时复制一次，从 MS SQL 数据库复制到其 Merge1 网站。 连接器还会将聊天消息的内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心内创建的 Cisco Jabber 连接器每天连接到 Microsoft Merge1 网站，将项目转移到 Microsoft 云中的安全 Azure 存储位置。

4. 作为连接器的自动用户映射使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述 *的 Email* 属性的值将项目导入特定用户的邮箱。 MS 邮箱上名为 **Cisco Jabber SQL** 文件夹的子文件夹是在用户邮箱中创建的，邮件项目将导入到该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Cisco Jabber 项都包含此属性，其中填充了每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，将登录到此帐户。

- 设置 MS SQL 数据库，以在步骤 1 中创建连接器之前从检索 Jabber 项目。 在步骤 2 中配置 Cisco Jabber 连接器时，SQL数据库的连接设置。 有关详细信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

- 必须在步骤 1 中创建 Cisco Jabber 连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>步骤 1：设置 Cisco Jabber 连接器

第一步是访问 Microsoft 365 合规中心内的数据连接器，在 MS 上为 Cisco Jabber 创建SQL连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击 MS 上的"数据 **连接器**  >  **""Cisco Jabber SQL"。**

2. On the **Cisco Jabber on MS SQL** product description page， click Add **connector**.

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-veritas-merge1-site"></a>步骤 2：在"Cisco Merge1"网站上配置 Cisco Jabber 连接器

第二步是在 Ms 上的 Cisco Jabber 配置 SQL Merge1 站点上的连接器。 若要了解如何在 MS 连接器上配置 Cisco Jabber SQL，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成在 Microsoft 365 合规中心中设置的连接器，请按照以下步骤操作：

1. 在 **MS 上的 Map Cisco Jabber SQL Microsoft 365** 用户"页面上，启用自动用户映射。 MS 上的 Cisco Jabber SQL包含一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>步骤 4：监视 Cisco Jabber 连接器

在 MS 连接器上创建 Cisco Jabber SQL后，可以查看 Microsoft 365 合规中心中的连接器状态。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 MS 连接器上的 **Cisco Jabber SQL** 显示该飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。