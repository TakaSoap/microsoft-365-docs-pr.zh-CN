---
title: 设置连接器以存档 MS 数据库SQL数据
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
description: 管理员可以设置连接器以从 MS 数据库导入和存档SQL数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164209"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>设置连接器以存档 MS 数据库SQL数据

使用 Microsoft 365 合规中心中的 Microsoft 365 连接器将数据从 MS SQL 数据库导入并存档到 Microsoft 365 组织的用户邮箱。 Microsoft 提供了 MS SQL 数据库导入程序连接器，该连接器配置为使用 XML 配置文件捕获数据库中的项目，以及将这些项目导入到 Microsoft 365。 连接器将 MS SQL 数据库的内容转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

MS SQL数据库中的内容存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 MS SQL 数据库连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-the-ms-sql-data"></a>对 MS 数据进行存档SQL概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 MS SQL 数据的过程。

![MS 存档数据的SQL工作流](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 您的组织与 MS SQL 数据库提供程序一起设置和配置 MS SQL 数据库网站。

2. 每 24 小时一次，MS SQL 数据库项目将复制到"中""合并 1"网站。 连接器还会将此内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心创建的 MS SQL 数据库导入程序连接器每天连接到一个 Microsoft Merge1 网站，将邮件传输至 Microsoft 云中的安全 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将已转换的 MS SQL 数据库项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **"MS** SQL导入程序"的"收件箱"文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 MS SQL Database 的每一项都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>准备工作

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (中创建 MS SQL 数据库导入程序连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中任何角色组。 可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>步骤 1：设置 MS SQL数据库导入程序连接器

第一步是访问 Microsoft365 合规中心的"数据连接器"页，并创建 MS SQL 数据库的连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击"数据连接器 MS SQL  >  **导入程序"。**

2. 在 **"MS SQL导入程序** 产品说明"页上，单击"**添加新连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>步骤 2：在 SQL Merge1 网站上配置 MS 数据库导入程序连接器

第二步是在 Merge1 SQL配置 MS 数据库导入程序连接器。 若要了解如何配置 MS 数据库导入程序SQL，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器设置，请按照以下步骤操作：

1. 在" **将 MS SQL导入程序用户映射到 Microsoft 365** 用户"页上，启用自动用户映射。 MS SQL 数据库项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>步骤 4：监视 MS SQL数据库导入程序连接器

创建 MS 数据库导入SQL程序连接器后，可以在 Microsoft 365 合规中心查看连接器状态。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡 **，然后选择"MS SQL数据库** 导入程序连接器"以显示包含连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。