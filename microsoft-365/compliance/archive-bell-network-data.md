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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理员可以设置 TeleMessage 连接器，以从 Bell 网络导入和存档短信和彩信数据。 这样，您可以在 Microsoft 365 中存档来自第三方数据源的数据，以便您可以使用合规性功能（如合法保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: fd2c986d31e148d209734f0aa65c7b12f950e2eb
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643644"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>设置连接器以存档 Bell Network 数据

使用 Microsoft 365 合规中心 中的 TeleMessage 连接器从 Bell 网络导入和存档短信服务 (SMS) 和彩信服务 (MMS) 消息。 设置和配置连接器后，它将每天连接到组织的 Bell 网络一次，并导入短信和彩信到 Microsoft 365 中的邮箱。

将短信和彩信存储在用户邮箱中后，可以将 Microsoft 365 合规性功能（如诉讼保留、内容搜索和 Microsoft 365 保留策略）应用于 Bell Network 数据。 例如，您可以使用内容搜索搜索 Bell Network SMS/MMS，或将包含 Bell Network 连接器数据的邮箱与案例的保管人Advanced eDiscovery关联。 使用 Bell 网络连接器在服务器中导入和存档Microsoft 365可帮助组织遵守政府及法规策略。

## <a name="overview-of-archiving-bell-network-data"></a>存档 Bell Network 数据概述

以下概述介绍使用连接器在服务器中存档 Bell Network 数据Microsoft 365。

![Bell 网络存档工作流。](../media/BellNetworkConnectorWorkflow.png)

1. 您的组织与 TeleMessage 和 Bell 合作，以设置 Bell 网络连接器。 有关详细信息，请参阅 [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver)。

2. 实时地，来自组织的 Bell Network 的短信和彩信将复制到 TeleMessage 站点。

3. 在 Microsoft 365 合规中心 创建的 Bell 网络连接器每天连接到 TeleMessage 站点，将过去 24 小时内的短信和彩信转移到 Microsoft 云中的安全 Azure 存储 位置。 连接器还会将短信和彩信的内容转换为电子邮件格式。

4. 连接器将移动通信项目导入到特定用户的邮箱。 将创建一个名为 **Bell SMS/MMS 网络** 存档器的新文件夹，该文件夹将导入到特定用户的邮箱中。 连接器使用"用户的电子邮件地址"属性的值 *执行此映射* 。 每个短信和彩信都包含此属性，该属性填充了邮件每个参与者的电子邮件地址。

   除了使用"用户的电子邮件地址"属性的值进行自动用户映射之外，您还可以通过上载 CSV 映射文件来定义自定义映射。 此映射文件包含您Microsoft 365的移动电话号码和相应的电子邮件地址。 如果同时启用自动用户映射和自定义映射，连接器将首先针对每个 Bell Network 项查看自定义映射文件。 如果找不到与Microsoft 365移动电话号码对应的有效用户，连接器将使用其尝试导入的项目的电子邮件地址属性中的值。 如果连接器在自定义映射文件或 Bell Network 项目的电子邮件地址属性中找不到Microsoft 365用户，该项目将不会导入。

## <a name="before-you-set-up-a-connector"></a>设置连接器之前

存档 Bell Network 数据所需的一些实现步骤Microsoft 365且必须先完成，然后才能在合规中心创建连接器。

- 从 [TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) 订购 Bell Network Archiver 服务，并获取组织的有效管理帐户。 在合规中心创建连接器时，需要登录此帐户。

- 获取 Bell Network 帐户和帐单联系人详细信息，以便填写 TeleMessage 载入表单，然后从 Bell 订购邮件存档服务。

- 在 TeleMessage 帐户中注册需要 Bell SMS/MMS 网络存档的所有用户。 注册用户时，请确保使用用于其帐户Microsoft 365电子邮件地址。

- 员工必须在 Bell 移动网络上拥有公司拥有和负责企业的移动电话。 在 BYOD Microsoft 365中存档消息不适用于员工拥有的设备或"自带设备 (BYOD) 设备。

- 必须为创建 Bell 网络连接器的用户分配邮箱导入导出Exchange Online。 在"数据连接器"页的"数据连接器"**页中添加连接器** Microsoft 365 合规中心。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"管理"角色组Exchange Online。 也可以创建角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 此 TeleMessage 数据连接器可用于美国政府GCC中Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-bell-network-connector"></a>创建 Bell 网络连接器

最后一步是在服务器中创建 Bell 网络Microsoft 365 合规中心。 连接器使用您提供的信息连接到 TeleMessage 站点，将短信/彩信传输至 Microsoft 365 中的相应用户邮箱框。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com) 然后单击数据连接器  >  **Bell SMS/MMS 网络存档器**。

2. 在 **"Bell Network** 产品说明"页上，单击" **添加连接器"**

3. 在"**服务条款"页上**，单击"接受 **"。**

4. 在"**登录到 TeleMessage"** 页上的"步骤 3"下，在下列框中输入所需信息，然后单击"下一步 **"。**

   - **用户名：** 你的 TeleMessage 用户名。

   - **密码：** 你的 TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在" **用户映射"** 页上，启用自动用户映射。 若要启用自定义映射，请上载包含用户映射信息的 CSV 文件，然后单击"下一步 **"。**

7. 查看设置，然后单击" **完成** "创建连接器。

8. 转到合规 **中心** 内"数据连接器"页上的"连接器"选项卡，查看新连接器的导入过程的进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项目。 稍后将提供对较大项目的支持。
