---
title: 设置一个安装 DataParser 连接器以将数据存档在 Microsoft 365
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
description: 了解如何设置和使用 17a-4 用户数据Parser 连接器，以导入和存档 Microsoft 365。
ms.openlocfilehash: 1302ae87900b765f0cdf3ed9e380c6c3361f0760678ef1f459827374a4be00e4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53900300"
---
# <a name="set-up-a-connector-to-archive-data-from-symphony"></a>设置连接器以存档来自"百年"的数据

使用来自 17a-4 LLC 的[一组用户数据Parser，将"](https://www.17a-4.com/Symphony-dataparser/)显示通信数据"导入并存档到组织Microsoft 365邮箱。 DataParser 包括一个配置为捕获第三方数据源中的项目，以及将这些项目导入到第三方数据源的 Microsoft 365。 该百年数据Parser 连接器将百年数据转换为电子邮件格式，然后将这些项目导入到用户邮箱Microsoft 365。

在将百年数据存储在用户邮箱中后，你可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用一个百年连接器导入数据并存档Microsoft 365可帮助你的组织遵守政府及法规策略。

## <a name="overview-of-archiving-symphony-data"></a>存档百年数据概述

以下概述介绍使用数据连接器在云中存档 Microsoft 365。

![17a-4 中用于百分百数据的存档工作流](../media/SymphonyDataParserConnectorWorkflow.png)

1. 你的组织与 17a-4 合作，以设置和配置部署 DataParser。

2. DataParser 会定期收集所有项目。 DataParser 还会将邮件内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的部署 DataParser 连接器连接到 DataParser，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. 在用户邮箱中创建名为 **"Inboxy DataParser"** 的"收件箱"文件夹中的子文件夹，并且"百年"项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个"百年"项目都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (步骤 1 中创建并完成安装) 的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。 默认情况下，此角色不会分配给角色组Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a>步骤 1：设置安装 DataParser 连接器

第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建一个 17a-4 连接器用于"安装"数据。

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **安装数据Parser**。

2. 在 **"百年数据Parser** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 17a-4 帐户并完成"安装数据Parser"连接向导中的步骤。

## <a name="step-2-configure-the-symphony-dataparser-connector"></a>步骤 2：配置部署 DataParser 连接器

与 17a-4 支持人员一起配置部署 DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

在将数据导入到邮箱之前，Microsoft 365数据Parser 连接器会自动将用户映射到其Microsoft 365。

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a>步骤 4：监视安装 DataParser 连接器

创建一个安装连接器后，可以在该连接器视图中查看Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择您创建的"完成"DataParser 连接器以显示该飞出页，其中包含连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
