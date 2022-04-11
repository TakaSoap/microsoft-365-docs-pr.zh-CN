---
title: 使用 Microsoft 提供的数据连接器将 Slack 电子数据展示数据存档到Microsoft 365
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
description: 了解如何设置和使用 Microsoft 提供的 Slack 电子数据展示数据连接器来导入和存档即时消息数据。
ms.openlocfilehash: 7ff8140ee75c146f79f14fbd474ab4e6780156ad
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760880"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>设置连接器以存档 Slack 电子数据展示数据 (预览) 

Microsoft 提供的 Slack 电子数据展示数据连接器可帮助你导入和存档即时消息数据 (，例如消息、附件、链接和修订，) 从组织的 Slack 工作区Microsoft 365。 数据连接器从 Slack API 提取数据，将其转换为电子邮件格式，然后在Microsoft 365中将这些项目导入到用户邮箱。 导入 Slack 数据后，可以将合规性解决方案（例如诉讼保留、Advanced eDiscovery、通信符合性和保留设置）应用到 Slack 内容。 使用 Slack 电子数据展示数据连接器在Microsoft 365中导入和存档数据可以帮助组织遵守政府和法规政策。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>存档 Slack 电子数据展示数据概述

以下概述介绍了使用 Microsoft 数据连接器在Microsoft 365中存档 Slack 数据的过程。

![Slack 电子数据展示存档工作流。](../media/SlackMSFTConnectorWorkflow.png)

1. 组织使用 Slack 设置和配置 Slack 工作区。

2. 设置数据连接器后，来自组织 Slack 工作区的消息将复制到Microsoft 365中的用户邮箱。 数据连接器还会将聊天消息的内容转换为电子邮件格式。

3. 连接器将转换后的聊天消息导入到特定用户的邮箱。 在用户邮箱中创建名为 **Slack 电子数据展示** 的收件箱文件夹中的子文件夹，并将聊天消息项导入到该文件夹。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- 组织需要 Slack Enterprise网格订阅。 有关详细信息，请参阅 [Slack 订阅和功能](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-)。

- 创建数据连接器的用户必须在其 Slack 组织中分配 **组织所有者** 应用程序角色。 有关详细信息，请参阅 [Slack 中的角色类型](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack)。

- 获取组织的 Slack 企业帐户的用户名和密码。 创建数据连接器时，可以使用这些凭据登录到此帐户。 此外，还建议在 Slack 组织中将自动用户预配配置为使用单一登录 (SSO) 。 [安全&合规中心中的角色](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)

- 创建 Slack 电子数据展示连接器的用户必须分配 Data Connector 管理员角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

## <a name="step-1-create-a-slack-ediscovery-connector"></a>步骤 1：创建 Slack 电子数据展示连接器

1. 转到 <https://compliance.microsoft.com> 左侧导航窗格中并单击 **“数据连接器** ”。

2. 在“ **概述** ”选项卡上，单击 **“筛选器** ”并选择 **“由 Microsoft**”，然后应用筛选器。

3. 单击 **Slack 电子数据展示 (预览)**。

4. 在 **Slack 电子数据展示 (预览)** 产品说明页上，单击 **“添加连接器**”。

5. 在 **“服务条款** 向导”页上，单击 **“接受**”。

6. 输入标识连接器的唯一名称，然后单击 **“下一步**”。 创建连接器后，输入的名称将标识 **数据连接器页上的连接器** 。

## <a name="step-2-sign-into-your-slack-organization"></a>步骤 2：登录到 Slack 组织

1. 在 **“登录到 Slack** 向导”页上，单击 **“登录到 Slack** ”登录到组织的 Slack 工作区。

2. 在“Slack **登录到工作区** ”页上，键入要从中存档数据的工作区的名称，然后单击 **“继续**”。

   将显示一个页面，其中包含 Slack 工作区的名称和登录提示。

3. 单击字符串 **组织所有者中的链接也可以在此处登录**。

