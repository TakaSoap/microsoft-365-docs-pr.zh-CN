---
title: 设置连接器以在 Microsoft 365 中存档安装数据
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
description: 管理员可以设置连接器，将数据从 Globanet 管理中心导入和存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 94bd9bb8f2b7586e685769af389d6cd0a0ea18ac
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619828"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>设置连接器以存档云数据

使用 Microsoft 365 合规中心中的 Globanet 连接器，向 Microsoft 365 组织的用户邮箱导入和存档安装数据。 云是金融服务行业使用的消息和协作平台。 Globanet 在 Microsoft 365 合规中心提供一个 [可](https://globanet.com/symphony) 配置以定期捕获第三方数据源 (中的项目) 然后将这些项目导入到用户邮箱。 连接器将项目的内容从"安装时间"帐户转换为电子邮件格式，然后将该项目导入到 Microsoft 365 中的邮箱。

在用户邮箱中存储了功能通信后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用安装连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-symphony-data"></a>存档云数据概述

以下概述介绍了使用数据连接器在 Microsoft 365 中存档"安装"通信的过程。

![分步存档工作流](../media/SymphonyConnectorWorkflow.png)

1. 你的组织与安装公司合作来设置和配置一个安装网站。

2. 每 24 小时一次，来自"一线"的聊天消息将复制到 Globanet Merge1 网站。 连接器还会将聊天消息的内容转换为电子邮件格式。

3. 你在 Microsoft 365 合规中心创建的部署连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱，如步骤 3 中所述。 在用户邮箱中创建名为 **"Inboxy"** 的收件箱文件夹中的新子文件夹，邮件项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个聊天消息都包含此属性，此属性填充了每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建 Globanet Merge1 帐户。 若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/ms-connectors-contact)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 (步骤 3 中创建并完成安装连接器) 必须分配给 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

## <a name="step-1-set-up-the-symphony-connector"></a>步骤 1：设置安装连接器

第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建一个连接器以用于"安全"数据。 

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击"**数据连接器**  >  **安装"。**

2. 在 **"百年** 产品说明"页上，单击 **"添加连接器"。**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 输入标识连接器的唯一名称，然后单击"下一 **步"。**

5. 登录到 Merge1 帐户以配置连接器。

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a>在 Globanet Merge1 网站上配置部署连接器

第二步是在 Merge1 网站上配置安装连接器。 有关在 Globanet Merge1 网站上配置安装连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：

1. 在 **"将外部用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。 该邮件包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"** 下一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-symphony-connector"></a>步骤 4：监视安装连接器

创建安装连接器后，可以在 Microsoft 365 合规中心内查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 左侧导航 **中并** 单击"数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **"安装** 连接器"以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
