---
title: 设置连接器以将 EML 数据存档在 Microsoft 365
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
description: 管理员可以设置连接器，以将 EML 数据从 Microsoft 365 导入和存档。 通过此连接器，可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: c590afc3e9501e9c7304852f46173bbd16034d17
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60179447"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a>设置连接器以存档 EML 数据

使用 Microsoft 365 合规中心 中的"Microsoft 365 合规中心"连接器将 EML 数据导入并存档到组织中用户Microsoft 365邮箱。 EML 是保存到文件的电子邮件的文件扩展名。 连接器将项目的内容从源格式转换为电子邮件格式，然后将该项目导入到用户邮箱。

在 EML 邮件存储在用户邮箱中后，可以应用Microsoft 365保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 EML 连接器导入数据并存档数据Microsoft 365有助于组织遵守政府及法规策略。

## <a name="overview-of-archiving-eml-data"></a>存档 EML 数据概述

以下概述介绍使用连接器在电子邮件中存档 EML 数据Microsoft 365。

![EML 数据的存档工作流。](../media/EMLConnectorWorkflow.png)

1. 您的组织与 EML 源一起设置和配置 EML 站点。

2. 每 24 小时复制一次 EML 源中的内容项，然后复制到"完成"合并 1 网站。 在此过程中，EML 文件的内容将转换为电子邮件格式。

3. 在 Microsoft 云中创建的 EML 连接器Microsoft 365 合规中心每天连接到 Microsoft Clouds Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 连接器使用步骤 [3](#step-3-map-users-and-complete-the-connector-setup)中所述的自动用户映射过程的 *Email* 属性值将转换后的邮件项目导入特定用户的邮箱。 在此过程中，在用户邮箱中创建名为 **EML** 的收件箱文件夹中的子文件夹，EML 项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每封邮件都包含此属性，其中填充了内容项每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://globanet.com/ms-connectors-contact) 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 中创建 EML 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-an-eml-connector"></a>步骤 1：设置 EML 连接器

第一步是访问电子邮件中的"数据连接器"Microsoft 365 合规中心为 EML 数据创建连接器。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器**  >  **EML"。**

2. 在 **"EML 产品** 说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-eml-connector-on-the-veritas-merge1-site"></a>步骤 2：在"完成"合并 1 网站中配置 EML 连接器

第二步是在"开发区 Merge1"网站上配置 EML 连接器。 有关配置 EML 连接器的信息，请参阅 [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)。

单击"保存&**完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将外部用户映射到Microsoft 365"页上**，启用自动用户映射。 EML 源项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，EML 项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-eml-connector"></a>步骤 4：监视 EML 连接器

创建 EML 连接器后，可以查看连接器在 Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **EML** 连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关已导入到 Microsoft 云的数据的信息。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。