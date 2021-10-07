---
title: 设置连接器以在 Skype for Business 中存档Microsoft 365
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
description: 了解如何在邮箱中设置和使用Microsoft 365 合规中心导入和存档数据Skype for Business到Microsoft 365。
ms.openlocfilehash: 39ce8dbe114e9c6a6d57e29701b375c279e446a9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153314"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>设置连接器以存档Skype for Business数据

使用 Microsoft 365 合规中心 中的一个 Microsoft 365 合规中心，将数据从 Skype for Business 平台导入并存档到组织的用户Microsoft 365邮箱。 该[连接器Skype for Business连接器](https://www.veritas.com/en/au/insights/merge1/skype-for-business)，配置为定期捕获第三方数据源 (中的项目) 将这些项目导入Microsoft 365。 连接器将用户之间的消息、持久聊天和会议消息等内容从 Skype for Business 转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在Skype for Business邮箱中存储数据后，可以应用Microsoft 365保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 Skype for Business 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-skype-for-business-data"></a>存档数据Skype for Business概述

以下概述介绍使用连接器在数据记录Skype for Business存档Microsoft 365。

![存档数据Skype for Business工作流。](../media/SkypeforBusinessConnectorWorkflow.png)

1. 您的组织与 Skype for Business一起设置和配置Skype for Business网站。

2. 每 24 小时Skype for Business一次，项目将复制到"是否合并 1"网站。 连接器还会将Skype for Business转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 Skype for Business 连接器，每天连接到 Microsoft 云中的 Skype for Business 网站，将 Skype for Business 内容传输至安全的 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Skype for Business** 的"收件箱"文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个Skype for Business项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 Merge1 帐户。 若要进行此操作，请联系["用户支持人员"。](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (步骤 1 中创建 Skype for Business 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** Microsoft 365 合规中心。 默认情况下，不会为此角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中的角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-skype-for-business-connector"></a>步骤 1：设置Skype for Business连接器

第一步是访问数据连接器页，Microsoft 365 合规中心数据创建Skype for Business连接器。 

1. 转到 ， <https://compliance.microsoft.com> 然后单击"数据 **连接器**  >  **Skype for Business"。**

2. 在 **"Skype for Business** 说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>步骤 2：在 Skype for Business Merge1 网站上配置网站集

第二步是在 Skype for Business Merge1 网站上配置连接器。 若要了解如何配置连接器Skype for Business，请参阅[Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将Skype for Business用户Microsoft 365页上，** 启用自动用户映射。 The Skype for Business items include a property called *Email*， which contains email addresses for users in your organization. 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-skype-for-business-connector"></a>步骤 4：监视Skype for Business连接器

创建连接器Skype for Business，可以查看连接器在连接器Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"****选项卡**，然后选择Skype for Business连接器以显示包含有关连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
