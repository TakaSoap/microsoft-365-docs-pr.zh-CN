---
title: 设置连接器以在Skype for Business Server中存档Microsoft 365
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
description: 了解如何设置和使用 17a-4 Skype for Business Server DataParser 连接器在 Microsoft 365 中导入和Skype for Business Server数据。
ms.openlocfilehash: 1cbb0873a86af099665cf8bf6353ce351bafb3cd
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400411"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-server-data"></a>设置连接器以存档Skype for Business Server数据

使用 Skype Server [DataParser](https://www.17a-4.com/skype-server-dataparser/)从 17a-4 LLC 导入数据，Skype for Business Server数据并存档到组织的用户Microsoft 365邮箱。 DataParser 包括一Skype for Business连接器，该连接器配置为捕获来自第三方数据源的项目，以及将这些项目导入Microsoft 365。 此Skype for Business Server DataParser 连接器会将Skype for Business Server数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365 中的用户邮箱。

在Skype for Business Server邮箱中存储数据后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 Skype for Business Server 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-skype-for-business-server-data"></a>存档数据Skype for Business Server概述

以下概述介绍使用数据连接器在数据连接器中Skype for Business Server数据Microsoft 365。

![17a-4 Skype for Business Server数据的存档工作流](../media/SkypeServerDataParserConnectorWorkflow.png)

1. 您的组织与 17a-4 一起设置和配置 Skype for Business Server DataParser。

2. DataParser 会Skype for Business Server收集项目。 DataParser 还会将邮件内容转换为电子邮件格式。

3. 在 Microsoft 365 合规中心 创建的 Skype for Business Server DataParser 连接器连接到 DataParser，将邮件传输至 Microsoft 云中的安全 Azure 存储 位置。

4. "收件箱"文件夹中名为 **Skype for Business Server DataParser** 的子文件夹是在用户邮箱中创建的，Skype for Business Server项目将导入到该文件夹中。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个Skype for Business Server项都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 (中创建 Skype for Business Server DataParser 连接器并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加连接器，Microsoft 365 合规中心。 默认情况下，不会向角色组分配此角色Exchange Online。 可以将邮箱导入导出角色添加到组织管理角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

## <a name="step-1-set-up-a-skype-for-business-server-dataparser-connector"></a>步骤 1：设置 Skype for Business Server DataParser 连接器

第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建一个 17a-4 连接器Skype for Business Server数据。

1. 转到 ， <https://compliance.microsoft.com> 然后单击 **DataParser**  >  **Skype for Business Server连接器**。

2. 在 **"Skype for Business Server DataParser** 产品说明"页上，单击"添加 **连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到您的 17a-4 帐户并完成 Skype for Business Server DataParser 连接向导中的步骤。

## <a name="step-2-configure-the-skype-for-business-server-dataparser-connector"></a>步骤 2：配置 Skype for Business Server DataParser 连接器

与 17a-4 支持人员一起配置 Skype for Business Server DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

DataParser Skype for Business Server连接器会自动将用户映射到其 Microsoft 365 电子邮件地址，然后再将数据导入Microsoft 365。

## <a name="step-4-monitor-the-skype-for-business-server-dataparser-connector"></a>步骤 4：监视 Skype for Business Server DataParser 连接器

创建一个Skype for Business Server DataParser 连接器后，可以查看该连接器在Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择Skype for Business Server DataParser 连接器，以显示包含有关连接器的属性和信息的飞出页。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
