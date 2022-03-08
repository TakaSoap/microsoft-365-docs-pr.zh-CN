---
title: 设置连接器以存档 AT&T SMS/MMS 网络数据
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
description: 管理员可以设置 TeleMessage 连接器，以从 AT 和 T 移动网络导入和存档&短信和彩信数据。 这样，您就可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 2b1e03c4d434b08c3dce21ed42c24e4573513c24
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322207"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>设置连接器以存档 AT&T SMS/MMS 数据

在 T Mobile 网络中使用 teleMessage Microsoft 365 合规中心从 AT 和 T 移动网络导入和存档&短信和彩信数据。 设置和配置连接器后，它每天连接到组织的 AT&T 网络一次，并导入短信和彩信数据到 Microsoft 365 中的邮箱。

在用户邮箱中存储短信和彩信后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 AT&T 网络数据。 例如，可以使用内容搜索&AT&T 网络数据，或者将包含 AT&T 网络连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 AT&T 网络连接器在 Microsoft 365 导入和存档数据可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-att-network-data"></a>存档 AT&T 网络数据概述

以下概述介绍使用连接器在 Microsoft 365 中存档 AT&T 网络数据的过程。

![ATT 网络存档工作流。](../media/ATTNetworkConnectorWorkflow.png)

1. 您的组织与 TeleMessage 合作，以设置 AT&T 网络连接器。 有关信息，请参阅 [AT&T 网络存档器](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)。

2. 实时地，来自组织的 AT 和 T 网络的短信&彩信复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心 创建的 AT&T 网络连接器每天连接到 TeleMessage 站点，将过去 24 小时内的短信和彩信转移到 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将短信和彩信的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 名为 **AT&T SMS/MMS 网络** 存档器的新文件夹在用户的邮箱中创建，项目将导入到该文件夹中。 连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。 每个短信和彩信都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。
 
   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器将首先查看自定义映射文件，针对每个电子邮件项目。 如果找不到与Microsoft 365电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或电子邮件Microsoft 365电子邮件地址属性中找不到有效的邮件用户，则不导入该项目。

## <a name="before-you-begin"></a>准备工作

存档 AT&T 网络数据所需的一些实现步骤位于外部Microsoft 365且必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage 订购移动存档器服务，](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取 AT&T 帐户和帐单联系人详细信息，以便可以填写 TeleMessage 载入表单，然后从 AT&T 订购邮件存档服务。

- 在 TeleMessage 帐户中注册&AT/T SMS/MMS 网络存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 你的员工必须在 AT 和 T 移动网络中拥有公司拥有和负责&移动电话。 在 BYOD Microsoft 365中存档消息不适用于员工拥有或"自带设备 (BYOD) 设备。

- 必须为创建 AT 连接器&T 网络连接器的用户分配数据连接器管理员角色。 若要在"数据连接器"页上添加连接器，需要此Microsoft 365 合规中心。 默认情况下，此角色添加到多个角色组。 有关这些角色组的列表，请参阅安全与合规中心内的权限中的"安全与合规& ["部分](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 或者，您组织的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅"权限"部分中的"创建自定义[角色Microsoft 365 合规中心](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- 此 TeleMessage 数据连接器可用于美国政府GCC环境中Microsoft 365环境。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未涵盖在 Microsoft 365 合规性和数据保护承诺中。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-att-network-connector"></a>创建 AT&T 网络连接器

完成上一部分中所述的先决条件后，可以在&T 网络连接器Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将短信和彩信传输至 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击"数据 **连接器** \ **AT&T 网络"**。

2. 在 **"AT&T 网络产品说明** "页上，单击" **添加连接器"**

3. 在" **服务条款"页上** ，单击"接受 **"**。

4. 在" **登录到 TeleMessage** "页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"**。

   - **用户名：** 你的 TeleMessage 用户名。

   - **密码：** 你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在" **用户映射"** 页上，启用自动用户映射。 若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一步 **"**。

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到合规 **中心** 内"数据连接器"页上的"连接器"选项卡，查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
