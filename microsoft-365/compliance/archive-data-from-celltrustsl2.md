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
description: 了解如何设置和使用 CellTrust SL2 数据连接器导入和存档移动通信数据。
ms.openlocfilehash: e5e07e4138445e46cdd21edc0cfb01d871dd3b6e
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761144"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365"></a>将数据从 CellTrust SL2 存档到Microsoft 365

CellTrust SL2 捕获移动通信数据，并与领先的存档技术集成，以满足 FINRA、HIPAA、FOIA 和 TCPA 等法规的电子发现要求。 SL2 数据连接器将移动通信项导入到Microsoft 365。 本文介绍使用 CellTrust SL2 数据连接器进行存档将 SL2 与 Microsoft 365 集成的过程。 完成此过程假定你已订阅 CellTrust SL2 服务并熟悉 SL2 体系结构。 有关 CellTrust SL2 的信息，请参阅 <https://www.celltrust.com>。

在Microsoft 365中将数据导入到用户邮箱后，可以应用Microsoft 365合规性功能，例如诉讼保留、电子数据展示、Microsoft 365保留策略和通信合规性。 使用 CellTrust SL2 数据连接器在Microsoft 365中导入和存档数据可以帮助组织遵守政府和法规政策。

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>使用 CellTrust SL2 数据连接器存档概述

CellTrust 的 SL2 平台捕获来自多个源的通信数据。 SL2 数据源是人员对人 (P2P) 或应用程序到人员 (A2P) 。 本文中所述的过程仅与 P2P 数据源相关。 对于所有 P2P 数据源，协作中至少有一方是订阅 SL2 服务的 SL2 用户。 以下概述介绍了在 Microsoft 365 中使用 CellTrust SL2 数据连接器的过程。

![CellTrust SL2 服务的存档工作流。](../media/CellTrustSL2ConnectorWorkflow.png)

1. SL2 用户在Microsoft Azure中向 SL2 服务发送和接收数据。

2. 组织在 CellTrust 的 SL2 云服务环境中具有 SL2 域。 域可能有一个或多个组织单位 (OU) 。 SL2 云服务将数据传输到Microsoft Azure平台中高度安全的区域，以便数据永远不会离开Microsoft Azure环境。 根据 SL2 计划 (Enterprise、SMB 或政府) ，域托管在 Microsoft Azure Global 或 Microsoft Azure 政府版上。

3. 创建 CellTrust SL2 数据连接器后，域和 OU (无论 SL2 计划) 如何，都开始将数据发送到Microsoft 365。 数据源的结构化是为了支持基于数据源、OU 或域本身的报告。 因此，组织只需一个连接器即可将所有数据源馈送到Microsoft 365。

