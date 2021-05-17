---
title: 设置连接器以将 Cisco Jabber 存档在 Oracle Microsoft 365
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
description: 了解如何在 Microsoft 365 合规中心设置和使用连接器，以从 Oracle 上的 Cisco Jabber 导入数据并Microsoft 365。
ms.openlocfilehash: c3a2d64605eb3cda235c73964507a82c940187fe
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767077"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a>设置连接器以将 Cisco Jabber 存档在 Oracle 数据 (预览) 

使用 Microsoft 365 合规中心中的一个 Microsoft 365 连接器，将数据从 Oracle 平台上的 Cisco Jabber 导入并存档到 Microsoft 365 组织的用户邮箱。 为 Oracle 连接器提供[Cisco Jabber，](https://www.veritas.com/insights/merge1/jabber)该连接器配置为定期捕获第三方数据源 (中的项目) 将这些项目导入 Microsoft 365。 连接器将 Oracle 上的 Cisco Jabber 中的内容（如文件和文件操作、注释和共享内容）转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在 Oracle 上的 Cisco Jabber 数据存储在用户邮箱中后，Microsoft 365合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 Oracle 连接器上的 Cisco Jabber 在 Microsoft 365 导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>对 Oracle 数据存档 Cisco Jabber 概述

以下概述介绍使用连接器在 Oracle 中存档 Cisco Jabber Microsoft 365。

![Cisco Jabber 对 Oracle 数据的存档工作流](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. 贵组织与 Oracle 上的 Cisco Jabber 合作，在 Oracle 网站上设置和配置 Cisco Jabber。

2. 每 24 小时一次，将 Oracle 项上的 Cisco Jabber 复制到该"改进 24 小时"网站。 连接器还将 Oracle 项上的 Cisco Jabber 转换为电子邮件格式。

3. 在 Microsoft 365 合规中心内创建的 Oracle 连接器上的 Cisco Jabber 每天连接到一个 Microsoft Clouds Merge1 网站，将 Jabber 内容传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Cisco Jabber on Oracle** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹。 连接器使用 *Email* 属性的值实现此操作。 每个 Jabber 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建 Merge1 帐户。 若要进行此操作，请联系["用户支持人员"。](https://www.veritas.com/content/support/en_US) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 步骤 1 中在 Oracle 连接器上创建 Cisco Jabber (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在合规性中心的"数据连接器"页上添加 **连接器，Microsoft 365** 此角色。 默认情况下，此角色不会分配给角色组Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>步骤 1：在 Oracle 连接器上设置 Cisco Jabber

第一步是访问安全与合规中心的"数据连接器"Microsoft 365为 Jabber 数据创建连接器。

1. 转到 ， <https://compliance.microsoft.com> 然后单击 Oracle **上的"数据连接器**  >  **""Cisco Jabber"。**

2. 在 **Oracle 产品说明页上的 Cisco Jabber** 上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>第 2 步：在 Oracle 上配置 Cisco Jabber，位于"完成"合并 1 网站上

第二步是在"Cisco Merge1"站点上的 Oracle 连接器上配置 Cisco Jabber。 若要了解如何在 Oracle 连接器上配置 Cisco Jabber，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)。

单击"保存&**完成**"后，将显示合规性中心内连接器Microsoft 365中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365设置，请按照以下步骤操作：

1. 在"**将 Oracle 用户映射到用户Microsoft 365上的"映射 Cisco Jabber"** 页上，启用自动用户映射。 Oracle 项上的 Cisco Jabber 包含名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>步骤 4：监视 Oracle 连接器上的 Cisco Jabber

在 Oracle 连接器上创建 Cisco Jabber 后，可以在合规性中心内查看Microsoft 365状态。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 Oracle 连接器上的 **Cisco Jabber** 以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目，但稍后会提供对较大项目的支持。
