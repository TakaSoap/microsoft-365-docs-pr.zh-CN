---
title: 将数据从 CellTrust SL2 平台存档到Microsoft 365
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
description: 了解如何设置和使用 CellTrust SL2 数据连接器来导入和存档移动应用数据。
ms.openlocfilehash: 4d54e424f326c42ac92ec5f0fc71a22e06351b7a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158426"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365"></a>将数据从 CellTrust SL2 存档到Microsoft 365

CellTrust SL2 捕获移动通信数据，并集成了领先的存档技术，以满足 FINRA、HIPAA、FOIA 和 TCPA 等法规的电子发现要求。 SL2 数据连接器将移动通信项目导入Microsoft 365。 本文介绍使用 CellTrust SL2 数据连接器进行存档Microsoft 365 SL2 与数据库集成的过程。 完成此过程假定你已订阅 CellTrust SL2 服务，并且熟悉 SL2 体系结构。 有关 CellTrust SL2 的信息，请参阅 <https://www.celltrust.com> 。

将数据导入 Microsoft 365 中的用户邮箱后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、Microsoft 365保留策略和通信合规性。 使用 CellTrust SL2 数据连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>使用 CellTrust SL2 数据连接器进行存档的概述

CellTrust 的 SL2 平台捕获来自多个源的通信数据。 SL2 数据源可以是个人到个人 (P2P) 或应用程序到 (A2P) 。 本文中介绍的过程仅适用于 P2P 数据源。 对于所有 P2P 数据源，协作中至少有一方是订阅 SL2 服务的 SL2 用户。 以下概述介绍在 Microsoft 365 中使用 CellTrust SL2 数据连接器的过程。

![CellTrust SL2 服务的存档工作流。](../media/CellTrustSL2ConnectorWorkflow.png)

1. SL2 用户在服务中向 SL2 服务发送和接收Microsoft Azure。

2. 你的组织在 CellTrust 的 SL2 云服务环境中具有 SL2 域。 你的域可能有一个或多个组织单位 (OUS) 。 SL2 云服务将你的数据传输到 Microsoft Azure 平台中的高度安全区域，以便你的数据永远不会离开Microsoft Azure环境。 根据 SL2 计划 (Enterprise、SMB 或政府) ，你的域托管在 Microsoft Azure 政府或政府Microsoft Azure上。

3. 创建 CellTrust SL2 数据连接器后，你的域和 (无论 SL2 计划) ，都开始将数据发送到 Microsoft 365。 数据源的结构支持基于数据源、OUS 或域本身的报告。 因此，贵组织只需要一个连接器来馈送所有数据源Microsoft 365。

4. 连接器在每个映射用户下创建一个文件夹，该文件夹具有Office 365 **CellTrust SL2** 许可证。 此映射使用电子邮件地址将 CellTrust SL2 用户Office 365邮箱。 如果 CellTrust SL2 中的用户 ID 与 Office 365不匹配，将不会存档用户的数据。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

