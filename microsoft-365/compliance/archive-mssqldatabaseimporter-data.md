---
title: 设置连接器以存档 MS SQL 数据库
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
description: 管理员可以设置连接器以从 MS 服务器导入和存档SQL 数据库。 通过此连接器，可以在 Microsoft 365 中存档来自第三方数据源Microsoft 365。 在存档此数据后，可以使用合规性功能（如合法保留、内容搜索和保留策略）管理第三方数据。
ms.openlocfilehash: 9bd83226973b0a51990382f02b17fba0da28d91b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59170681"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>设置连接器以存档 MS SQL 数据库

使用 Microsoft 365 合规中心 中的一个 SQL 数据库 连接器，将数据从 MS SQL 数据库 导入并存档到组织Microsoft 365邮箱。 对于配置为使用 SQL 数据库 XML 配置文件从数据库捕获项目，以及将这些项目导入数据库，Microsoft 365。 连接器将 MS 邮箱SQL 数据库转换为电子邮件格式，然后将这些项目导入 Microsoft 365。

MS 中的内容SQL 数据库存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签。 使用 MS SQL 数据库 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-the-ms-sql-data"></a>对 MS 存档数据进行SQL概述

以下概述介绍使用连接器将 MS SQL数据存档在Microsoft 365。

![MS 存档数据的SQL工作流。](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 您的组织与 MS SQL 数据库提供商合作，以设置和配置 MS SQL 数据库网站。

2. 每 24 小时一次，MS SQL 数据库项目将复制到该"是否合并 1"网站。 连接器还会将此内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 MS SQL 数据库 导入程序连接器每天连接到一个 Microsoft 云中的一个安全 Azure 存储 位置，并连接到该站点。

4. 连接器使用自动用户映射的 *Email* 属性值将已转换的 MS SQL 数据库 项目导入到特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 "收件箱"文件夹中名为 **"MS SQL 数据库导入** 程序"的子文件夹是在用户邮箱中创建的，并且项目会导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 MS 集合SQL 数据库项都包含此属性，其中填充了项目每个参与者的电子邮件地址。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建一个 Microsoft Merge1 帐户。 若要创建帐户，请联系["用户支持人员"。](https://www.veritas.com/content/support/) 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (中创建 MS SQL 数据库 导入程序连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色不会分配给角色组Exchange Online。 可以将邮箱导入导出角色添加到邮箱管理角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>步骤 1：设置 MS SQL 数据库导入程序连接器

第一步是访问"数据连接器"页，Microsoft 365 合规中心为 MS 连接器创建SQL 数据库。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击数据连接器  >  **MS SQL 数据库导入程序**。

2. 在 **"MS SQL 数据库导入程序** 产品说明"页上，单击"**添加新连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>步骤 2：在 SQL 数据库 Merge1 网站上配置 MS 导入程序连接器

第二步是在 Merge1 SQL 数据库配置 MS 导入程序连接器。 若要了解如何配置 MS 连接器导入程序SQL 数据库，请参阅[Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。

单击"保存 **&完成****"后**，将显示连接器向导中的"用户Microsoft 365 合规中心页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成连接器设置，请按照以下步骤操作：

1. 在"**将 MS SQL 数据库导入程序用户Microsoft 365"页上，** 启用自动用户映射。 MS SQL 数据库项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与Microsoft 365关联，则项目会导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>步骤 4：监视 MS SQL 数据库导入程序连接器

创建 MS 导入SQL 数据库连接器后，可以在"导入程序"中查看Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 **"MS SQL 数据库****导入** 程序"连接器以显示该飞出页，其中包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。