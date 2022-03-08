---
title: 设置连接器以将 XSLT/XML 数据存档到 Microsoft 365
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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自 Microsoft 365 的 XSLT/XML 数据。 此连接器允许您存档 Microsoft 365 中第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 9f8d33099dee0126922d3170f458317875293af8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322095"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>设置连接器以存档 XSLT/XML 数据

使用 Microsoft 365 合规中心 连接器将数据从网页源导入并存档到组织的用户Microsoft 365邮箱。 对于使用 XSLT (可扩展样式表语言转换) 创建的文件，通过 [XSLT/XML](https://globanet.com/xslt-xml) 连接器 (可将 XML 文件转换为可导入 Microsoft 365 的其他文件格式 (如 HTML 或文本) 。 连接器将项目的内容从 XSLT/XML 源转换为电子邮件格式，然后将转换的项目导入到Microsoft 365邮箱。

XSLT/XML 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 XSLT/XML 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-xsltxml-data"></a>存档 XSLT/XML 数据概述

以下概述介绍使用连接器在数据记录中存档 XSLT/XML 源数据Microsoft 365。

![XSLT/XML 数据的存档工作流。](../media/XSLT-XMLConnectorWorkflow.png)

1. 您的组织使用 XSLT/XML 源来设置和配置 XSLT/XML 网站。

2. 每 24 小时发送一次，来自 XSLT/XML 源的聊天消息将复制到"改进并合并 1"网站。 连接器还会将内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 中创建的 XSLT/XML 连接器每天连接到 Microsoft 云中的一个安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **XSLT/XML** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每封邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系 ["用户支持人员"](https://www.veritas.com/content/support/)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须为在步骤 1 中创建 XSLT/XML 连接器 (在步骤 3) 中完成该连接器的用户分配数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-an-xsltxml-connector"></a>步骤 1：设置 XSLT/XML 连接器

第一步是访问数据连接Microsoft 365 合规中心为  XSLT/XML 数据创建连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器** > **XSLT/XML"**。

2. 在" **XSLT/XML** 产品说明"页上，单击" **添加新连接器"**。

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 输入标识连接器的唯一名称，然后单击"下一步 **"**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-an-xsltxml-connector"></a>步骤 2：配置 XSLT/XML 连接器

第二步是在 Merge1 网站上配置 XSLT/XML 连接器。 若要了解如何在"一线合并 1"网站上配置 XSLT/XML 连接器，请参阅 [Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)三方连接器用户指南。

单击"保存 **&完成**"后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

1. 若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

2. 在"**将 XSLT/XML 用户** 映射到用户Microsoft 365，启用自动用户映射。 XSLT/XML 项目包括一个称为 *"电子邮件*"的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

3. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-xsltxml-connector"></a>步骤 4：监视 XSLT/XML 连接器

创建 XSLT/XML 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **XSLT/XML** 连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。