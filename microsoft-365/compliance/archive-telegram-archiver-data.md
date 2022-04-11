---
title: 在 Microsoft 365 中设置用于存档 Telegram 通信数据的连接器
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
description: 管理员可以设置 TeleMessage 连接器，以便在Microsoft 365中导入和存档 Telegram 通信数据。 这样就可以在Microsoft 365中存档来自第三方数据源的数据，以便可以使用符合性功能（如法定保留、内容搜索和保留策略）来管理组织的第三方数据。
ms.openlocfilehash: e44eaa160bc78015191d2ceaca99bebbd31462fc
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64762070"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data"></a>设置连接器以存档电报通信数据

使用Microsoft 365 合规中心中的 TeleMessage 连接器导入和存档电报聊天、附件、文件以及已删除的消息和呼叫。 设置和配置连接器后，连接到组织的 TeleMessage 帐户，并使用 Telegram Archiver 将员工的移动通信导入到Microsoft 365中的邮箱。

将 Telegram Archiver 连接器数据存储在用户邮箱中后，可以将Microsoft 365合规性功能（如诉讼保留、内容搜索和Microsoft 365保留策略）应用于 Telegram 通信数据。 例如，可以使用内容搜索搜索 Telegram 通信，或者将包含 Telegram 存档器连接器数据的邮箱与Advanced eDiscovery事例中的保管人关联。 使用 Telegram 存档器连接器在Microsoft 365中导入和存档数据可以帮助组织遵守公司治理法规和法规策略。

## <a name="overview-of-archiving-telegram-communications-data"></a>报表通信数据存档概述

以下概述介绍了使用连接器在Microsoft 365中存档 Telegram 通信数据的过程。

![电报通信存档工作流。](../media/TelegramConnectorWorkflow.png)

1. 组织使用 TeleMessage 设置 Telegram Archiver 连接器。 有关详细信息，请参阅[激活 TeleMessage Telegram Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/)。

2. 实时将组织的 Telegram 数据复制到 TeleMessage 站点。

3. 在Microsoft 365 合规中心中创建的 Telegram Archiver 连接器每天连接到 TeleMessage 站点，并将过去 24 小时内的电子邮件传输到 Microsoft 云中的安全Azure 存储区域。

4. 连接器将移动通信项导入到特定用户的邮箱。 将在特定用户的邮箱中创建一个名为 Telegram Archiver 的新文件夹，并将项目导入到该邮箱中。 连接器使用 *用户的电子邮件地址属性的* 值执行此映射。 每个电子邮件都包含此属性，其中填充了电子邮件的每个参与者的电子邮件地址。

> 除了使用 *用户的电子邮件地址* 属性的值进行自动用户映射外，还可以通过上传 CSV 映射文件来定义自定义映射。 此映射文件应包含用户的移动号码以及每个用户的相应Microsoft 365邮箱地址。 如果启用自动用户映射并提供自定义映射，则对于每个电子邮件项，连接器将首先查看自定义映射文件。 如果找不到与用户的移动号码相对应的有效Microsoft 365用户，连接器将使用电子邮件项的用户电子邮件地址属性。 如果连接器在自定义映射文件或电子邮件项 *的用户电子邮件地址* 属性中找不到有效的Microsoft 365用户，则不会导入该项目。

## <a name="before-you-set-up-a-connector"></a>在设置连接器之前

- [从 TeleMessage 订购 Telegram 存档服务](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)，并为组织获取有效的管理帐户。 在合规中心创建连接器时，需要登录到此帐户。

- 在 TeleMessage 帐户中注册所有需要电报存档的用户。 注册用户时，请务必使用用于其Microsoft 365帐户的相同电子邮件地址。

- 在员工的移动电话上安装 Telegram Archiver 应用并激活它。 Telegram Archiver 应用允许他们与其他 Telegram 用户进行通信和聊天。

- 在步骤 3 中创建 Telegram Archiver 连接器的用户必须分配数据连接器管理员角色。 在Microsoft 365 合规中心 **的数据连接器** 页上添加连接器需要此角色。 默认情况下，此角色将添加到多个角色组。 有关这些角色组的列表，请参阅 [安全&合规中心](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)“权限”中的“安全与合规中心中的角色”部分。 或者，组织中的管理员可以创建自定义角色组，分配数据连接器管理员角色，然后将相应的用户添加为成员。 有关说明，请参阅Microsoft 365 合规中心中的权[限中的](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)“创建自定义角色组”部分。

- 此 TeleMessage 数据连接器在美国政府云Microsoft 365 GCC环境中可用。 第三方应用程序和服务可能涉及在Microsoft 365基础结构之外的第三方系统上存储、传输和处理组织的客户数据，因此Microsoft 365合规性和数据保护承诺不涵盖这些数据。 Microsoft 没有表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="create-a-telegram-archiver-connector"></a>创建 Telegram Archiver 连接器

完成上一部分中所述的先决条件后，可以在Microsoft 365 合规中心中创建 Telegram Archiver 连接器。 连接器使用你提供的信息连接到 TeleMessage 站点，并将电报通信数据传输到Microsoft 365中的相应用户邮箱框。

1. 转到<https://compliance.microsoft.com>，然后单击 **Telegram 存档器**>**数据连接器**。

2. 在 **“电报存档器** 产品说明”页上，单击 **“添加连接器**”。

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
