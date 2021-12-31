---
title: 设置连接器以将 Salesforce Chatter 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器以将 Salesforce Chatter 数据从 Microsoft 365 导入和存档。 此连接器允许您将来自第三方数据源的数据存档到 Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: a06f08354f4b9c6d0f76d823699265668bb678fd
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643094"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>设置连接器以存档 Salesforce Chatter 数据

使用 Microsoft 365 合规中心 中的一个 Microsoft 365 合规中心，将数据从 Salesforce Chatter 平台导入并存档到贵组织的用户Microsoft 365邮箱。 该连接器提供[Salesforce Chatter](http://globanet.com/chatter/)连接器，用于捕获第三方数据源中的项目，并导入这些项Microsoft 365。 连接器将内容（如聊天、附件和帖子）从 Salesforce Chatter 转换为电子邮件格式，然后在 Microsoft 365 中将这些项目导入用户邮箱。

将 Salesforce Chatter 数据存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 Salesforce Chatter 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-salesforce-chatter-data"></a>存档 Salesforce Chatter 数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 Salesforce Chatter 数据的过程。

![Salesforce Chatter 数据的存档工作流。](../media/SalesforceChatterConnectorWorkflow.png)

1. 您的组织与 Salesforce Chatter 合作，以设置和配置 Salesforce Chatter 网站。

2. 每 24 小时复制一次 Salesforce Chatter 项，然后复制到该网吧。 连接器还会将 Salesforce Chatter 项目作为电子邮件格式。

3. 在 Microsoft 365 合规中心 中创建的 Salesforce Chatter 连接器每天连接到 Microsoft Merge1 网站，将 Chatter 内容传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Salesforce Chatter** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Chatter 项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 创建 Salesforce 应用程序，并获取 令牌 [https://salesforce.com](https://salesforce.com) 。 你将需要以管理员角色登录到 Salesforce 帐户，并获取用户个人令牌以导入数据。 此外，需要在 Chatter 网站上发布触发器，以捕获更新、删除和编辑。 这些触发器将在频道上创建帖子，Merge1 将捕获该频道的信息。 有关如何创建应用程序和获取令牌的分步说明，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)

- 必须在步骤 1 (步骤 1 中创建 Salesforce Chatter 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 需要此角色才能在数据连接器页的"数据连接器"页上添加Microsoft 365 合规中心。 默认情况下，不会为此角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>步骤 1：设置 Salesforce Chatter 连接器

第一步是访问数据连接器页，Microsoft 365 合规中心聊天者数据的连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **Salesforce Chatter**。

2. 在 **"Salesforce Chatter** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>步骤 2：在"完成"合并 1 网站中配置 Salesforce Chatter

第二步是在"网吧 Merge1"网站上配置 Salesforce Chatter 连接器。 若要了解如何配置 Salesforce Chatter 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)。

单击"保存 **&完成"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将 Salesforce Chatter 用户映射到Microsoft 365页上**，启用自动用户映射。 Salesforce Chatter 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>步骤 4：监视 Salesforce Chatter 连接器

创建 Salesforce Chatter 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后单击 **"Salesforce Chatter"** 连接器以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。