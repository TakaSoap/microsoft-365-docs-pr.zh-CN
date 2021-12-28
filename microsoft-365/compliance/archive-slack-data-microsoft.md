---
title: 使用 Microsoft 提供的数据连接器Microsoft 365 Slack 电子数据展示数据进行存档
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
description: 了解如何设置和使用 Microsoft 提供的 Slack 电子数据展示数据连接器，以导入和存档即时消息数据。
ms.openlocfilehash: 71369f2330193120f252d108641e99434c9fba78
ms.sourcegitcommit: 27eb93a7d46bcbb9c948a50b0a8481ffd3832ca0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2021
ms.locfileid: "61612798"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>设置连接器以存档 Slack 电子数据展示数据 (预览) 

Microsoft 提供的 Slack 电子数据展示数据连接器可帮助你导入和存档即时消息数据 (如从组织的 Slack 工作区到 Microsoft 365 的邮件、附件、链接和修订) 。 数据连接器从 Slack API 提取数据，将其转换为电子邮件格式，然后将这些项目导入 Microsoft 365。 导入 Slack 数据后，可以将合规性解决方案（如诉讼保留、Advanced eDiscovery通信合规性和保留设置）应用到 Slack 内容。 使用 Slack 电子数据展示数据连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>存档 Slack 电子数据展示数据概述

以下概述介绍使用 Microsoft 数据连接器将 Slack 数据存档到 Microsoft 365。

![Slack 电子数据展示存档工作流。](../media/SlackMSFTConnectorWorkflow.png)

1. 你的组织使用 Slack 来设置和配置 Slack 工作区。

2. 设置数据连接器后，来自组织的 Slack 工作区的邮件将复制到 Microsoft 365。 数据连接器还会将聊天消息的内容转换为电子邮件格式。

3. 连接器将转换后的聊天消息导入到特定用户的邮箱。 在用户邮箱中创建名为 **Slack 电子数据** 展示的收件箱文件夹中的子文件夹，聊天消息项目将导入该文件夹。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 你的组织需要适用于 Slack Enterprise网格订阅。 有关详细信息，请参阅 [Slack 订阅和功能](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-)。

- 必须为创建数据连接器的用户分配 Slack 组织中的 **"组织** 所有者"应用程序角色。 有关详细信息，请参阅 Slack [中的角色类型](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack)。

- 获取组织的 Slack 企业帐户的用户名和密码。 创建数据连接器时，可以使用这些凭据登录此帐户。 还建议你在 Slack 组织中配置自动用户预配，以使用 SSO (单一) 。

- 必须为创建 Slack 电子数据展示连接器的用户分配邮箱导入导出Exchange Online。 若要在数据连接器页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会向角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-create-a-slack-ediscovery-connector"></a>步骤 1：创建 Slack 电子数据展示连接器

1. 转到左侧 <https://compliance.microsoft.com> 导航 **窗格，然后单击** "数据连接器"。

2. 在" **概述"** 选项卡上，单击 **"筛选** "并选择" **按 Microsoft"，** 然后应用筛选器。

3. 单击 **Slack 电子数据展示 (预览) 。**

4. 在 **Slack 电子数据展示 (预览)** 产品说明"页上，单击"**添加连接器"。**

5. 在"**服务条款向导**"页上，单击"接受 **"。**

6. 输入标识连接器的唯一名称，然后单击下一 **步**。 创建连接器后，输入的名称将标识"数据连接器"页上的连接器。

## <a name="step-2-sign-into-your-slack-organization"></a>步骤 2：登录到 Slack 组织

1. 在" **登录到 Slack"** 向导页上，单击 **"登录到 Slack"** 以登录到组织的 Slack 工作区。

2. 在 **Slack"登录到工作区"** 页上，键入要存档其数据的工作区的名称，然后单击"继续 **"。**

   将显示一个页面，其中显示 Slack 工作区的名称和登录提示。

3. 单击字符串 **"Org Owners 也可以在此处登录"中的链接**。

4. 在工作区登录页面上，输入你组织的 Slack 企业帐户的电子邮件地址和密码，然后单击 **登录。**

   成功登录后，将显示一个页面，请求连接器应用访问 Slack 组织的权限。

5. 单击 **"** 允许"以允许应用管理你的组织。

   单击"允许 **"** 后，Slack 页面将关闭，并显示连接器向导中的"将 **Slack Microsoft 365用户** 映射到用户"页面。

## <a name="step-3-map-users-and-select-data-types-to-import"></a>步骤 3：映射用户并选择要导入的数据类型

1. 配置以下一个或两个选项以将 Slack 用户映射到其Microsoft 365邮箱。

   - **自动用户映射**。 选择此选项可自动将 Slack 用户名映射到Microsoft 365邮箱。 连接器使用 Email 属性的值（每个 *Slack* 邮件或项目都包含该值）来操作。 此属性填充了邮件每个参与者的电子邮件地址。 如果连接器可以将电子邮件地址与相应的Microsoft 365关联，该项目将导入到这些Microsoft 365邮箱。 若要使用此选项，必须为 Slack 组织配置 SSO。

   - **自定义用户映射**。 除了使用自定义用户映射之外，还可以选择 (自定义) 映射。 使用此选项，必须创建 CSV 文件，然后将用户的 Slack 成员 ID 映射到其Microsoft 365电子邮件地址。 为此，请单击"下载 **CSV** 映射模板"，使用组织中所有用户的 Slack 成员 ID 和 Microsoft 365 电子邮件地址填充 CSV 文件，然后选择 CSV 文件并将其上载到向导。 确保不要更改 CSV 文件的列标题。 以下是 CSV 映射文件的示例：

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > 用户的成员 ID 可以通过单击 ...用户配置文件中的"更多"按钮，然后选择"**复制成员 ID"。** 或者，可以使用 Slack [users.list API](https://api.slack.com/methods/users.list) 方法获取 Slack 团队所有成员的 ID。

   如果启用自动用户映射并提供自定义映射文件，连接器将首先查看自定义映射文件，以将 Slack 用户映射到 Microsoft 365邮箱。 如果连接器找不到与 Slack Microsoft 365对应的有效用户，连接器将使用 Slack 项目的 *Email* 属性。 如果连接器在自定义映射文件或邮件Microsoft 365 *Email* 属性中找不到有效的邮件用户，则不导入该项目。

2. 在" **选择要导入的数据类型"向导** 页上，选择要导入的 Slack 数据类型。 如果要从所有频道导入邮件，请选择所有选项。 否则，请仅选择要导入的数据类型。

     除了 Slack 消息之外，还可以指定要导入到 Slack 的其他类型的 Slack Microsoft 365。 

3. 配置要导入的数据类型后，单击"下一步"，查看连接器设置，然后单击"**完成"** 以创建连接器。

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>步骤 4：监视 Slack 电子数据展示连接器

创建 Slack 电子数据展示连接器后，可以在"数据展示"视图中查看Microsoft 365 合规中心。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **Slack 电子数据** 展示连接器以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
