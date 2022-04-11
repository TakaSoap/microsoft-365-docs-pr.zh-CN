---
title: 在 Microsoft 365 中设置连接器以存档罗杰斯网络数据
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
description: 管理员可以设置 TeleMessage 连接器，以便在 Microsoft 365 中导入和存档 Rogers 网络数据。 这样就可以在Microsoft 365中存档来自第三方数据源的数据，以便可以使用符合性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: 54c57c2ddf8d4224884137efb0cfa4679a13b46d
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758698"
---
# <a name="set-up-a-connector-to-archive-rogers-network-data"></a>设置连接器以存档罗杰斯网络数据

使用Microsoft 365 合规中心中的 TeleMessage 连接器从 Rogers 移动网络导入和存档短信和 MMS 数据。 设置和配置[罗杰斯网络存档器连接器](https://www.telemessage.com/mobile-archiver/network-archiver/rogers/)后，它将连接到组织的 Rogers 移动网络，并将短信和彩信数据导入到Microsoft 365中的邮箱。

在用户邮箱中存储来自 Rogers 移动网络的数据后，可以将Microsoft 365合规性功能（如诉讼保留、内容搜索和Microsoft 365保留策略）应用于数据。 例如，可以使用内容搜索或与核心电子数据展示案例关联的搜索从 Rogers 移动网络搜索短信和 MMS 消息。 使用 Rogers 网络存档器连接器在Microsoft 365中导入和存档数据可以帮助组织遵守公司治理法规和法规策略。

## <a name="overview-of-archiving-rogers-mobile-network-data"></a>对罗杰斯移动网络数据进行存档概述

以下概述介绍了使用连接器在 Microsoft 365 中存档 Rogers 短信和 MMS 数据的过程。

![罗杰斯网络存档工作流。](../media/RogersNetworkConnectorWorkflow.png)

1. 你的组织使用 TeleMessage 来设置罗杰斯网络存档器连接器。 有关详细信息，请参阅[激活 TeleMessage Rogers 网络存档器以进行Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-the-rogers-network-archiver/)。

2. 组织中的 Rogers 移动网络数据将实时复制到 TeleMessage 站点。

3. 在Microsoft 365 合规中心中创建的罗杰斯网络存档器连接器每天连接到 TeleMessage 站点，并将过去 24 小时内的电子邮件传输到 Microsoft 云中的安全Azure 存储区域。

4. 连接器将移动通信项导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 Rogers SMS/MMS 网络存档器的新文件夹，这些项目将导入到该邮箱中。 连接器使用 *用户的电子邮件地址属性的* 值执行映射。 每个电子邮件都包含此属性，其中填充了电子邮件的每个参与者的电子邮件地址。

   除了使用 *用户的电子邮件地址* 属性的值进行自动用户映射外，还可以通过上传 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动号码以及每个用户的相应Microsoft 365邮箱地址。 如果启用自动用户映射并提供自定义映射，则对于每个电子邮件项，连接器将首先查看自定义映射文件。 如果找不到与用户的移动号码相对应的有效Microsoft 365用户，连接器将使用该电子邮件项的用户的电子邮件地址属性。 如果连接器在自定义映射文件或电子邮件项 *的用户电子邮件地址* 属性中找不到有效的Microsoft 365用户，则不会导入该项目。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- [从 TeleMessage 订购 Rogers 网络存档器服务](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)，并为组织获取有效的管理帐户。 在合规中心创建连接器时，需要登录到此帐户。

- 在 TeleMessage 帐户中注册所有需要罗杰斯网络存档的用户。 注册用户时，请务必使用用于其Microsoft 365帐户的相同电子邮件地址。

- 你的员工必须在 O2 移动网络上拥有公司拥有和公司责任的移动电话。 Microsoft 365中的存档消息不适用于员工拥有或“自带设备 (BYOD) 设备。

- 获取组织的 Rogers 帐户和计费联系人详细信息，以便你可以完成载入表单，并从 Rogers 订购消息存档服务。

- 在步骤 3 中创建 Rogers 网络存档器连接器的用户必须分配“数据连接器管理员”角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

- 此 TeleMessage 数据连接器在美国政府云Microsoft 365 GCC环境中可用。 第三方应用程序和服务可能涉及在Microsoft 365基础结构之外的第三方系统上存储、传输和处理组织的客户数据，因此Microsoft 365合规性和数据保护承诺不涵盖这些数据。 Microsoft 没有表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-rogers-network-archiver-connector"></a>创建 Rogers 网络存档器连接器

完成上一部分中所述的先决条件后，可以在Microsoft 365 合规中心中创建 Rogers 网络存档器连接器。 连接器使用你提供的信息连接到 TeleMessage 站点，并将 Rogers SMS/MMS 数据传输到Microsoft 365中的相应用户邮箱框。

1. 转到 <https://compliance.microsoft.com> 并单击 **“数据连接器** > **Rogers 网络存档器**”。

2. 在 **“罗杰斯网络存档器** 产品说明”页上，单击 **“添加连接器**”。

3. 在 **“服务条款”** 页上，单击 **“接受**”。

4. 在 **“登录到 TeleMessage** ”页上的步骤 3 下，在以下框中输入所需的信息，然后单击 **“下一步**”。

    - **用户：** TeleMessage 用户名。

    - **密码：** TeleMessage 密码。

5. 创建连接器后，可以关闭弹出窗口并转到下一页。

6. 在 **“用户映射** ”页上，启用自动用户映射。 若要启用自定义映射，请上传包含用户映射信息的 CSV 文件，然后单击 **“下一步**”。

7. 查看设置，然后单击 **“完成** ”以创建连接器。

8. 转到 **“数据连接器** ”页中的“连接器”选项卡，查看新连接器的导入过程进度。

## <a name="known-issues"></a>已知问题

- 目前，我们不支持导入大于 10 MB 的附件或项。 稍后会提供对较大项的支持。
