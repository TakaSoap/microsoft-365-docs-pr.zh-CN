---
title: 设置连接器以在聊天连接 ICE 聊天Microsoft 365
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
description: 了解如何设置和使用 17a-4 ICE 连接 Chat DataParser 连接器，以导入和存档 连接 中的 ICE 聊天Microsoft 365。
ms.openlocfilehash: 632426422bd8f9db984b66fdea08276b7345441c
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643002"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a>设置连接器以存档 ICE 连接聊天数据

使用 17a-4 LLC 中的[ICE DataParser](https://www.17a-4.com/ice-dataparser/)将 ICE 连接 Chat 数据导入并存档到 Microsoft 365 组织的用户邮箱。 DataParser 包括一个 ICE 聊天连接器，该连接器配置为捕获来自第三方数据源的项目，并导入这些项Microsoft 365。 ICE DataParser 连接器将 ICE 连接 聊天数据转换为电子邮件格式，然后将这些项目导入 Microsoft 365。

ICE 连接聊天数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 ICE DataParser 连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-ice-chat-data"></a>存档 ICE 聊天数据概述

以下概述介绍使用数据连接器在聊天中存档 ICE 连接 Chat 数据Microsoft 365。

![ICE 的存档工作流连接 17a-4 聊天数据。](../media/ICEChatDataParserConnectorWorkflow.png)

1. 你的组织与 17a-4 一起设置和配置 ICE DataParser。

2. DataParser 会连接 ICE 聊天聊天项目。 DataParser 还会将邮件内容转换为电子邮件格式。

3. 在 microsoft 云中创建的 ICE DataParser Microsoft 365 合规中心连接到 DataParser，将邮件传输至 Microsoft 云中的Azure 存储位置。

4. 在用户邮箱中创建名为 **ICE DataParser** 的收件箱文件夹中的子文件夹，ICE 连接 Chat 项目将导入该文件夹。 连接器使用 Email 属性的值确定将项目导入到哪个 *邮箱* 。 每个 ICE 连接 聊天项目都包含此属性，该属性填充了每个参与者的电子邮件地址。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 为 Microsoft 连接器创建 DataParser 帐户。 为此，请联系 [17a-4 LLC](https://www.17a-4.com/contact/)。 在步骤 1 中创建连接器时，需要登录此帐户。

- 必须在步骤 1 中创建 ICE DataParser 连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页的"数据连接器"页上添加 **连接器，需要** 此Microsoft 365 合规中心。 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到"管理"角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此 17a-4 数据连接器在美国政府云GCC环境中Microsoft 365可用。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-set-up-an-ice-dataparser-connector"></a>步骤 1：设置 ICE DataParser 连接器

第一步是访问 Microsoft 365 合规中心 中的"数据连接器"页，并创建 ICE 连接 17a-4 连接器。

1. 转到 ， <https://compliance.microsoft.com> 然后单击数据 **连接器**  >  **ICE DataParser**。

2. 在 **ICE DataParser** 产品说明页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到你的 17a-4 帐户并完成 ICE DataParser 连接向导中的步骤。

## <a name="step-2-configure-the-ice-dataparser-connector"></a>步骤 2：配置 ICE DataParser 连接器

与 17a-4 支持人员一起配置 ICE DataParser 连接器。

## <a name="step-3-map-users"></a>步骤 3：映射用户

ICE DataParser 连接器会自动将用户映射到其Microsoft 365电子邮件地址，然后再将数据导入Microsoft 365。

## <a name="step-4-monitor-the-ice-dataparser-connector"></a>步骤 4：监视 ICE DataParser 连接器

创建 ICE DataParser 连接器后，可以查看连接器在连接器Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择您创建的 ICE DataParser 连接器以显示浮出控件页，其中包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"下**， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
