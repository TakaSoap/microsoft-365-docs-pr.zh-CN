---
title: 设置连接器以在 Microsoft 365 中存档 FX Connect 数据
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
description: 管理员可以设置连接器以从 Microsoft 365 中的 Globanet FX Connect 导入和存档数据。 此连接器允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: da6b0c82193fc76090ba9a324ea4c3d8f415063a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904202"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>设置连接器以存档 FX Connect 数据

使用 Microsoft 365 合规中心中的 Globanet 连接器，将数据从 FX Connect 协作平台导入并存档到 Microsoft 365 组织的用户邮箱。 Globanet 提供 [配置为](https://globanet.com/fx-connect/) 捕获 FX Connect 项目以及将这些项目导入到 Microsoft 365 的 FX Connect 连接器。 连接器将内容从 FX Connect（如会议、邮件和您组织的 FX Connect 帐户的其他详细信息）转换为电子邮件格式，然后将这些项目导入到 Microsoft 365 中的用户邮箱。

将 FX Connect 数据存储在用户邮箱中后，可以应用 Microsoft 365 合规性功能，如诉讼保留、电子数据展示、保留策略和保留标签以及通信合规性。 使用 FX Connect 连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府法规策略。

## <a name="overview-of-archiving-fx-connect-data"></a>存档 FX Connect 数据概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 FX Connect 信息的过程。

![FX Connect 数据的存档工作流](../media/FXConnectConnectorWorkflow.png)

1. 您的组织与 FX Connect 合作，以设置和配置 FX Connect 站点。

2. 每 24 小时一次，来自 FX Connect 帐户的项目将复制到 Globanet Merge1 网站。 连接器还会将 FX Connect 项目转换为电子邮件格式。

3. 在 Microsoft 365 合规中心创建的 FX Connect 连接器每天连接到 Globanet Merge1 网站，将 FX Connect 项目转移到 Microsoft 云中安全的 Azure 存储位置。

4. 连接器使用自动用户映射的 *Email* 属性值将项目导入特定用户的邮箱，如步骤 [3 中所述](#step-3-map-users-and-complete-the-connector-setup)。 在用户邮箱中创建名为 **FX Connect** 的收件箱文件夹中的子文件夹，项目将导入到该文件夹中。 连接器使用 *Email* 属性的值实现此操作。 每个 FX Connect 项目都包含此属性，该属性用项目每个参与者的电子邮件地址填充。

## <a name="before-you-begin"></a>开始之前

- 为 Microsoft 连接器创建 Globanet Merge1 帐户。  若要创建帐户，请联系 [Globanet 客户支持](https://globanet.com/ms-connectors-contact)。 在步骤 1 中创建连接器时，将登录到此帐户。

- 必须在步骤 1 中创建 FX Connect 连接器 (在步骤 3) 中完成该连接器的用户必须分配至 Exchange Online 中的邮箱导入导出角色。 在 Microsoft 365 合规中心的"数据连接器"页面上添加连接器需要此角色。 默认情况下，此角色不会分配给 Exchange Online 中的角色组。 可以将"邮箱导入导出"角色添加到 Exchange Online 中的"组织管理"角色组。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的创建角色组或修改角色组部分。

## <a name="step-1-set-up-the-fx-connect-connector"></a>步骤 1：设置 FX 连接连接器

第一步是访问 Microsoft 365 合规中心的数据连接器页面，并创建 FX Connect 数据的连接器。 

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **FX Connect**。

2. 在 **"FX Connect** 产品说明"页上，单击"**添加连接器"。**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 输入标识连接器的唯一名称，然后单击下一 **步**。

5. 登录到 Merge1 帐户以配置连接器。

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a>步骤 2：在 Globanet Merge1 网站上配置 FX 连接连接器

第二步是在 Merge1 网站上配置 FX 连接连接器。 若要了解如何配置 FX Connect 连接器，请参阅 [Merge1 第三方连接器用户指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)。

单击 **"保存&** 完成"后，将显示 Microsoft  365 合规中心中的连接器向导中的"用户映射"页。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步骤 3：映射用户并完成连接器设置

若要映射用户并完成 Microsoft 365 合规中心中的连接器设置，请按照以下步骤操作：

1. 在" **将 FX 连接到 Microsoft 365 用户"页上** ，启用自动用户映射。 FX Connect 项目包括名为 *Email* 的属性，该属性包含组织中用户的电子邮件地址。 如果连接器可以将此地址与 Microsoft 365 用户关联，则项目将导入该用户的邮箱。

2. 单击 **"下** 一步"，查看设置，然后转到"数据连接器"页以查看新连接器的导入过程的进度。

## <a name="step-4-monitor-the-fx-connect-connector"></a>步骤 4：监视 FX Connect 连接器

创建 FX Connect 连接器后，可以在 Microsoft 365 合规中心查看连接器状态。

1. 转到左侧 <https://compliance.microsoft.com/> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择 **"FX 连接** "连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

3. 在 **"源的连接器状态"** 下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含已导入到 Microsoft 云的数据。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。