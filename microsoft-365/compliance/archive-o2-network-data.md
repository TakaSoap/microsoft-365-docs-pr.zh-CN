---
title: 设置连接器以将 O2 网络数据存档在 Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以在 Microsoft 365 中从 O2 移动网络导入和存档短信和彩信Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 873396df23e9d4834c0da37e31af599d7fc0fb38
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61646129"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>设置连接器以存档 O2 网络数据

使用 Microsoft 365 合规中心 中的 TeleMessage 连接器从 O2 移动网络导入和存档短信 (短信) 短信和语音呼叫。 设置和配置连接器后，它每天连接到组织的 O2 网络一次，将短信和语音呼叫导入到 Microsoft 365 中的邮箱。

在用户邮箱中存储短信和语音呼叫后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 O2 网络数据。 例如，您可以使用内容搜索搜索 O2 网络短信和语音呼叫，或将包含 O2 网络数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 O2 网络连接器导入数据并存档数据Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-o2-network-data"></a>存档 O2 网络数据概述

以下概述介绍使用连接器在服务器中存档 O2 网络数据Microsoft 365。

![O2 网络存档工作流。](../media/O2NetworkConnectorWorkflow.png)

1. 您的组织与 TeleMessage 和 O2 一起设置 O2 网络连接器。 有关详细信息，请参阅 [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver)。

2. 每 24 小时一次，您组织的 O2 网络发送的短信和语音呼叫会复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心 中创建的 O2 网络连接器每天连接到 TeleMessage 站点，将短信和语音呼叫从前 24 小时转移到 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将短信和语音呼叫的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 名为 **"O2 SMS 和语音** 网络存档器"的新文件夹将创建于特定用户的邮箱中，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。 每个短信和语音呼叫都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器将首先针对每个 O2 项查看自定义映射文件。 如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或 O2 Microsoft 365电子邮件地址属性中找不到有效的邮件用户，则不导入该项目。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

存档 O2 网络数据所需的一些实现步骤位于外部Microsoft 365必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage 订购 O2 网络存档器服务，](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取 O2 网络帐户和帐单联系人详细信息，以便可以填写 TeleMessage 载入表单，然后从 O2 订购邮件存档服务。

- 在 TeleMessage 帐户中注册需要 O2 SMS 和语音网络存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 你的员工必须在 O2 移动网络上拥有公司拥有和负责企业的移动电话。 存档 MICROSOFT 365中的消息不适用于员工拥有或"自带设备 (BYOD) 设备。

- 必须为创建 O2 网络连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"页中添加连接器Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此 TeleMessage 数据连接器可用于美国政府云GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-an-o2-network-connector"></a>创建 O2 网络连接器

完成上一节中所述的先决条件后，可以在"配置"部分中创建 O2 网络Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将短信和语音呼叫转接到 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器** \> **O2 网络**。

2. 在 **"O2 网络产品** 说明"页上，单击" **添加连接器"**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**

   - **用户名：** 你的 TeleMessage 用户名。

   - **密码：** 你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在"**用户映射"页上**，启用自动用户映射，然后单击"下一步 **"。** 如果你需要自定义映射上传 CSV 文件，然后单击下一 **步**。

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到"数据连接器" **页中的"** 连接器"选项卡以查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。