4. 连接器在每个映射用户下创建一个文件夹，其中包含一个名为 **CellTrust SL2** 的适当Office 365许可证。 此映射使用电子邮件地址将 CellTrust SL2 用户连接到Office 365邮箱。 如果 CellTrust SL2 中的用户 ID 在Office 365中没有匹配项，则不会存档用户的数据。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- 验证在 CellTrust SL2 云服务环境中是否具有域。 有关获取生产或试用 SL2 域的其他信息， [请联系 CellTrust](https://www.celltrust.com/contact-us/#form)。

- 获取用于访问 SL2 域的管理员帐户的凭据。

- 在步骤 1 (中创建 CellTrust SL2 数据连接器并在步骤 3) 中完成该连接器的用户必须分配数据连接器管理员角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

- 此 CellTrust 数据连接器在美国政府云Microsoft 365 GCC环境中可用。 第三方应用程序和服务可能涉及在Microsoft 365基础结构之外的第三方系统上存储、传输和处理组织的客户数据，因此Microsoft 365合规性和数据保护承诺不涵盖这些数据。 Microsoft 没有表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-create-a-celltrust-sl2-connector"></a>步骤 1：创建 CellTrust SL2 连接器

第一步是在Microsoft 365 合规中心中创建数据连接器。

1. 转到 <https://compliance.microsoft.com> 左侧导航窗格中并单击 **“数据连接器** ”。

2. 在“ **概述** ”选项卡上，单击 **“筛选器** ”并选择 **“按 CellTrust**”，然后应用筛选器。

   ![配置筛选器以显示 CellTrust 连接器。](../media/DataConnectorsFilter.png)

3. 单击 **CellTrust SL2 (预览)**。

4. 在 **CellTrust SL2 (预览)** 产品说明页上，单击 **“添加连接器**”。

5. 在 **“服务条款”** 页上，单击 **“接受**”。

6. 输入标识连接器的唯一名称，然后单击 **“下一步**”。 创建连接器后，输入的名称将标识 **数据连接器页上的连接器** 。

7. 在 **“登录到 CellTrust 帐户** ”页上，单击 **“登录到 CellTrust**”。 你将被重定向到 **CellTrust 门户，以便** 在新的浏览器窗口中Microsoft 365。

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>步骤 2：选择要存档的域或 OU

下一步是登录 CellTrust SL2 域的管理员帐户，然后选择要在Microsoft 365中存档的域和 OU。

1. 在“CellTrust **Microsoft 365连接器**”页上，选择 SL2 云服务中的环境以显示登录页。

   通常，应看到一个表示环境的选项。 但是，如果在多个环境中具有域，则会看到每个环境的选项。 进行选择后，将重定向到 SL2 登录页。

2. 使用域或 OU 管理员帐户凭据登录。

   如果以 SL2 域管理员身份登录，则会在该域中看到域的名称和 OU。 如果没有 OU，则只能看到域的名称。 如果以 OU 管理员身份登录，则只能看到 OU 的名称。

3. 启用要存档的业务单元。 选择域不会自动选择 OU。 必须单独启用每个 OU 来存档它。

   ![启用 OU 存档。](../media/EnableCellTrustOUs.png)

4. 完成所选内容后，关闭浏览器窗口并返回到Microsoft 365 合规中心中的向导页。 几秒钟后，向导会自动前进到下一步映射用户。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

最后一步是在Microsoft 365 合规中心中映射用户并完成连接器设置。

1. 在 **“用户映射**”页上，如果 SL2 和 Microsoft 365 中用户的电子邮件地址相同，请选择 **“启用自动用户映射**”。 否则，应通过上传 CSV 文件来手动用户电子邮件地址，该文件将用户的 SL2 地址映射到其Microsoft 365地址。

2. 单击 **“下一步**”，查看设置，然后单击 **“完成** ”以创建连接器。

   新的连接器将添加到 **“数据连接器** ”页上的列表中。

## <a name="get-help-from-celltrust"></a>从 CellTrust 获取帮助

有关联系 CellTrust 以获取有关设置 CellTrust SL2 数据连接器的帮助的详细信息，请参阅 [“CellTrust 客户支持”页](https://www.celltrust.com/contact-us/#support) 。

## <a name="more-information"></a>更多信息

- 域管理员可以为域或该域中的任何 OU 设置连接器。 如果使用 OU 管理员帐户，则只能为该特定 OU 设置连接器。

- 若要成功完成上述步骤，必须为你分配Microsoft 365 E5许可证并具有适当的Microsoft Office管理员权限。

- 若要测试新连接器，请使用 SL2 移动应用或 SL2 门户发送短信。 转到Microsoft 365邮箱，并在收件箱中打开 **CellTrust SL2** 文件夹。 短信可能需要几分钟才能显示在邮箱中。

- 许多法律和法规要求保持电子通信，以便在请求时将其作为证据进行制作。 电子发现 (电子数据展示) 用于遵守电子通信的生产。 企业资讯存档 (EIA) 解决方案旨在执行电子数据展示，并提供保留策略管理、数据分类和内容监督等功能。 Microsoft 365为遵守影响组织的法规和标准提供了长期保留解决方案。

- 本文档中使用的术语 *存档* 是指在企业资讯存档 (EIA) 解决方案中使用的上下文中存档。 EIA 解决方案具有电子数据展示功能，可生成用于法律诉讼、诉讼、审核和调查的文档。 在用于灾难恢复和业务连续性的备份和还原上下文中存档不是本文档中术语的预期用途。
