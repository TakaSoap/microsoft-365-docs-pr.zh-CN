---
title: 设置连接器以将 XSLT/XML 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器，以从 Microsoft 365 中导入和存档来自 Its 的 XSLT/XML Microsoft 365。 此连接器允许您在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163752"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>设置连接器以存档 XSLT/XML 数据

使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从网页源导入并存档到组织的用户Microsoft 365邮箱。 对于使用 XSLT (可扩展样式表语言转换) 创建的文件，通过[XSLT/XML](https://globanet.com/xslt-xml)连接器，您可以快速开发这些文件 (如 HTML 或文本) ，这些格式可以导入 Microsoft 365。 连接器将项目的内容从 XSLT/XML 源转换为电子邮件格式，然后将转换的项目导入到Microsoft 365邮箱。

XSLT/XML 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 XSLT/XML 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-xsltxml-data"></a>存档 XSLT/XML 数据概述

以下概述介绍使用连接器在数据记录中存档 XSLT/XML 源数据Microsoft 365。

![XSLT/XML 数据的存档工作流](../media/XSLT-XMLConnectorWorkflow.png)

1. 您的组织使用 XSLT/XML 源来设置和配置 XSLT/XML 网站。

2. 每 24 小时发送一次，来自 XSLT/XML 源的聊天消息将复制到"完成"合并 1 网站。 连接器还会将内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心内创建的 XSLT/XML 连接器每天连接到一个 Microsoft Clouds Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **XSLT/XML** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每封邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 中创建 XSLT/XML 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。 默认情况下，此角色不会分配给角色组Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-an-xsltxml-connector"></a>步骤 1：设置 XSLT/XML 连接器

第一步是在合规性中心内访问Microsoft 365连接器，并创建 XSLT/XML 数据的连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **XSLT/XML**。

2. 在 **"XSLT/XML** 产品说明"页上，单击"**添加新连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-an-xsltxml-connector"></a>步骤 2：配置 XSLT/XML 连接器

第二步是在 Merge1 网站上配置 XSLT/XML 连接器。 若要了解如何在"一线合并 1"网站上配置 XSLT/XML 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)。

单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

1. 若要映射用户并完成 Microsoft 365合规中心中的连接器设置，请按照以下步骤操作：

2. 在"**将 XSLT/XML 用户映射到用户Microsoft 365，** 启用自动用户映射。 XSLT/XML 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

3. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-xsltxml-connector"></a>步骤 4：监视 XSLT/XML 连接器

创建 XSLT/XML 连接器后，可以在合规性中心内查看Microsoft 365状态。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **XSLT/XML** 连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。