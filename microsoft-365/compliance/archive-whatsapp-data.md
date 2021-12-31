---
title: 设置连接器以将 WhatsApp 数据存档在 Microsoft 365
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
description: 管理员可以设置 TeleMessage 连接器，以将 WhatsApp 数据导入和存档Microsoft 365。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 4f0db9fbc33f63912667c3f9202352d2955fd55e
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643876"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>设置连接器以存档 WhatsApp 数据

使用远程邮箱中的 TeleMessage Microsoft 365 合规中心导入和存档 WhatsApp 呼叫、聊天、附件、文件和已删除的消息。 设置和配置连接器后，它将每天连接到组织的 TeleMessage 帐户一次，并且使用 TeleMessage WhatsApp 电话 存档器或 TeleMessage WhatsApp 云存档器将员工的移动通信导入 Microsoft 365 中的邮箱。

将 WhatsApp 数据存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和Microsoft 365保留策略）应用于 WhatsApp 数据。 例如，您可以使用内容搜索搜索 WhatsApp 邮件，或将包含 WhatsApp 邮件的邮箱与特定案例的保管人Advanced eDiscovery关联。 使用 WhatsApp 连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-whatsapp-data"></a>存档 WhatsApp 数据概述

以下概述介绍使用连接器在应用程序服务中存档 WhatsApp 数据Microsoft 365。

![WhatsApp 存档工作流。](../media/WhatsAppConnectorWorkflow.png)

1. 您的组织与 TeleMessage 合作，以设置 WhatsApp 存档器连接器。 有关详细信息，请参阅 [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)。

2. 实时将组织的 WhatsApp 数据复制到 TeleMessage 网站。

3. 在 Microsoft 365 合规中心 中创建的 WhatsApp 连接器每天连接到 TeleMessage 站点，将过去 24 小时内的 WhatsApp 数据传输至 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将内容 WhatsApp 数据转换为电子邮件格式。

4. 连接器将 WhatsApp 数据导入到特定用户的邮箱。 将创建一个名为 **WhatsApp Archiver** 的新文件夹，该文件夹将导入到特定用户的邮箱中。 连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。 每个 WhatsApp 邮件都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来实现自定义映射。 此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器将首先针对每个 WhatsApp 项查看自定义映射文件。 如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或 WhatsApp Microsoft 365电子邮件地址属性中找不到有效的邮件用户，该项目将不会导入。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

存档 WhatsApp 通信数据所需的一些实现步骤位于外部Microsoft 365且必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage 订购 WhatsApp Archiver](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 在 TeleMessage 帐户中注册需要 WhatsApp 存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 在员工的移动电话上电话[TeleMessage WhatsApp](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/)和 Archiver 应用并激活它。 或者，可以在员工的移动电话上安装常规 WhatsApp 或 WhatsApp Business 应用，并扫描 TeleMessage 网站上 QR 代码，以激活 WhatsApp 云存档器服务。 有关详细信息，请参阅[WhatsApp Cloud Archiver。](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)

- 必须为创建 Verizon 网络连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"页中添加连接器Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 此 TeleMessage 数据连接器可用于美国政府云GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-whatsapp-archiver-connector"></a>创建 WhatsApp 存档器连接器

完成上一部分中所述的先决条件后，可以在"设置"部分中创建 whatsApp Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将 WhatsApp 数据传输至 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击数据 **连接器**  >  **WhatsApp Archiver**。

2. 在 **"WhatsApp 存档程序产品** 说明"页上，单击" **添加连接器"**

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
