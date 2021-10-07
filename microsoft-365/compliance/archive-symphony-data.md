---
title: 设置连接器以在邮箱中存档Microsoft 365
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
description: 管理员可以设置一个连接器，以将数据从"百年百货"导入并Microsoft 365。 通过此连接器，可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 78a14a91c6c77be6cc738674107c0a2a4c7ee768
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172499"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>设置连接器以存档云数据

使用 Microsoft 365 合规中心 中的一个"Microsoft 365 合规中心"连接器，将"百年"数据导入并存档到组织Microsoft 365邮箱。 百年是金融服务行业使用的消息和协作平台。 在 Microsoft 365 合规中心 中，[为](https://globanet.com/symphony)第三方数据源 (中定期捕获项目) 然后将这些项目导入到用户邮箱进行配置。 连接器将项目的内容从"百分百"帐户转换为电子邮件格式，然后将该项目导入 Microsoft 365。

在将百年通信存储在用户邮箱中后，你可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用一个百年连接器在企业邮箱中导入和存档Microsoft 365可帮助你的组织遵守政府及法规策略。

## <a name="overview-of-archiving-symphony-data"></a>存档百年数据概述

以下概述介绍使用数据连接器在云中存档 Microsoft 365。

![监控存档工作流。](../media/SymphonyConnectorWorkflow.png)

1. 你的组织与用户一起设置和配置一个"百年"网站。

2. 每 24 小时发送一次，来自 Everyy 的聊天消息将复制到"改进"合并 1 网站。 连接器还会将聊天消息的内容转换为电子邮件格式。

3. 在 Microsoft 云中创建的 Microsoft 365 合规中心 连接器每天连接到一个百分卡合并 1 网站，将邮件Azure 存储 Microsoft 云中的安全位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **"Inboxy"** 的"收件箱"文件夹中的新子文件夹，邮件项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个聊天消息都包含此属性，其中填充了每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 (步骤 1 中创建并完成该连接器) 用户必须分配至 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-symphony-connector"></a>步骤 1：设置安装连接器

第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建一个连接器用于"安装"数据。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"**数据连接器**  >  **""百年"。**

2. 在 **"百年** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a>在"部署合并 1"网站上配置"百年"连接器

第二步是在 Merge1 网站上配置部署连接器。 有关在"网吧 Merge1"网站上配置"安装连接器"的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将外部用户映射到Microsoft 365"页上**，启用自动用户映射。 "百年"项目包含一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-symphony-connector"></a>步骤 4：监视安装连接器

创建"百年"连接器后，可以在"目录"中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **"百** 年"连接器以显示飞出页面。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。