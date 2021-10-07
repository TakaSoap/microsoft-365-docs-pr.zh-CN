---
title: 设置连接器以将 Yieldbroker 数据存档到 Microsoft 365
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
description: 管理员可以设置连接器以将 Yieldbroker 数据从 Microsoft 365 导入和存档。 此连接器允许您将来自第三方数据源的数据存档到 Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: ca6ef83374cdc95f3f761f884aaa8c563e2d142a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207375"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>设置连接器以存档 Yieldbroker 数据

使用 Microsoft 365 合规中心 连接器将数据从 Yieldbroker 导入并存档到组织Microsoft 365邮箱。 对于配置为捕获第三方数据源中的项目，以及将这些项目导入到第三方数据源的[Yieldbroker](https://globanet.com/yieldbroker/)连接器，Microsoft 365。 连接器将 Yieldbroker 中的内容转换为电子邮件格式，然后将这些项目导入到用户邮箱中的 Microsoft 365。

在 Yieldbroker 存储在用户邮箱中后，Microsoft 365诉讼保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 Yieldbroker 连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-yieldbroker-data"></a>存档 Yieldbroker 数据概述

以下概述介绍使用连接器在数据记录中存档 Yieldbroker 数据Microsoft 365。

![Yieldbroker 数据的存档工作流。](../media/YieldbrokerConnectorWorkflow.png)

1. 您的组织与 Yieldbroker 合作，以设置和配置 Yieldbroker 站点。

2. 每 24 小时复制一次 Yieldbroker 项，然后复制到该"是否合并 1"网站。 连接器还会将内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 Yieldbroker 连接器每天连接到一个 Microsoft 云中的一个安全 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换后的 Yieldbroker 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **Yieldbroker** 的收件箱文件夹中的子文件夹，项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Yieldbroker 都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 中创建 Yieldbroker 连接器 (在步骤 3) 中完成此连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，不会为此角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-yieldbroker-connector"></a>步骤 1：设置 Yieldbroker 连接器

第一步是访问数据连接器页，Microsoft 365 合规中心为 Yieldbroker 创建连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器** &gt; **Yieldbroker**。

2. 在 **"Yieldbroker** 产品说明"页上，单击"**添加新连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>第 2 步：配置位于以下位置的 Yieldbroker 连接器：

第二步是在 Merge1 站点上配置 Yieldbroker 连接器。 若要了解如何配置 Yieldbroker，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器设置，请按照以下步骤操作：

1. 在"**将 Yieldbroker 用户映射到Microsoft 365页上**，启用自动用户映射。 Yieldbroker 项目包括一个称为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-yieldbroker-connector"></a>步骤 4：监视 Yieldbroker 连接器

创建 Yieldbroker 连接器后，可以在该连接器的 Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **"Yieldbroker** 连接器"以显示包含有关连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"下**， **单击"下载** 日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。