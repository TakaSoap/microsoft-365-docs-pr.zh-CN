---
title: 设置连接器以将 Slack 数据存档在 Microsoft 365
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
description: 了解如何设置和使用 17a-4 Slack DataParser 连接器以在 17a-4 Slack 中导入和存档 Slack Microsoft 365。
ms.openlocfilehash: 918fbc9e08b874f9ab82bf8e42cac4501ff6bdc9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155270"
---
# <a name="set-up-a-connector-to-archive-slack-data"></a>设置连接器以存档 Slack 数据

使用[17a-4 LLC 中的 DataParser](https://www.17a-4.com/slack-dataparser/)将数据从 Slack 平台导入并存档到组织Microsoft 365邮箱。 DataParser 包括一个 Slack 连接器，该连接器配置为捕获来自第三方数据源的项目，以及将这些项目导入Microsoft 365。 Slack DataParser 连接器将 Slack 数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365。

Slack 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Slack 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-slack-data"></a>存档 Slack 数据概述

以下概述介绍使用数据连接器在数据连接器中存档 Slack Microsoft 365。

![17a-4 Slack 数据的存档工作流。](../media/SlackDataParserConnectorWorkflow.png)

1. 你的组织使用 17a-4 来设置和配置 Slack DataParser。

2. DataParser 会定期收集 Slack 项目。 DataParser 还会将邮件内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 Slack DataParser 连接器连接到 DataParser，将邮件Azure 存储 Microsoft 云中的安全位置。

4. 在用户邮箱中创建名为 **Slack DataParser** 的"收件箱"文件夹中的子文件夹，Slack 项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 Slack 项目都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 中创建 Slack DataParser 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会向角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 此数据连接器可用于美国政府GCC中Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-a-slack-dataparser-connector"></a>步骤 1：设置 Slack DataParser 连接器

第一步是访问数据连接器页，Microsoft 365 合规中心 Slack 数据创建 17a-4 连接器。

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据连接器  >  **Slack DataParser**。

2. 在 **Slack DataParser** 产品说明页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 17a-4 帐户并完成 Slack DataParser 连接向导中的步骤。

## <a name="step-2-configure-the-slack-dataparser-connector"></a>步骤 2：配置 Slack DataParser 连接器

与 17a-4 支持人员一起配置 Slack DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

Slack DataParser 连接器会自动将用户映射到Microsoft 365电子邮件地址，然后再将数据导入Microsoft 365。

## <a name="step-4-monitor-the-slack-dataparser-connector"></a>步骤 4：监视 Slack DataParser 连接器

创建 Slack DataParser 连接器后，可以查看该连接器在 Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择您创建的 Slack DataParser 连接器以显示该飞出页，其中包含连接器的属性和信息。

3. 在 **"源的连接器状态"下**， **单击"下载** 日志"链接 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