4. 在工作区登录页上，输入组织 Slack 企业帐户的电子邮件地址和密码，然后单击 **“登录**”。

   成功登录后，将显示一个页面，请求连接器应用访问 Slack 组织的权限。

5. 单击 **“允许** ”以允许应用管理组织。

   单击 **“允许**”后，Slack 页面关闭，并显示连接器向导中 **“映射 Slack 电子数据展示用户到Microsoft 365用户**”页。

## <a name="step-3-specify-the-users-to-import-data-for"></a>步骤 3：指定要导入数据的用户

选择以下选项之一，指定要导入其 Slack 电子数据展示数据的用户。

- **组织中的所有用户**。 选择此选项可导入所有用户的数据。

- **只有处于诉讼保留状态的用户**。 选择此选项仅导入邮箱处于诉讼保留状态的用户的数据。 此选项将数据导入到将 LitigationHoldEnabled 属性设置为 True 的用户邮箱。 有关详细信息，请参阅 [“创建诉讼保留](create-a-litigation-hold.md)”。

## <a name="step-4-map-users-and-select-data-types-to-import"></a>步骤 4：映射用户并选择要导入的数据类型

1. 配置以下一个或两个选项，将 Slack 用户映射到其Microsoft 365邮箱。

   - **自动用户映射**。 选择此选项可自动将 Slack 用户名映射到Microsoft 365邮箱。 连接器使用 *Email* 属性的值来执行此操作，每个 Slack 消息或项都包含该属性。 此属性填充了邮件的每个参与者的电子邮件地址。 如果连接器可以将电子邮件地址与相应的Microsoft 365用户关联，则将该项目导入到这些用户的Microsoft 365邮箱。 若要使用此选项，必须为 Slack 组织配置 SSO。

   - **自定义用户映射**。 你还可以选择使用自定义用户映射，而不是 (或) 自动用户映射。 使用此选项，必须创建并上传一个 CSV 文件，该文件将用户的 Slack 成员 ID 映射到其Microsoft 365电子邮件地址。 为此，请单击 **“下载 CSV 映射模板**”，使用 Slack 成员 ID 填充 CSV 文件，并为组织中的所有用户Microsoft 365电子邮件地址，然后选择 CSV 文件并将其上传到向导。 请务必不要更改 CSV 文件中的列标题。 下面是 CSV 映射文件的示例：

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > 可以通过单击 ... 获取用户的成员 ID用户配置文件中的“更多”按钮，然后选择 **“复制成员 ID**”。 或者，可以使用 Slack [users.list API 方法](https://api.slack.com/methods/users.list) 获取 Slack 团队所有成员的 ID。

   如果启用自动用户映射并提供自定义映射文件，连接器将首先查看自定义映射文件，将 Slack 用户映射到Microsoft 365邮箱。 如果连接器找不到与 Slack 用户相对应的有效Microsoft 365用户，则连接器将使用 Slack 项目的 *Email* 属性。 如果连接器在邮件项的自定义映射文件或 *Email* 属性中找不到有效的Microsoft 365用户，则不会导入该项目。

2. 在 **“选择要导入向导的数据类型** ”页上，选择要导入的 Slack 数据类型。 如果要从所有通道导入消息，请选择所有选项。 否则，请仅选择要导入的数据类型。

     除了 Slack 消息，还可以指定要导入到Microsoft 365的其他类型的 Slack 内容。 

3. 配置要导入的数据类型后，单击 **“下一步**”，查看连接器设置，然后单击 **“完成** ”创建连接器。

## <a name="step-5-monitor-the-slack-ediscovery-connector"></a>步骤 5：监视 Slack 电子数据展示连接器

创建 Slack 电子数据展示连接器后，可以在Microsoft 365 合规中心中查看连接器状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 左侧导航栏中并单击 **数据连接器** 。

2. 单击 **“连接器”** 选项卡，然后选择 **Slack 电子数据展示** 连接器以显示浮出控件页，其中包含有关连接器的属性和信息。

3. 在 **“连接器状态与源**”下，单击 **“下载日志** ”链接打开 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项。 稍后会提供对较大项的支持。
