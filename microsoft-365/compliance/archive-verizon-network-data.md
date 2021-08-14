---
title: 设置连接器以将 Verizon 网络数据存档到 Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以在 Microsoft 365 中从 Verizon 网络导入和存档短信和彩信Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: a484d8919c549bedf43bdf3895da5d0a7795f041f6514ac2720681894bfeabc4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53820648"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>设置连接器以存档 Verizon 网络数据

使用 Microsoft 365 合规中心 中的 TeleMessage 连接器从 Verizon 网络导入和存档短信服务 (SMS) 和彩信服务 (MMS) 数据。 设置和配置连接器后，它将每天连接到组织的 Verizon 网络一次，并导入短信和彩信数据到 Microsoft 365 中的邮箱。

将 Verizon 网络连接器数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Verizon 数据。 例如，您可以使用内容搜索搜索 Verizon 短信和彩信，或将包含 Verizon 网络数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 Verizon 网络连接器在 Microsoft 365导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-verizon-network-data"></a>存档 Verizon 网络数据概述

以下概述介绍使用连接器在服务器中存档 Verizon 网络数据Microsoft 365。

![Verizon 网络存档工作流](../media/VerizonNetworkConnectorWorkflow.png)

1. 你的组织与 TeleMessage 和 Verizon 合作以设置 Verizon 网络连接器。 有关详细信息，请参阅[Verizon Network Archiver。](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/)

2. 每 24 小时发送一次，来自组织的 Verizon 网络的短信和彩信将复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心 创建的 Verizon 网络连接器每天连接到 TeleMessage 站点，将过去 24 小时内的短信和彩信转移到 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将短信和彩信的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 名为 **"Verizon SMS/MMS 网络** 存档器"的新文件夹将创建于特定用户的邮箱中，并且项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。 每个短信和彩信都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来实现自定义映射。 此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器首先会针对每个 Verizon 项查看自定义映射文件。 如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或 Verizon Microsoft 365电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

存档 Verizon 网络数据所需的一些实现步骤位于 Microsoft 365 且必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage 订购 Verizon 网络](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 存档器服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取您的 Verizon 网络帐户和帐单联系人详细信息，以便可以填写 TeleMessage 载入表单，然后从 Verizon 订购邮件存档服务。

- 在 TeleMessage 帐户中注册需要 Verizon SMS 和 MMS 存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 员工必须在 Verizon 移动网络上拥有公司拥有和负责企业的移动电话。 在 BYOD Microsoft 365中存档消息不适用于员工拥有的设备或自带设备 (BYOD) 设备。

- 必须为创建 Verizon 网络连接器的用户分配邮箱导入导出Exchange Online。 这是在"数据连接器"页的"数据连接器 **"页中添加** Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 此数据连接器可用于美国政府GCC云Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-verizon-network-connector"></a>创建 Verizon 网络连接器

完成上一部分中所述的先决条件后，可以在部署中创建 Verizon 网络Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将短信和彩信传输至 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击数据 **连接器**  >  **Verizon 网络**。

2. 在 **"Verizon 网络** 产品说明"页上，单击" **添加连接器"**

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