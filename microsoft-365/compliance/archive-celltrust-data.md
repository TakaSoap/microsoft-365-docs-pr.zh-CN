---
title: 设置连接器以将 CellTrust 数据存档在Microsoft 365
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
description: 管理员可以设置连接器以将 CellTrust 数据从 Microsoft 365 导入和存档。 此连接器允许您将来自第三方数据源的数据存档到 Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 89d19be7b23d76c5edbfe6949ba6b6b0166458a4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195709"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>设置连接器以存档 CellTrust 数据

使用 Microsoft 365 合规中心 连接器将数据从 CellTrust 平台导入并存档到组织Microsoft 365邮箱。 该连接器提供[CellTrust](https://globanet.com/celltrust/)连接器，用于捕获第三方数据源中的项目，并导入这些项Microsoft 365。 连接器将短信的内容从 CellTrust 帐户转换为电子邮件格式，然后将这些项目导入用户邮箱中的 Microsoft 365。

将 CellTrust 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 CellTrust 连接器在组织中导入和存档Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-celltrust-data"></a>存档 CellTrust 数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 CellTrust 数据的过程。

![CellTrust 数据的存档工作流。](../media/CellTrustConnectorWorkflow.png)

1. 您的组织与 CellTrust 一起设置和配置 CellTrust 网站。

2. 每 24 小时复制一次 CellTrust 项，然后复制到该"是否合并 1"网站。 连接器还会将邮件内容转换为电子邮件格式。

3. 在 Microsoft 云中创建的 CellTrust 连接器Microsoft 365 合规中心每天连接到该 Microsoft 365 合规中心 Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 作为连接器的自动用户映射使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述 *的 Email* 属性的值将项目导入特定用户的邮箱。 在用户邮箱中创建名为 **CellTrust** 的收件箱文件夹中的子文件夹，邮件项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 CellTrust 项目都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建 Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 中创建 CellTrust 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-celltrust-connector"></a>步骤 1：设置 CellTrust 连接器

第一步是访问 Microsoft 365 合规中心 中的数据连接器，并创建 CellTrust 数据的连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器""** \> **单元格信任"。**

2. 在 **"CellTrust** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a>步骤 2：在"完成"合并 1 网站中配置 CellTrust 连接器

第二步是在"则 Iss Merge1"网站上配置 CellTrust 连接器。 若要了解如何配置 CellTrust 连接器，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成在 Microsoft 365 合规中心 中设置的连接器，请按照以下步骤操作：

1. 在"**将 CellTrust 用户映射到Microsoft 365"页上**，启用自动用户映射。 CellTrust 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-celltrust-connector"></a>步骤 4：监视 CellTrust 连接器

创建 CellTrust 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **CellTrust** 连接器以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。