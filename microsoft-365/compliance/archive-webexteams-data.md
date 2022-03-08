---
title: 将连接器设置为 Webex Teams数据Microsoft 365
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
description: 管理员可以设置一个连接器，从 Microsoft 365 中从具有该连接器的 Teams 导入和存档数据。 此连接器允许您存档 Microsoft 365 中第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 0906156f5c0c796deaa5bd72738813d912e30b47
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312301"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>设置连接器以存档 Webex Teams数据

使用 Web 部件中的 Microsoft 365 合规中心 连接器将数据从 Webex Teams导入并存档到组织Microsoft 365邮箱。 该连接器提供了[一Teams](https://globanet.com/webex-teams/) Webex 连接器，该连接器配置为捕获 Webex Teams通信项目，并导入到Microsoft 365。 连接器将 Webex Teams 中的内容（如一对一聊天、群组对话、频道对话和来自组织的 Webex Teams 帐户的附件）转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在 Webex Teams数据存储在用户邮箱中之后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Webex Teams连接器导入和存档 Microsoft 365可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-webex-teams-data"></a>存档 Webex Teams概述

以下概述介绍使用连接器将 Webex 存档到 Teams 数据的过程Microsoft 365。

![Webex 存档工作流Teams数据。](../media/WebexTeamsConnectorWorkflow.png)

1. 您的组织与 Webex Teams一起设置和配置 Webex Teams网站。

2. 每 24 小时一次，Webex Teams项目将复制到"完成"合并 1 网站。 连接器还会将 Webex Teams转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 Webex Teams 连接器，每天连接到 Microsoft Clouds Merge1，将 Webex Teams 项转移到 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **"Webex** Teams"收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个 Webex Teams项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系 ["用户支持人员"](https://globanet.com/ms-connectors-contact)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 在 上创建[https://developer.webex.com/](https://developer.webex.com)一个应用程序，以从 Webex Teams数据。 有关创建应用程序的分步说明，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   创建此应用程序时，Webex 平台将生成一组唯一凭据。 在全局 Merge1 网站上配置 Webex Teams连接器时，步骤 2 中会使用这些凭据。

- 必须为在步骤 1 Teams创建 Webex (连接器并将其在步骤 3) 中完成的用户分配有数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-the-webex-teams-connector"></a>步骤 1：设置 Webex Teams连接器

第一步是获取对数据连接器的访问权限，并设置 [Webex Teams](https://globanet.com/webex-teams/)连接器。

1. 转到 ，[https://compliance.microsoft.com](https://compliance.microsoft.com/)然后单击 **数据连接器** > **Webex Teams**。

2. 在"**Webex Teams** 产品说明"页上，单击"添加 **连接器"**。

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 输入标识连接器的唯一名称，然后单击"下一步 **"**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>步骤 2：在 Teams Merge1 网站上配置 Webex 连接器

第二步是在 Merge1 Teams Webex 连接器。 若要了解如何配置 Webex 连接器Teams，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。

单击"保存 **&完成**"后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**映射 Webex Teams用户Microsoft 365，** 启用自动用户映射。 Webex Teams项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-webex-teams-connector"></a>步骤 4：监视 Webex Teams连接器

创建 Webex Teams连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **Webex Teams** 连接器以显示该飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。