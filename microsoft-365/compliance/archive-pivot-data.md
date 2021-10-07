---
title: 设置连接器以在数据透视表中存档Microsoft 365
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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自 Microsoft 365。 此连接器允许您存档 Microsoft 365 中第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: d4b5a81bb8a940e9680e1c0cfbd914b28d1df6e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194521"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>设置连接器以存档透视数据

使用数据透视表中的 Microsoft 365 合规中心 连接器将数据从透视平台导入并存档到组织Microsoft 365邮箱。 对于配置为定期捕获第三[](https://globanet.com/pivot/)方数据源 (中的项目) 然后将这些项导入第三方数据源 Microsoft 365。 Pivot 是一个即时消息平台，允许与金融市场参与者进行协作。 连接器将聊天消息等项目从用户的透视帐户转换为电子邮件格式，然后将这些项目导入 Microsoft 365。

将透视数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用透视连接器在数据透视表中导入和存档Microsoft 365可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-pivot-data"></a>存档数据透视表数据概述

以下概述介绍使用连接器在数据透视表中存档数据Microsoft 365。

![透视数据的存档工作流。](../media/PivotConnectorWorkflow.png)

1. 组织使用 Pivot 来设置和配置透视源网站。

2. 每 24 小时复制一次透视表项，然后复制到该"中""合并 1"网站。 连接器还会将透视表项目转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的数据透视连接器每天连接到一次"Microsoft 365 合规中心"网站，将透视项目传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将透视项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Pivot** 的收件箱文件夹中的子文件夹，项目将导入该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每个透视表项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 中创建数据透视 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，不会向角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-pivot-connector"></a>步骤 1：设置透视表连接器

第一步是访问 Microsoft 合规中心中的"数据连接器"页面，并创建用于透视数据的连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""**  >  **透视"。**

2. 在"**数据透视表** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>步骤 2：在"完成"合并 1 网站中配置透视连接器

第二步是在 Merge1 网站上配置透视连接器。 若要了解如何在"一线合并 1"网站上配置透视连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 356 合规中心中的连接器设置，请按照以下步骤操作：

1. 在"**将透视用户映射到Microsoft 365"页上**，启用自动用户映射。 透视表项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-pivot-connector"></a>步骤 4：监视透视表连接器

创建透视表连接器后，可以在数据透视表中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **透视表连接器** 以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。