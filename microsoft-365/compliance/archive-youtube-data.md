---
title: 设置连接器以将 YouTube 数据存档在Microsoft 365
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
description: 管理员可以设置连接器，以将 YouTube 数据从 Microsoft 365 导入和存档。 此连接器允许您将来自第三方数据源的数据存档到 Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、电子数据展示和保留策略）管理第三方数据。
ms.openlocfilehash: 6205e9a8425b4d9eeea2278a131881045b6e6bac
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153230"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>设置连接器以存档 YouTube 数据

使用 Microsoft 365 合规中心 连接器将数据从 YouTube 导入并存档到组织Microsoft 365邮箱。 该连接器配置为捕获第三方数据源中的项目，并导入这些项目以Microsoft 365。 连接器将 YouTube 中的聊天、附件、任务、笔记和帖子等内容转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在 YouTube 数据存储在用户邮箱中后，您可以应用Microsoft 365保留、电子数据展示、保留策略和保留标签等合规性功能。 使用 YouTube 连接器导入数据并存档Microsoft 365可帮助您的组织遵守政府及法规策略。

## <a name="overview-of-archiving-youtube-data"></a>存档 YouTube 数据概述

以下概述说明了使用连接器在邮件中存档 YouTube 数据Microsoft 365。

![YouTube 数据的存档工作流。](../media/YouTubeConnectorWorkflow.png)

1. 您的组织与 YouTube 合作，以设置和配置 YouTube 网站。

2. 每 24 小时复制一次 YouTube 项目，然后复制到该"是否合并 1"网站。 连接器还会将 YouTube 项目转换为电子邮件格式。

3. 您每天在 Microsoft 365 合规中心 创建的 YouTube 连接器连接到 Microsoft 云中的 Microsoft 365 合规中心 网站，将 YouTube 内容传输至安全的 Azure 存储 位置。

4. 连接器使用自动用户映射的 *Email* 属性值将转换的项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **YouTube** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 YouTube 项目都包含此属性，其中填充了项目每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 Merge1 帐户。 若要创建此帐户，请联系["用户支持人员"。](https://www.veritas.com/form/requestacall/ms-connectors-contact) 在步骤 1 中创建连接器时，需要登录此帐户。

- 创建一个 YouTube 应用程序以从 YouTube 帐户提取数据。 有关创建应用程序的分步说明，请参阅[Merge1 Third-Party Connectors User Guide。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)

- 必须在步骤 1 中创建 YouTube 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的"邮箱导入导出"角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会为此角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-youtube-connector"></a>步骤 1：设置 YouTube 连接器

第一步是访问"数据连接器"页，Microsoft 365 合规中心为 YouTube 数据创建连接器。

1. 转到 ， <https://compliance.microsoft.com> 然后单击"**数据连接器**  >  **""YouTube"。**

2. 在 **"YouTube 产品** 说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>步骤 2：在"如果您"合并 1 网站中配置 YouTube

第二步是在"则网吧 Merge1"网站上配置 YouTube 连接器。 若要了解如何配置 YouTube 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)。

单击"保存 **&完成"** 后，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器Microsoft 365 合规中心，请按照以下步骤操作：

1. 在"**将 YouTube 用户映射到Microsoft 365页上**，启用自动用户映射。 YouTube 项目包括一个称为 *Email* 的属性，该属性包含您组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-youtube-connector"></a>步骤 4：监视 YouTube 连接器

创建 YouTube 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **"YouTube"** 连接器以显示该飞出页，其中包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
