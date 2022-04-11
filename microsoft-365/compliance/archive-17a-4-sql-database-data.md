---
title: 在Microsoft 365中设置用于存档SQL数据的连接器
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
description: 了解如何设置和使用 17a-4 SQL DataParser 连接器在 Microsoft 365 中导入和存档SQL数据。
ms.openlocfilehash: 1932e7830c1e23a07dbd9d6cbb968c3f12193d54
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761530"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a>设置连接器以存档SQL数据

使用 17a-4 LLC [中的 SQL DataParser](https://www.17a-4.com/sql-dataparser/) 将数据从SQL数据库导入和存档到Microsoft 365组织中的用户邮箱。 DataParser 包含一个SQL连接器，该连接器配置为从第三方数据源捕获项并将这些项导入到Microsoft 365。 SQL DataParser 连接器将SQL数据转换为电子邮件格式，然后在Microsoft 365中将这些项目导入到用户邮箱。

SQL数据存储在用户邮箱中后，可以应用Microsoft 365合规性功能，例如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用SQL连接器在Microsoft 365中导入和存档数据可以帮助组织遵守政府和法规政策。

## <a name="overview-of-archiving-sql-data"></a>存档SQL数据概述

以下概述介绍了在Microsoft 365中使用数据连接器存档SQL数据的过程。

![17a-4 中SQL数据的存档工作流。](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. 组织使用 17a-4 设置和配置 SQL DataParser。

2. DataParser 会定期收集SQL项。 DataParser 还会将邮件的内容转换为电子邮件格式。

3. 在Microsoft 365 合规中心中创建的 SQL DataParser 连接器连接到 DataParser 并将消息传输到 Microsoft 云中的安全Azure 存储位置。

4. 在用户邮箱中创建名为 **SQL DataParser** 的收件箱文件夹中的子文件夹，并将SQL项导入到该文件夹。 连接器使用 *Email* 属性的值确定要将项目导入到哪个邮箱。 每个SQL项都包含此属性，其中填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录到此帐户。

- 在步骤 1 (中创建 SQL DataParser 连接器并在步骤 3) 中完成该连接器的用户必须分配数据连接器管理员角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

- 此 17a-4 数据连接器在美国政府云Microsoft 365 GCC环境中可用。 第三方应用程序和服务可能涉及在Microsoft 365基础结构之外的第三方系统上存储、传输和处理组织的客户数据，因此Microsoft 365合规性和数据保护承诺不涵盖这些数据。 Microsoft 没有表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>步骤 1：设置 SQL DataParser 连接器

第一步是访问Microsoft 365 合规中心中的数据连接器页，并为SQL数据创建 17a-4 连接器。

1. 转到<https://compliance.microsoft.com>并单击 **“数据连接器** > **SQL DataParser**。

2. 在 **“SQL DataParser** 产品说明”页上，单击 **“添加连接器**”。

3. 在 **“服务条款”** 页上，单击 **“接受**”。

4. 输入标识连接器的唯一名称，然后单击 **“下一步**”。

5. 登录到 17a-4 帐户并完成 SQL DataParser 连接向导中的步骤。

## <a name="step-2-configure-the-sql-dataparser-connector"></a>步骤 2：配置 SQL DataParser 连接器

使用 17a-4 支持配置 SQL DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

SQL DataParser 连接器会在将数据导入到Microsoft 365之前自动将用户映射到其Microsoft 365电子邮件地址。

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>步骤 4：监视 SQL DataParser 连接器

创建 SQL DataParser 连接器后，可以在Microsoft 365 合规中心中查看连接器状态。

1. 转到 <https://compliance.microsoft.com> 左侧导航栏中并单击 **数据连接器** 。

2. 单击 **“连接器”** 选项卡，然后选择创建的SQL DataParser 连接器以显示浮出控件页，其中包含有关连接器的属性和信息。

3. 在 **“连接器状态与源**”下，单击 **“下载日志** ”链接打开 (或保存) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项。 稍后会提供对较大项的支持。
