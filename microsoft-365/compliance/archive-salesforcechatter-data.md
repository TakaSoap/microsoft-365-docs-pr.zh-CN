---
title: 设置连接器以在 Microsoft 365 中存档 Salesforce Chatter 数据
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
description: 管理员可以设置连接器以将 Salesforce Chatter 数据从 Globanet 导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 518eb38756d86812a8b3d41e4bc2cd46d5a23386
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740309"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>设置连接器以存档 Salesforce Chatter 数据

使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 Salesforce Chatter 平台导入并存档到 Microsoft 365 组织的用户邮箱。 Globanet 提供了 [Salesforce Chatter](http://globanet.com/chatter/) 连接器，可捕获第三方数据源中的项目，并导入到 Microsoft 365。 连接器将内容（如聊天、附件和来自 Salesforce Chater 的帖子）转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

Salesforce Chatter 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 Salesforce Chatter 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。

## <a name="overview-of-archiving-salesforce-chatter-data"></a>存档 Salesforce Chatter 数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Salesforce Chatter 数据的过程。

![Salesforce Chatter 数据的存档工作流](../media/SalesforceChatterConnectorWorkflow.png)

1. 您的组织与 Salesforce Chatter 合作，以设置和配置 Salesforce Chatter 网站。

2. 每 24 小时一次，Salesforce Chatter 项目将复制到 Globanet Merge1 网站。 连接器还将 Salesforce Chatter 项目作为电子邮件格式。

3. 你在 Microsoft 365 合规中心创建的 Salesforce Chatter 连接器每天连接到 Globanet Merge1 网站，将聊天内容转移到 Microsoft 云中安全的 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Salesforce Chatter** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个聊天项目都包含此属性，此属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Merge1 帐户。 若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us/)。 在步骤 1 中创建连接器时，需要登录到此帐户。

- 创建 Salesforce 应用程序，并获取令牌 [https://salesforce.com](https://salesforce.com) 。 你将需要以管理员角色登录到 Salesforce 帐户，并获取用户个人令牌以导入数据。 此外，需要在聊天网站上发布触发器，以捕获更新、删除和编辑。 这些触发器将在频道上创建帖子，Merge1 将捕获来自频道的信息。 有关如何创建应用程序和获取令牌的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。

- 在步骤 1 (创建 Salesforce Chatter 连接器) 在步骤 3 中完成该连接器的用户必须分配给 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中任何角色组。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>步骤 1：设置 Salesforce Chatter 连接器

第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建用于聊天数据的连接器。 

1. 转到， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Salesforce Chatter。**

2. 在 **Salesforce Chatter** 产品说明页上，单击 **"添加连接器"。**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 输入标识连接器的唯一名称，然后单击"下一 **步"。**

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-salesforce-chatter-on-the-globanet-merge1-site"></a>步骤 2：在 Globanet Merge1 网站上配置 Salesforce Chatter

第二步是在 Globanet Merge1 网站上配置 Salesforce Chatter 连接器。 若要了解如何配置 Salesforce Chatter 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。

单击 **"保存**&完成"后，将显示Microsoft 365 合规中心连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：

1. 在 **"将 Salesforce Chatter 用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。 Salesforce Chatter 项目包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>步骤 4：监视 Salesforce Chatter 连接器

创建 Salesforce Chatter 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航 **中并** 单击"数据连接器"。

2. 单击 **"连接器"** 选项卡，然后单击 **Salesforce Chatter** 连接器以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
