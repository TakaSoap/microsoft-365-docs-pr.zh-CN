---
title: 在 Microsoft 365 中设置连接器以存档 YouTube 数据
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
description: 管理员可以设置连接器，将 YouTube 数据从 Veritas 导入并存档到Microsoft 365。 使用此连接器可在Microsoft 365中存档来自第三方数据源的数据。 存档此数据后，可以使用符合性功能（如法定保留、电子数据展示和保留策略）来管理第三方数据。
ms.openlocfilehash: 20343411a77210845bfad22e34dfcada6f8ca9b9
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759448"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>设置连接器以存档 YouTube 数据

使用Microsoft 365 合规中心中的 Veritas 连接器将数据从 YouTube 导入和存档到Microsoft 365组织中的用户邮箱。 Veritas 提供了一个连接器，该连接器配置为从第三方数据源捕获项并将这些项导入到Microsoft 365。 连接器将聊天、附件、任务、笔记和帖子等内容从 YouTube 转换为电子邮件格式，然后将这些项目导入Microsoft 365中的用户邮箱。

在用户邮箱中存储 YouTube 数据后，可以应用Microsoft 365合规性功能，例如诉讼保留、电子数据展示、保留策略和保留标签。 使用 YouTube 连接器在Microsoft 365中导入和存档数据可以帮助组织遵守政府和法规政策。

## <a name="overview-of-archiving-youtube-data"></a>YouTube 数据存档概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 YouTube 数据的过程。

![为 YouTube 数据存档工作流。](../media/YouTubeConnectorWorkflow.png)

1. 组织与 YouTube 协作，设置和配置 YouTube 网站。

2. 每 24 小时一次，YouTube 项目将复制到 Veritas Merge1 网站。 连接器还会将 YouTube 项目转换为电子邮件格式。

3. 你在Microsoft 365 合规中心中创建的 YouTube 连接器每天连接到 Veritas Merge1 站点，并将 YouTube 内容传输到 Microsoft 云中的安全Azure 存储位置。

4. 连接器使用自动用户映射 *的电子邮件属性的* 值将转换后的项目导入到特定用户的邮箱，如 [步骤 3](#step-3-map-users-and-complete-the-connector-setup) 中所述。 在用户邮箱中创建名为 **YouTube** 的收件箱文件夹中的子文件夹，并将项目导入到该文件夹。 连接器使用 *Email* 属性的值确定要将项目导入到哪个邮箱。 每个 YouTube 项目都包含此属性，其中填充了该项目的每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- 为 Microsoft 连接器创建 Merge1 帐户。 若要创建此帐户，请联系 [Veritas 客户支持部门](https://www.veritas.com/form/requestacall/ms-connectors-contact)。 在步骤 1 中创建连接器时，需要登录到此帐户。

- 创建一个 YouTube 应用程序以从 YouTube 帐户提取数据。 有关创建应用程序的分步说明，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)。

- 在步骤 1 (中创建 YouTube 连接器并在步骤 3) 中完成该连接器的用户必须分配数据连接器管理员角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

## <a name="step-1-set-up-the-youtube-connector"></a>步骤 1：设置 YouTube 连接器

第一步是访问Microsoft 365 合规中心中的 **“数据连接器”** 页，并为 YouTube 数据创建连接器。

1. 转到 <https://compliance.microsoft.com> ，然后单击 **“数据连接器** > **YouTube**”。

2. 在 **YouTube** 产品说明页上，单击 **“添加连接器**”。

3. 在 **“服务条款”** 页上，单击 **“接受**”。

4. 输入标识连接器的唯一名称，然后单击 **“下一步**”。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>步骤 2：在 Veritas Merge1 网站上配置 YouTube

第二步是在 Veritas Merge1 网站上配置 YouTube 连接器。 有关如何配置 YouTube 连接器的信息，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)。

单击 **“保存&完成**”后，将显示Microsoft 365 合规中心连接器向导中的 **“用户映射**”页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并在Microsoft 365 合规中心中完成连接器设置，请执行以下步骤：

1. 在 **Map YouTube 用户Microsoft 365用户** 页面上，启用自动用户映射。 YouTube 项目包括名为 *“电子邮件*”的属性，其中包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365用户关联，则项将导入到该用户的邮箱。

2. 单击 **“下一步**”，查看设置，然后转到 **“数据连接器** ”页，查看新连接器的导入过程进度。

## <a name="step-4-monitor-the-youtube-connector"></a>步骤 4：监视 YouTube 连接器

创建 YouTube 连接器后，可以在Microsoft 365 合规中心中查看连接器状态。

1. 转到 <https://compliance.microsoft.com/> 左侧导航栏中并单击 **数据连接器** 。

2. 单击 **“连接器”** 选项卡，然后选择 **YouTube** 连接器以显示浮出控件页，其中包含有关连接器的属性和信息。

3. 在 **“连接器状态与源**”下，单击 **“下载日志** ”链接打开 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项。 稍后会提供对较大项的支持。