- 验证 CellTrust SL2 云服务环境中是否具有域。 有关获取生产或试用 SL2 域的其他信息，请联系 [CellTrust](https://www.celltrust.com/contact-us/#form)。

- 获取凭据以访问 SL2 域的管理员帐户。

- 必须在步骤 1 中创建 CellTrust SL2 数据连接器 (并将其在步骤 3) 中完成的用户分配给 Exchange Online 中的邮箱导入导出角色。 若要在"数据连接器"页上添加连接器，需要此 **角色Microsoft 365 合规中心。** 默认情况下，不会向角色组分配此角色Exchange Online。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 此数据连接器可用于美国政府GCC中Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-create-a-celltrust-sl2-connector"></a>步骤 1：创建 CellTrust SL2 连接器

第一步是在数据连接器Microsoft 365 合规中心。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **窗格，然后单击** "数据连接器"。

2. 在" **概述"** 选项卡上，单击 **"筛选** "并选择 **"By CellTrust"，** 然后应用筛选器。

   ![配置筛选器以显示 CellTrust 连接器。](../media/DataConnectorsFilter.png)

3. 单击 **CellTrust SL2 (预览) 。**

4. 在 **CellTrust SL2 (预览**) "产品说明"页上，单击"**添加连接器"。**

5. 在"**服务条款"页上**，单击"接受 **"。**

6. 输入标识连接器的唯一名称，然后单击下一 **步**。 创建连接器后，输入的名称将标识"数据连接器"页上的连接器。

7. 在"**登录到您的 CellTrust 帐户"页上**，单击 **"登录到 CellTrust"。** You'll be redirected to the **CellTrust Portal for Microsoft 365** in a new browser window.

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>步骤 2：选择要存档的域或 US

下一步是登录到 CellTrust SL2 域的管理员帐户，然后选择要存档在 Microsoft 365 中的域和 MICROSOFT 365。

1. 在"CellTrust **Microsoft 365 连接器**"页上，选择 SL2 云服务中的环境以显示登录页面。

   通常，应该会看到一个表示环境的选项。 但是，如果您具有多个环境的域，则会看到每个环境的选项。 做出选择后，你将重定向到 SL2 登录页。

2. 使用域或 OU 管理员帐户凭据登录。

   如果你以 SL2 域管理员登录，你将看到域的名称和该域中的 US。 如果您没有 OUS，则只会看到您的域的名称。 如果您以 OU 管理员角色登录，则只会看到 OU 的名称。

3. 启用要存档的业务单位。 选择域不会自动选择 US。 必须单独启用每个 OU 才能将其存档。

   ![启用要存档的 US。](../media/EnableCellTrustOUs.png)

4. 完成选择后，关闭浏览器窗口，然后返回到向导Microsoft 365 合规中心。 几秒钟后，向导将自动前进到映射用户的下一步。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

最后一步是映射用户并完成连接器在 Microsoft 365 合规中心。

1. 在"**用户映射"** 页上，如果用户的电子邮件地址在 SL2 和 Microsoft 365 中均相同，请选择"启用自动用户映射"。 否则，您应通过上载 CSV 文件手动将用户的 SL2 地址映射到其Microsoft 365电子邮件地址。

2. 单击 **"下** 一步"，查看设置，然后单击" **完成** "以创建连接器。

   新连接器将添加到"数据连接器" **页上** 的列表中。

## <a name="get-help-from-celltrust"></a>从 CellTrust 获取帮助

有关与 CellTrust 联系的详细信息，请参阅 [CellTrust 客户支持](https://www.celltrust.com/contact-us/#support) 页，了解有关设置 CellTrust SL2 数据连接器的帮助。

## <a name="more-information"></a>更多信息

- 域管理员可以为域或该域中的任何 US 设置连接器。 如果使用 OU 管理员帐户，则只能为特定 OU 设置连接器。

- 若要成功完成上述步骤，您必须获得一个Microsoft 365 E5许可证，并拥有适当的Microsoft Office权限。

- 若要测试新连接器，使用 SL2 移动应用或 SL2 门户发送短信。 转到你的邮箱Microsoft 365打开 **收件箱中的 CellTrust SL2** 文件夹。 可能需要几分钟时间，短信才能显示在邮箱中。

- 许多法律和法规都要求以如下方式保留电子通信：在请求时，可以生成该通信作为证据。 电子 (电子数据) 用于遵守电子通信的生产要求。 企业资讯存档 (EIA) 解决方案旨在执行电子数据展示，并提供保留策略管理、数据分类和内容监督等功能。 Microsoft 365提供长期保留解决方案，以遵守影响组织的法规和标准。

- 本文档 *中使用的* 术语存档是指在 EIA 存档解决方案中使用的企业资讯 (存档) 。 EIA 解决方案具有电子数据展示功能，可生成用于法律诉讼、诉讼、审核和调查的文档。 在用于灾难恢复和业务连续性的备份和还原上下文中进行存档并非本文档中术语的预定用途。
