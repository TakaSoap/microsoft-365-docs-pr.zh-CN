---
title: 设置连接器以将 Jive 数据存档到Microsoft 365
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
description: 管理员可以设置连接器，以导入和存档来自 Microsoft 365 中来自 Microsoft 365。 此连接器允许您在 Microsoft 365中存档第三方数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: b2842d3d9dff71292b5ff47e62b1915850106e42
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170693"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>设置连接器以存档 Jive 数据

使用协作平台中的 Microsoft 365 合规中心 连接器，将数据从协作平台导入并存档到组织Microsoft 365邮箱。 该连接器配置为定期[](https://globanet.com/jive/)捕获第三方数据源 (中的项目，) 然后将这些项目导入Microsoft 365。 连接器将用户 Jive 帐户中的电子邮件、聊天和附件等内容转换为电子邮件格式，然后在 Microsoft 365 中将这些项目导入用户邮箱。

Jive 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Jive 连接器导入数据并存档数据Microsoft 365有助于组织遵守政府法规策略。

## <a name="overview-of-archiving-jive-data"></a>存档 Jive 数据概述

以下概述介绍使用连接器在数据记录中存档 Jive 数据Microsoft 365。

![Jive 数据的存档工作流。](../media/JiveConnectorWorkflow.png)

1. 你的组织与 Jive 一起设置和配置 Jive 网站。

2. 每 24 小时一次，Jive 中的项目将复制到"改进"合并 1 网站。 连接器还会将 Jive 项目的内容转换为电子邮件格式。

3. 在 Microsoft 云中创建的 Jive 连接器Microsoft 365 合规中心连接到 Microsoft 云中的一个安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Jive** 的收件箱文件夹中的新子文件夹，项目将导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个 Jive 项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 (步骤 1 中创建 Jive 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，不会向角色组分配此角色Exchange Online。 可以将邮箱导入导出角色添加到组织管理角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-jive-connector"></a>步骤 1：设置 Jive 连接器

第一步是访问数据连接器页，Microsoft 365 合规中心 Jive 数据创建连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Jive**。

2. 在 **"Jive** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-jive-connector"></a>步骤 2：配置 Jive 连接器

第二步是在 Merge1 网站上配置 Jive 连接器。 若要了解如何配置 Jive 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。

单击"保存 **&完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将 Jive 用户映射到Microsoft 365页上**，启用自动用户映射。 Jive 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-jive-connector"></a>步骤 4：监视 Jive 连接器

创建 Jive 连接器后，可以查看连接器在连接器Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **Jive** 连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。