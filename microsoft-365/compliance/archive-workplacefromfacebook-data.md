---
title: 设置连接器以从 Facebook 数据存档工作区Microsoft 365
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
description: 管理员可以设置一个连接器，以将来自 Workplace 的数据从 Facebook 导入和存档，Facebook 会将其存档到 Microsoft 365。 设置连接器需要你使用管理程序 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: ebf6f8f4aab2ac4290610458e10181d8e74181f2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312259"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>设置连接器以从 Facebook 数据存档 Workplace

使用工作区中的"Microsoft 365 合规中心连接器，将数据从 Facebook 导入并存档到组织中用户Microsoft 365邮箱。 对于配置为定期捕获第三方数据源 (中的项目，) Facebook 连接器提供 [Workplace](https://globanet.com/workplace/)，) 将这些项目导入Microsoft 365。 连接器将工作区中的聊天、附件、帖子和视频等内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

工作区数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Facebook 连接器中的 Workplace 在 Microsoft 365导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>从 Facebook 数据存档工作区概述

以下概述介绍使用连接器在工作区中存档工作区Microsoft 365。

![从 Facebook 数据存档工作区工作流。](../media/WorkplaceConnectorWorkflow.png)

1. 你的组织与 Facebook 的 Workplace 合作来设置和配置工作区网站。

2. 每 24 小时复制一次 Workplace 中的项目，然后复制到其 Merge1 网站。 连接器还会将这些项目的内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的来自 Facebook 连接器的 Workplace，每天连接到 Microsoft Clouds Merge1，将工作区项目转移到 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入特定用户的邮箱，如步骤 3 中所述。 "收件箱"文件夹中的"工作区"文件夹（来自 **Facebook** ）中创建一个子文件夹，工作区项目将导入该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每个 Workplace 项目都包含此属性，该属性填充了每个聊天或帖子参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系 ["用户支持人员"](https://globanet.com/ms-connectors-contact)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 在 中创建自定义集成， https://my.workplace.com/work/admin/apps/ 以通过 API 从工作区检索数据，实现合规性和电子数据展示目的。

   创建集成时，工作区平台会生成一组用于生成用于身份验证的令牌的唯一凭据。 这些令牌在步骤 2 中的 Workplace from Facebook 连接器配置向导中使用。 有关如何创建应用程序的分步说明，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

- 必须在步骤 1 中通过 Facebook 连接器创建工作区 (在步骤 3) 中完成该连接器的用户必须分配有"数据连接器管理员"角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>步骤 1：从 Facebook 连接器设置工作区

第一步是访问工作区中的"数据连接器"Microsoft 365 合规中心为 Workplace 数据创建连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器"** > **"从 Facebook 工作"**。

2. 在" **来自 Facebook 产品说明的工作区** "页上，单击" **添加连接器"**。

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 输入标识连接器的唯一名称，然后单击"下一步 **"**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>步骤 2：在"是否通过 Facebook 合并 1"网站上配置"工作区"连接器

第二步是在 Merge1 网站上配置 Facebook 中的 Workplace 连接器。 若要了解如何从 Facebook 连接器配置 Workplace，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

单击"保存 **&完成**"后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将外部用户映射到 Microsoft 365"页上**，启用自动用户映射。 工作区项目包括一个称为 *"电子邮件* "的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>步骤 4：通过 Facebook 连接器监视工作区

从 Facebook 连接器创建 Workplace 后，可以在"工作区"视图中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后从 **Facebook 连接器选择"工作区** "以显示飞出页面。 此页面包含有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。