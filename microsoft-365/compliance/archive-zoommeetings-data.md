---
title: 设置连接器以在"会议"中存档"缩放Microsoft 365
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
description: 管理员可以设置一个连接器，以将来自"显示会议"的"会议"导入和存档Microsoft 365。 这样，您就可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: f776fe3d03f8674a698b5c8fe2f355aa5635577f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327303"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>设置连接器以存档"缩放会议"数据

使用 Microsoft 365 合规中心 连接器将"缩放会议"数据导入并存档到组织中用户Microsoft 365邮箱。 该[连接器配置为定期](https://globanet.com/zoom/)捕获第三方数据源 (中的项目，) 将这些项目导入Microsoft 365。 连接器将会议内容 (包括聊天、录制的文件和元数据) 从 Zoom Meetings 帐户转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

缩放会议数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Zoom Meetings 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-zoom-meetings-data"></a>存档缩放会议数据概述

以下概述介绍使用连接器在"会议"中存档"缩放会议"数据Microsoft 365。

![缩放会议存档工作流。](../media/ZoomMeetingsConnectorWorkflow.png)

1. 你的组织使用"缩放会议"来设置和配置"缩放会议"网站。

2. 每 24 小时一次，"缩放会议"中的会议项目将复制到"是否合并 1"网站。 连接器还会将会议内容转换为电子邮件格式。

3. 在 Microsoft 云中创建的"缩放会议"Microsoft 365 合规中心，每天连接到"Microsoft Merge1"，将会议消息传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用 *Email* 属性的值和自动用户映射将转换的会议项目导入特定用户的邮箱，如步骤 3 中所述。 "收件箱"文件夹中名为"缩放会议"的新子文件夹是在用户邮箱中创建的，并且会议项目将导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个会议项目都包含此属性，其中填充了会议每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系 ["用户支持人员"](https://globanet.com/ms-connectors-contact)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 获取组织的 Zoom Business 或 Zoom Enterprise用户名和密码。 配置"缩放会议"连接器时，需要在步骤 2 中登录此帐户。

- 在缩放市场中创建 [以下应用程序](https://marketplace.zoom.us)：

  - OAuth 应用程序

  - JWT 应用程序

  创建这些应用程序后，Zoom 平台将生成一组用于生成令牌的唯一凭据。 这些令牌用于在连接器连接到 Zoom 帐户，将项目复制到 Merge1 网站时对连接器进行身份验证。 在步骤 2 中配置缩放连接器时，你将使用这些令牌。

  有关如何创建 OAuth 和 JWT 应用程序的分步说明，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。

- 必须为在步骤 1 中创建"缩放会议"连接器 (步骤 3) 用户分配"数据连接器管理员"角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>步骤 1：设置缩放会议连接器

第一步是访问"缩放会议"Microsoft 365 合规中心"缩放会议"连接器。

1. 转到 ，[https://compliance.microsoft.com](https://compliance.microsoft.com/)然后单击"数据 **连接器** > "**"会议"**。

2. 在" **缩放会议"** 产品说明页上，单击" **添加连接器"**。

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 输入标识连接器的唯一名称，然后单击"下一步 **"**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-zoom-meetings-connector"></a>步骤 2：配置缩放会议连接器

第二步是在 Merge1 网站上配置"缩放会议"连接器。 若要详细了解如何在"显示合并 1"网站上配置"缩放会议"连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)。

单击"保存 **&完成**"后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

1. 在"**将外部用户映射到 Microsoft 365"页上**，启用自动用户映射。

   "缩放会议"项目包括一个称为 *"电子邮件* "的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱

2. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>步骤 4：监视 Zoom 会议连接器

创建"缩放会议"连接器后，可以在"会议"视图中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择" **缩放会议** "连接器以显示飞出页面。 此页面包含有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。

- 若要使"缩放会议"连接器正常工作，必须在设置"缩放会议"时启用录制。