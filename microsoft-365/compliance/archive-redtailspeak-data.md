---
title: 设置连接器以将 Red tail Speak 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器以将 Red tail Speak 数据从 Its 导入和存档到Microsoft 365。 通过此连接器，可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: bce266bebd38e49e8ad756dc4100050694bc5d8c
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643608"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>设置连接器以存档 Redtail Speak 数据

使用 Microsoft 365 合规中心 连接器从 Redtail Speak to user mailboxes in your Microsoft 365 organization 导入和存档数据。 对于配置为从组织的 SFTP 服务器捕获项目（从 Redtail 接收项目）的 [Redtail Speak](https://globanet.com/redtail/) 连接器，则使用该连接器。 连接器将 Redtail Speak 中的内容转换为电子邮件格式，然后将这些项目导入用户邮箱中Microsoft 365。

在 Redtail Speak 数据存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 Redtail Speak 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>存档 Redtail Speak 数据概述

以下概述介绍了使用连接器在"Redtail Speak"文件中存档"Redtail Speak"Microsoft 365。

![Redtail Speak 数据的存档工作流。](../media/RedtailSpeakConnectorWorkflow.png)

1. 贵组织与 Redtail Speak 合作，以设置和配置 SMTP 网关，其中邮件每天从 Redtail Speak 转发到组织的 SFTP 服务器。

2. 每 24 小时复制一次 Redtail Speak 项，然后复制到"是否合并 1"网站。 连接器还会将 Redtail Speak 项目转换为电子邮件格式。

3. 在 Microsoft 云中创建的 Redtail Speak 连接器Microsoft 365 合规中心每天连接到 Microsoft 云中的一个安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的 Redtail Speak 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Redtail Speak** 的收件箱文件夹中的子文件夹，项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Redtail Speak 项目都包含此属性，该属性用该项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 在步骤 2 中，需要指定组织的 SFTP 服务器。 这一步是必需的，以便该企业 Merge1 可以联系它以通过 SFTP 收集 Redtail Speak 数据。

- 必须在步骤 1 中创建 Redtail Speak 导入程序连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此角色Microsoft 365 合规中心。 默认情况下，此角色不会分配给角色Exchange Online角色组。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此位于美国政府云中的 GCC 环境Microsoft 365预览版。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>步骤 1：设置 Redtail Speak 连接器

第一步是访问"Redtail  Speak"数据Microsoft 365 合规中心访问"数据连接器"页。

1. 转到并选择 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 数据 **连接器** &gt; **Redtail Speak**。

2. 在 **"Redtail Speak** 产品说明"页上，选择"**添加新连接器"。**

3. 在"**服务条款"页上**，选择"接受 **"。**

4. 输入标识连接器的唯一名称，然后选择"下一 **步"。**

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>步骤 2：在"中文合并 1"网站上配置 Redtail Speak 连接器

第二步是在 Merge1 网站上配置 Redtail Speak 连接器。 若要了解如何配置 Redtail Speak 连接器，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。

选择"保存 **&完成**"后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器设置，请按照以下步骤操作：

1. 在"**将用户映射到用户Microsoft 365"页上**，启用自动用户映射。 Redtail Speak 项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 选择 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>步骤 4：监视 Redtail Speak 连接器

创建 Redtail Speak 连接器后，可以查看"Redtail Speak"连接器Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后选择" 数据连接器"。

2. 选择" **连接器"** 选项卡，然后选择 **"Redtail Speak"** 连接器以显示飞出页面。 此页面显示有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **选择"下载** 日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。