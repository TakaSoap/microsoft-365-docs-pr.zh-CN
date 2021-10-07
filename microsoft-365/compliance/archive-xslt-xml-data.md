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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自 Its 的 XSLT/XML Microsoft 365。 此连接器允许您在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: a7220d12a444754e1cdb67facac085452b2f6a7c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155066"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>设置连接器以存档 XSLT/XML 数据

使用 Microsoft 365 合规中心 连接器将网页源数据导入并存档到组织中用户Microsoft 365邮箱。 对于使用 XSLT (可扩展样式表语言转换) 创建的文件，通过[XSLT/XML](https://globanet.com/xslt-xml)连接器，您可以快速开发这些文件 (如 HTML 或文本) ，这些格式可以导入 Microsoft 365。 连接器将项目的内容从 XSLT/XML 源转换为电子邮件格式，然后将转换的项目导入到Microsoft 365邮箱。

XSLT/XML 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 XSLT/XML 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-xsltxml-data"></a>存档 XSLT/XML 数据概述

以下概述介绍使用连接器在数据记录中存档 XSLT/XML 源数据Microsoft 365。

![XSLT/XML 数据的存档工作流。](../media/XSLT-XMLConnectorWorkflow.png)

1. 您的组织使用 XSLT/XML 源来设置和配置 XSLT/XML 网站。

2. 每 24 小时发送一次，来自 XSLT/XML 源的聊天消息将复制到"改进并合并 1"网站。 连接器还会将内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 XSLT/XML 连接器每天连接到一个 Microsoft 云中的一个安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **XSLT/XML** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每封邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 中创建 XSLT/XML 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会向角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-an-xsltxml-connector"></a>步骤 1：设置 XSLT/XML 连接器

第一步是访问数据连接器，并Microsoft 365 合规中心 XSLT/XML 数据的连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **XSLT/XML**。

2. 在 **"XSLT/XML** 产品说明"页上，单击"**添加新连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-an-xsltxml-connector"></a>步骤 2：配置 XSLT/XML 连接器

第二步是在 Merge1 网站上配置 XSLT/XML 连接器。 若要了解如何在"一线合并 1"网站上配置 XSLT/XML 连接器，请参阅 [Merge1 第](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)三方连接器用户指南。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

1. 若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

2. 在"**将 XSLT/XML 用户映射到用户Microsoft 365，** 启用自动用户映射。 XSLT/XML 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

3. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-xsltxml-connector"></a>步骤 4：监视 XSLT/XML 连接器

创建 XSLT/XML 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **XSLT/XML** 连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"下**， **单击"下载** 日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。