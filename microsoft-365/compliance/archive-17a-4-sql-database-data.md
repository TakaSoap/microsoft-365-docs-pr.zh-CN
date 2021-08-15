---
title: 设置连接器以在SQL中存档Microsoft 365
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
description: 了解如何设置和使用 17a-4 SQL DataParser 连接器在 Microsoft 365 中导入和SQL数据。
ms.openlocfilehash: 6820400d215f2ed94f9741e877bee54c11ab746ebb0f6933840f3d5e9b3792dc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53872240"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a>设置连接器以存档SQL数据

使用 SQL 17a-4 LLC 中的数据[Parser](https://www.17a-4.com/sql-dataparser/)将 SQL 数据库中的数据导入并存档到 Microsoft 365 组织中。 DataParser 包括一SQL连接器，该连接器配置为捕获第三方数据源中的项目，并导入这些项Microsoft 365。 DataParser SQL连接器会将SQL数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在SQL邮箱中存储数据后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 SQL 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-sql-data"></a>存档数据SQL概述

以下概述介绍使用数据连接器在数据连接器中SQL数据Microsoft 365。

![17a-4 SQL数据的存档工作流](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. 你的组织使用 17a-4 来设置和配置 SQL DataParser。

2. DataParser 会SQL收集项目。 DataParser 还会将邮件内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 SQL DataParser 连接器连接到 DataParser，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. "收件箱"文件夹中名为 **SQL DataParser** 的子文件夹是在用户邮箱中创建的，SQL项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个SQL项都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (中创建 SQL DataParser 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。 默认情况下，此角色不会分配给角色组Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>步骤 1：设置 SQL DataParser 连接器

第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建一个 17a-4 连接器SQL数据。

1. 转到 ， <https://compliance.microsoft.com> 然后单击 **DataParser**  >  **SQL连接器**。

2. 在 **"SQL产品说明"** 页上，单击"添加 **连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到您的 17a-4 帐户并完成 SQL DataParser 连接向导中的步骤。

## <a name="step-2-configure-the-sql-dataparser-connector"></a>步骤 2：配置 SQL DataParser 连接器

与 17a-4 支持人员一起SQL DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

DataParser SQL连接器会自动将用户映射到其 Microsoft 365 电子邮件地址，然后再将数据导入Microsoft 365。

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>步骤 4：监视 SQL DataParser 连接器

创建一个SQL DataParser 连接器后，可以在该连接器的 Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择SQL DataParser 连接器，以显示包含有关连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
