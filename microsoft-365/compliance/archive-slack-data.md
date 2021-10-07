---
title: 设置连接器以将 Slack 电子数据展示数据存档在 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理员可以设置连接器，以将数据从 Slack 电子数据展示导入和存档到Microsoft 365。 通过此连接器，可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 793cff875db8e328ce44278fbf8caa909c309612
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192327"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>设置连接器以存档 Slack 电子数据展示数据

使用 Microsoft 365 合规中心 中的一个 Microsoft 365 合规中心 将社交媒体、即时消息和文档协作平台的第三方数据导入和存档到 Microsoft 365 组织中。 对于[第三方](https://globanet.com/slack/)数据源 (中定期捕获项目，然后) 将这些项目导入到第三方数据源 Microsoft 365。 Slack 从 Slack API 提取邮件和文件，并将其转换为电子邮件格式，然后将项目导入到用户邮箱。

Slack 电子数据展示数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Slack 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>存档 Slack 电子数据展示数据概述

以下概述介绍使用连接器在资源库内存档 Slack Microsoft 365。

![Slack 存档工作流。](../media/SlackConnectorWorkflow.png)

1. 你的组织与 Slack 一起设置和配置 Slack 网站。

2. 每 24 小时一次，Slack 电子数据展示中的聊天消息会复制到"改进"功能合并 1 网站。 连接器还会将聊天消息的内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 中创建的 Slack 电子数据展示连接器每天连接到 Microsoft 云中的一个安全 Azure 存储 位置，并连接到 Microsoft Merge1 网站。

4. 连接器使用 *Email* 属性的值和自动用户映射将转换后的聊天消息项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **Slack 电子** 数据展示的"收件箱"文件夹中的新子文件夹，聊天消息项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个聊天消息都包含此属性，该属性用聊天消息每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact) 在步骤 1 中创建连接器时，将登录到此帐户。

- 获取组织的 Slack 企业帐户的用户名和密码。 配置 Slack 时，需要在步骤 2 中登录此帐户。

- 必须在步骤 1 中创建 Slack 电子数据展示连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>步骤 1：设置 Slack 电子数据展示连接器

第一步是访问数据连接器页，Microsoft 365 合规中心 Slack 数据的连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Slack 电子数据展示**。

2. 在 **Slack 电子数据展示产品** 说明页面上，单击添加 **连接器**。

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-slack-ediscovery"></a>步骤 2：配置 Slack 电子数据展示

第二步是在 Merge1 网站上配置 Slack 电子数据展示连接器。 若要详细了解如何在"一线合并"网站上配置 Slack 电子数据展示连接器，请参阅 [Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)三方连接器用户指南。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

1. 在"**将外部用户映射到Microsoft 365"页上**，启用自动用户映射。

   Slack 电子数据展示项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>步骤 4：监视 Slack 电子数据展示连接器

创建 Slack 电子数据展示连接器后，可以在"数据展示"视图中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **Slack 电子数据展示连接器** 以显示飞出页面。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。