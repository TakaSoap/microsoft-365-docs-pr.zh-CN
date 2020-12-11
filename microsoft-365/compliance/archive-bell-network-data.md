---
title: 设置连接器以存档 Bell SMS/MMS 网络数据
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
description: 管理员可以设置 TeleMessage 连接器，以从 Bell 网络导入和存档短信和彩信数据。 这允许你在 Microsoft 365 中存档来自第三方数据源的数据，以便可以使用合规性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: d615488e5f6441efd828a6b91c187e7a8f5ca2c8
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620473"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>设置连接器以存档 Bell Network 数据

使用 Microsoft 365 合规中心中的 TeleMessage 连接器从 Bell 网络导入和存档短信服务 (SMS) 和彩信服务 (MMS) 消息。 设置和配置连接器后，它每天连接到组织的 Bell Network 一次，将短信和彩信导入 Microsoft 365 中的邮箱。

将短信和彩信存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Bell Network 数据。 例如，您可以使用内容搜索搜索 Bell Network SMS/MMS，或将包含 Bell 网络连接器数据的邮箱与高级电子数据展示案例中的保管人关联。 使用 Bell 网络连接器在 Microsoft 365 中导入和存档数据可帮助组织遵守政府政策和法规策略。

## <a name="overview-of-archiving-bell-network-data"></a>对 Bell Network 数据进行存档的概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Bell Network 数据的过程。

![Bell Network archiving workflow](../media/BellNetworkConnectorWorkflow.png)

1. 您的组织与 TeleMessage 和 Bell 合作，以设置 Bell 网络连接器。 有关详细信息，请参阅[Bell Network Archiver。](https://www.telemessage.com/office365-activation-for-bell-network-archiver)

2. 每 24 小时一次，来自您组织的 Bell Network 的短信和彩信将复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心创建的 Bell 网络连接器每天连接到 TeleMessage 站点，将过去 24 小时内的短信和彩信转移到 Microsoft 云中安全的 Azure 存储位置。 连接器还会将短信和彩信的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 在特定用户的邮箱中创建名为 **Bell SMS/MMS 网络** 存档程序的新文件夹，项目将导入到该文件夹中。 连接器使用用户的电子邮件地址属性的值执行 *此映射* 。 每个短信和彩信都包含此属性，此属性填充了邮件每个参与者的电子邮件地址。

   除了使用用户的电子邮件地址属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含组织中用户的移动电话号码和相应的 Microsoft 365 电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器将首先针对每个 Bell Network 项查看自定义映射文件。 如果找不到与用户移动电话号码对应的有效 Microsoft 365 用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或 Bell Network 项目的电子邮件地址属性中找不到有效的 Microsoft 365 用户，将不会导入该项目。

## <a name="before-you-begin"></a>开始之前

存档 Bell Network 数据所需的一些实施步骤在 Microsoft 365 外部，必须先完成这些步骤，然后才能在合规中心创建连接器。

- 从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 订购 Bell Network Archiver 服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取 Bell Network 帐户和帐单联系人详细信息，以便填写 TeleMessage 载入表单，然后从 Bell 订购邮件存档服务。

- 在 TeleMessage 帐户中注册需要 Bell SMS/MMS 网络存档的所有用户。 注册用户时，请务必使用用于其 Microsoft 365 帐户的相同电子邮件地址。

- 你的员工必须在 Bell 移动网络中拥有公司拥有和负责企业的移动电话。 Microsoft 365 中的存档邮件不适用于员工拥有或"自带设备 (BYOD) 设备。

- 必须在 Exchange Online 中为创建 Bell 网络连接器的用户分配邮箱导入导出角色。 这是在 Microsoft 365合规中心的"数据连接器"页中添加连接器所必需。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将邮箱导入导出角色添加到 Exchange Online 中的组织管理角色组。 也可以创建一个角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)Exchange Online[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)中管理角色组"一文的"创建角色组或修改角色组"部分。

## <a name="create-a-bell-network-connector"></a>创建 Bell 网络连接器

最后一步是在 Microsoft 365 合规中心创建 Bell Network 连接器。 连接器使用你提供的信息连接到 TeleMessage 网站，将短信/彩信传输给 Microsoft 365 中的相应用户邮箱。

1. 转到并 [https://compliance.microsoft.com](https://compliance.microsoft.com) 单击数据连接器  >  **Bell SMS/MMS 网络存档器**。

2. 在 **"Bell Network** 产品说明"页上，单击 **"添加连接器"**

3. 在"**服务条款"页上**，单击"**接受"。**

4. 在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一 **步"。**

   - **用户名：** TeleMessage 用户名。

   - **密码：** TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在 **"用户映射"** 页上，启用自动用户映射。 若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一 **步"。**

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到合规性 **中心** 中"数据连接器"页上的"连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
