---
title: 设置连接器以在 Microsoft 365 中存档 Redtail Speak 数据
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
description: 管理员可以设置连接器以将 Redtail Speak 数据从 Globanet 导入并存档到 Microsoft 365。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 存档此数据后，可以使用合规性功能（如法定保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 546298288e69746856a1250cc4b87643dd479c91
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722942"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data-preview"></a>设置连接器以存档 Redtail Speak 数据 (预览) 

使用 Microsoft 365 合规中心中的 Globanet 连接器从 Redtail Speak 向 Microsoft 365 组织的用户邮箱导入和存档数据。 Globanet 为您提供了一个 [Redtail Speak](https://globanet.com/redtail/) 连接器，该连接器配置为从从 Redtail 接收项目的组织的 SFTP 服务器捕获项目。 连接器将 Redtail Speak 中的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

Redtail Speak 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 Redtail Speak 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>存档 Redtail Speak 数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Redtail Speak 数据的过程。

![Redtail Speak 数据的存档工作流](../media/RedtailSpeakConnectorWorkflow.png)

1. 贵组织与 Redtail Speak 合作，以设置和配置 SMTP 网关，其中每日邮件从 Redtail Speak 转发到组织的 SFTP 服务器。

2. 每 24 小时一次，Redtail Speak 项目将复制到 Globanet Merge1 网站。 连接器还会将 Redtail Speak 项目转换为电子邮件格式。

3. 你在 Microsoft 365 合规中心创建的 Redtail Speak 连接器每天连接到 Globanet Merge1 网站，将邮件转移到 Microsoft 云中安全的 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的 Redtail Speak 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Redtail Speak** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Redtail Speak 项目都包含此属性，此属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Globanet Merge1 帐户。 若要创建帐户，请联系 [Globanet 客户支持部门](https://globanet.com/contact-us/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 在步骤中，需要指定组织的 SFTP 服务器。 这是必需的，以便 Globanet Merge1 可以联系它以通过 SFTP 收集 Redtail Speak 数据。

- 在步骤 1 中创建 Redtail Speak 导入程序连接器 (步骤 3) 必须分配给 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中任何角色组。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>步骤 1：设置 Redtail Speak 连接器

第一步是访问 Microsoft 365 合规中心中的"数据连接器"页，并创建 Redtail Speak 数据的连接器。 

1. 转到并 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 单击 **数据连接器** &gt; **Redtail Speak。**

2. 在 **"Redtail Speak** 产品说明"页上，单击 **"添加新连接器"。**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 输入标识连接器的唯一名称，然后单击"下一 **步"。**

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>步骤 2：在 Globanet Merge1 网站上配置 Redtail Speak 连接器

第二步是在 Merge1 网站上配置 Redtail Speak 连接器。 若要了解如何配置 Redtail Speak 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器设置，请按照以下步骤操作：

1. 在 **"将用户映射到 Microsoft 365 用户** "页上，启用自动用户映射。 Redtail Speak 项目包括一个称为 *"电子邮件*"的属性，其中包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>步骤 4：监视 Redtail Speak 连接器

创建 Redtail Speak 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航 **中并** 单击"数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **"Redtail Speak"** 连接器以显示飞出页面。 此页面显示有关连接器的属性和信息。

3. 在 **"源的** 连接器状态"下，单击"下载日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
